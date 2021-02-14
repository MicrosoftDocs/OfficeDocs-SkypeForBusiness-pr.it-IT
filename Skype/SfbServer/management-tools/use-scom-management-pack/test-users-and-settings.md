---
title: Configurare gli utenti e le impostazioni di test del nodo Watcher
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Riepilogo: configurare gli account utente di test e le impostazioni del nodo Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: 687aec65089939d2f4cb7b110b4139eca28433fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814836"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurare gli utenti e le impostazioni di test del nodo Watcher
 
**Riepilogo:** Configurare gli account utente di test e le impostazioni del nodo Watcher per le transazioni sintetiche di Skype for Business Server.
  
Dopo avere configurato il computer che fungerà da nodo Watcher, è necessario eseguire le operazioni seguenti:
  
1. [Configurare gli account utente di](test-users-and-settings.md#testuser) test per l'utilizzo da parte di questi nodi Watcher. Se si utilizza il metodo di autenticazione Negotiate, è inoltre necessario utilizzare il cmdlet **Set-CsTestUserCredential** per abilitare questi account di test per l'utilizzo nel nodo Watcher.
    
2. Aggiornare le impostazioni di configurazione del nodo Watcher.
    
## <a name="configure-test-user-accounts"></a>Configurare gli account utente di test
<a name="testuser"> </a>

Gli account di test non devono rappresentare persone effettive, ma devono essere account di Active Directory validi. Inoltre, questi account devono essere abilitati per Skype for Business Server, devono avere indirizzi SIP validi e devono essere abilitati per VoIP aziendale (per usare la transazione sintetica Test-CsPstnPeerToPeerCall). 
  
Se si utilizza il metodo di autenticazione TrustedServer, è necessario verificare che tali account esistano e configurarli come specificato. È consigliabile assegnare almeno due utenti di test per ogni pool che si desidera testare. Se si utilizza il metodo di autenticazione Negotiate, è necessario utilizzare anche il cmdlet Set-CsTestUserCredential e Skype for Business Server Management Shell per consentire a questi account di test di funzionare con le transazioni sintetiche. A tale scopo, eseguire un comando simile al seguente (questi comandi presuppongono che i due account utente di Active Directory siano stati creati e che questi account siano abilitati per Skype for Business Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

È necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password. Se non si include la password, il cmdlet Set-CsTestUserCredential richiederà di immettere tali informazioni. Il nome utente può essere specificato utilizzando il formato nome dominio\nome utente mostrato nel blocco di codice precedente.
  
Per verificare che le credenziali utente di test siano state create, eseguire questi comandi da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Per ogni utente verranno restituite informazioni simili alle seguenti:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurare un nodo Watcher di base con le transazioni sintetiche predefinite

Dopo aver creato gli utenti di test, è possibile creare un nodo Watcher utilizzando un comando simile al seguente:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Questo comando crea un nuovo nodo Watcher che utilizza le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche. Nel nuovo nodo Watcher vengono inoltre utilizzati gli utenti di test watcher1@litwareinc.com e watcher2@litwareinc.com. Se il nodo Watcher utilizza l'autenticazione TrustedServer, i due account di test possono essere qualsiasi account utente valido abilitato per Active Directory e Skype for Business Server. Se il nodo Watcher utilizza il metodo di autenticazione Negotiate, questi account utente devono essere abilitati anche per il nodo Watcher utilizzando il cmdlet Set-CsTestUserCredential.
  
Per verificare che l'individuazione automatica del pool di destinazione per l'accesso sia configurata correttamente invece di usare direttamente la destinazione di un pool, eseguire la procedura seguente:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurazione dei test estesi

Se si desidera abilitare il test PSTN, che verifica la connettività con la rete telefonica a commutazione pubblica, è necessario eseguire alcune operazioni di configurazione aggiuntive durante la configurazione del nodo Watcher. Prima di tutto, è necessario associare gli utenti di test al tipo di test PSTN eseguendo un comando simile al seguente da Skype for Business Server Management Shell:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> I risultati di questo comando devono essere archiviati in una variabile. In questo esempio la variabile è denominata $pstnTest. 
  
Successivamente, è possibile utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Skype for Business Server. Ad esempio, il comando seguente crea una nuova configurazione del nodo Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i due utenti di test creati in precedenza e aggiungendo il tipo di test PSTN:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Il comando precedente avrà esito negativo se non sono stati installati i file principali di Skype for Business Server e il database RTCLocal nel computer del nodo Watcher. 
  
Per testare più criteri vocali, è possibile creare un test esteso per ogni criterio utilizzando il cmdlet **New-CsExtendedTest.** Gli utenti forniti devono essere configurati con i criteri vocali desiderati. I test estesi vengono passati al cmdlet **New-CsWatcherNodeConfiguration** utilizzando delimitatori virgole, ad esempio:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Poiché il cmdlet **New-CsWatcherNodeConfiguration** è stato chiamato senza utilizzare il parametro Tests, solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) verranno abilitate per il nuovo nodo Watcher. Di conseguenza, il nodo Watcher testerà i componenti seguenti:
  
- Registrazione
    
- Messaggistica istantanea
    
- GroupIM
    
- P2PAV (Sessioni audio/video peer-to-peer)
    
- AvConference (Conferenze audio)
    
- Presenza
    
- ABS (Servizio Rubrica)
    
- ABWQ (Servizio Web Rubrica)
    
I componenti seguenti non verranno testati per impostazione predefinita:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Messaggistica unificata di Exchange)
    
- JoinLauncher
    
- MCXP2PIM (messaggistica istantanea di dispositivi mobili legacy)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (chiamate gateway PSTN, specificate come test esteso)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Aggiunta e rimozione di transazioni sintetiche

Dopo avere configurato un nodo Watcher, è possibile utilizzare il cmdlet Set-CsWatcherNodeConfiguration per aggiungere o rimuovere transazioni sintetiche dal nodo. Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, utilizzare il metodo Add e un comando simile al seguente:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

È possibile aggiungere più test separandone i nomi con le virgole. Ad esempio:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Se uno o più di questi test (ad esempio, DataConference) sono già stati abilitati nel nodo Watcher, si verificherà un errore. In questo caso verrà visualizzato un messaggio di errore simile al seguente:
  
Set-CsWatcherNodeConfiguration: esiste una sequenza di chiavi duplicata 'DataConference' per la chiave 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' o vincolo di identità univoco.
  
Quando si verifica questo errore, non vengono apportate modifiche. Il comando deve essere eseguito nuovamente con la rimozione del test duplicato.
  
Per rimuovere una transazione sintetica da un nodo Watcher, utilizzare il metodo Remove. Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

È possibile utilizzare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test. Ad esempio, se si desidera che un nodo Watcher esempli il test di messaggistica istantanea, è possibile configurarlo utilizzando questo comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Quando si esegue questo comando, tutte le transazioni sintetiche nel nodo Watcher specificato verranno disabilitate ad eccezione della messaggistica istantanea.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Visualizzazione e verifica della configurazione del nodo Watcher

Se si desidera visualizzare i test assegnati a un nodo Watcher, utilizzare un comando simile al seguente:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Questo comando restituirà informazioni simili alle seguenti, a seconda delle transazioni sintetiche assegnate al nodo:
  
Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Per visualizzare le transazioni sintetiche in ordine alfabetico, utilizzare invece il comando seguente: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Si otterrà informazioni simili alle seguenti:
  
Identity : atl-cs-001.litwareinc.com <br/>
TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}<br/>
TargetFqdn : atl-cs-001.litwareinc.com<br/>
PortNumber : 5061<br/>

Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Questo comando testerà ogni nodo Watcher della distribuzione e confermerà se sono state completate le azioni seguenti:
  
- È installato il ruolo di registrazione necessario.
    
- La chiave del Registro di sistema necessaria viene creata (completata quando è stato eseguito Set-CsWatcherNodeConfiguration cmdlet).
    
- I server eseguono la versione corretta di Skype for Business Server.
    
- Le porte sono configurate correttamente.
    
- Gli utenti di test assegnati dispongono delle credenziali necessarie.
    
## <a name="managing-watcher-nodes"></a>Gestione dei nodi Watcher
<a name="testuser"> </a>

Oltre a modificare le transazioni sintetiche eseguite in un nodo Watcher, è inoltre possibile utilizzare il cmdlet **Set-CsWatcherNodeConfiguration** per eseguire altre due attività importanti: l'abilitazione e la disabilitazione del nodo Watcher e la configurazione del nodo Watcher per l'utilizzo di URL Web interni o URL Web esterni durante l'esecuzione dei test.
  
Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate. In alcuni casi, tuttavia, potrebbe essere necessario sospendere tali transazioni. Se il nodo Watcher è temporaneamente disconnesso dalla rete, ad esempio, non vi è alcun motivo per eseguire le transazioni sintetiche. Senza connettività di rete, tali transazioni avranno esito negativo. Per disabilitare temporaneamente un nodo Watcher, eseguire un comando simile al seguente da Skype for Business Server Management Shell:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Questo comando disabiliterà l'esecuzione di transazioni sintetiche nel nodo Watcher atl watcher 001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, reimpostare la proprietà Enabled su True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> È possibile utilizzare la proprietà Enabled per attivare o disattivare i nodi Watcher. Per eliminare in modo definitivo un nodo Watcher, utilizzare il cmdlet **Remove-CsWatcherNodeConfiguration**:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Questo comando rimuove tutte le impostazioni di configurazione del nodo Watcher dal computer specificato, impedendo al computer di eseguire automaticamente transazioni sintetiche. Tuttavia, il comando non disinstalla i file dell'agente di System Center o i file di sistema di Skype for Business Server.
  
Per impostazione predefinita, i nodi Watcher utilizzano gli URL Web esterni di un'organizzazione durante l'esecuzione di test. Tuttavia, i nodi Watcher possono anche essere configurati per l'utilizzo degli URL Web interni dell'organizzazione. Ciò consente agli amministratori di verificare l'accesso agli URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'utilizzo di URL interni anziché esterni, impostare la proprietà UseInternalWebURls su True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Reimpostando questa proprietà sul valore predefinito False ($False), il watcher utilizzerà nuovamente gli URL esterni:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Istruzioni di configurazione speciali per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così come è. Nella maggior parte dei casi, non appena la transazione sintetica viene aggiunta alle impostazioni di configurazione del nodo Watcher, il nodo Watcher può iniziare a utilizzare tale transazione sintetica durante i test. Esistono tuttavia alcune transazioni sintetiche che richiedono istruzioni di configurazione speciali, come illustrato nelle sezioni seguenti.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transazione sintetica per conferenze dati

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, probabilmente non sarà possibile eseguire la transazione sintetica per conferenze dati, a meno che non si disattiveranno innanzitutto le impostazioni proxy del browser Internet di Windows Internet Explorer® per l'account Servizio di rete completando la procedura seguente:
  
1. Nel computer del nodo Watcher fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Accessori,** fare clic con il pulsante destro del mouse su **Prompt** dei comandi e quindi scegliere Esegui **come amministratore.**
    
2. Nella finestra della console digitare il comando seguente e quindi premere INVIO. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    Nella finestra di comando verrà visualizzato il messaggio seguente:

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    Questo messaggio indica che sono state disabilitate le impostazioni proxy di Internet Explorer per l'account Servizio di rete.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transazione sintetica di messaggistica unificata di Exchange

La transazione sintetica di messaggistica unificata di Exchange verifica che gli utenti di prova possano connettersi agli account della segreteria telefonica ospitati in Exchange.
  
Gli utenti di test dovranno essere preconfigurati con account della segreteria telefonica. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transazione sintetica di Chat persistente

Per utilizzare la transazione sintetica di Persistent Chat, è necessario innanzitutto creare un canale e concedere agli utenti di test le autorizzazioni per utilizzarlo.
  
È possibile utilizzare la transazione sintetica di Persistent Chat per configurare questo canale: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

È necessario eseguire questa attività di installazione dall'interno dell'organizzazione:
  
- Se eseguito da un computer non server, l'utente che esegue il cmdlet deve essere membro del ruolo CsPersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC, Access Control) di Role-Based.
    
- Se eseguito dal server stesso, l'utente che esegue il cmdlet deve essere membro del gruppo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transazione sintetica di chiamata peer-to-peer PSTN

La Test-CsPstnPeerToPeerCall sintetica verifica la capacità di effettuare e ricevere chiamate tramite una rete PSTN (Public Switched Telephone Network).
  
Per eseguire questa transazione sintetica, è necessario configurare:
  
- Due utenti di test abilitati per le comunicazioni unificate (un chiamante e un destinatario).
    
- Numeri DID (Direct Inward Dialing) per ogni account utente.
    
- Criteri VoIP e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.
    
- Gateway PSTN che accetta chiamate ed elementi multimediali che instraderanno le chiamate al pool principale di un destinatario, in base al numero composto.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transazione sintetica dell'archivio contatti unificato

La transazione sintetica dell'archivio contatti unificato verifica la capacità di Skype for Business Server di recuperare i contatti per conto di un utente da Exchange.
  
Per utilizzare questa transazione sintetica, devono essere soddisfatte le condizioni seguenti:
  
- Lyss-Exchange'autenticazione da server a server deve essere configurata.
    
- Gli utenti di prova devono disporre di una cassetta postale di Exchange valida.
    
Una volta soddisfatte queste condizioni, è possibile eseguire il cmdlet Windows PowerShell seguente per eseguire la migrazione degli elenchi contatti degli utenti di test a Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

La migrazione degli elenchi contatti degli utenti di prova a Exchange potrebbe richiedere del tempo. Per monitorare lo stato della migrazione, è possibile eseguire la stessa riga di comando senza il flag -Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Questa riga di comando avrà esito positivo al termine della migrazione.
  
### <a name="xmpp-synthetic-transaction"></a>Transazione sintetica XMPP

Per la transazione sintetica di messaggistica istantanea XMPP (Extensible Messaging and Presence Protocol) è necessario configurare la funzionalità XMPP con uno o più domini federati.
  
Per abilitare la transazione sintetica XMPP, è necessario fornire un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile. Ad esempio:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In questo esempio, una regola di Skype for Business Server dovrà esistere per instradare i messaggi per litwareinc.com a un gateway XMPP.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transazione sintetica Video Interop Server (VIS)

Per la transazione sintetica Video Interop Server (VIS) è necessario scaricare e installare i file di supporto delle transazioni sintetiche ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Per installare VISSTSupportPackage.msi verificare che le dipendenze (in Requisiti di sistema) per il file msi siano già installate. Eseguire VISSTSupportPackage.msi per eseguire un'installazione semplice. Il file MSI installa tutti i file nel percorso seguente: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Per ulteriori informazioni su come eseguire la transazione sintetica VIS, vedere la documentazione relativa al cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Modifica della frequenza di esecuzione per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

Per impostazione predefinita, le transazioni sintetiche verranno eseguite con gli utenti configurati ogni 15 minuti. Le transazioni sintetiche vengono eseguite in sequenza all'interno di un insieme di utenti per evitare che due transazioni sintetiche siano in conflitto tra loro. Per il completamento di tutte le transazioni sintetiche è necessario un intervallo più lungo.
  
Se è consigliabile eseguire transazioni sintetiche con maggiore frequenza, il numero di transazioni sintetiche eseguite con un determinato set di utenti deve essere ridotto in modo che i test possano essere completati nell'intervallo di tempo desiderato con un buffer per ritardi occasionali della rete. Se è consigliabile eseguire più transazioni sintetiche, creare più set di utenti per eseguire transazioni sintetiche aggiuntive.
  
Per modificare la frequenza di esecuzione delle transazioni sintetiche, eseguire la procedura seguente:
  
1. Aprire System Center Operations Manager. Fare clic sulla sezione Creazione e modifica. Fare clic sulla sezione Regole in Creazione e modifica.
    
2. Nella sezione Rules individuare la regola con il nome "Main Synthetic Transaction Runner Performance Collection Rule".
    
3. Fare clic con il pulsante destro del mouse sulla regola e selezionare Sostituzioni, selezionare Ignora regola, quindi selezionare "Per tutti gli oggetti della classe: Pool Watcher".
    
4. Nella finestra Proprietà sostituzione selezionare Nome parametro "Frequenza" e impostare il valore di sostituzione su quello desiderato.
    
5. Nella stessa finestra, selezionare il Management Pack a cui deve essere applicata la sostituzione.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Utilizzo della registrazione dettagliata per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

Le transazioni sintetiche si rivelano estremamente utili per identificare i problemi relativi al sistema. Ad esempio, il cmdlet Test-CsRegistration può avvisare gli amministratori del fatto che gli utenti hanno difficoltà a registrarsi con Skype for Business Server. Tuttavia, potrebbero essere necessari ulteriori dettagli per determinare la causa effettiva di un errore.
  
Per questo motivo, le transazioni sintetiche forniscono una registrazione completa. Con la registrazione completa, per ogni attività effettuata da una transazione sintetica vengono registrate le informazioni seguenti:
  
- Ora di inizio dell'attività.
    
- Ora di fine dell'attività.
    
- L'azione eseguita (ad esempio, la creazione, la partecipazione o l'uscita da una conferenza, l'accesso a Skype for Business Server; l'invio di un messaggio istantaneo).
    
- Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività.
    
- Messaggi di registrazione SIP.
    
- Record di eccezione o codici di diagnostica generati durante l'esecuzione dell'attività.
    
- Risultato netto dell'esecuzione dell'attività.
    
Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica, ma non vengono visualizzate o salvate automaticamente in un file di registro. Se si esegue manualmente una transazione sintetica, è possibile utilizzare il parametro OutLoggerVariable per specificare una variabile Windows PowerShell in cui verranno archiviate le informazioni. Da qui, è possibile utilizzare uno dei due metodi per salvare e/o visualizzare i messaggi di errore nel registro RTF in formato XML o HTML. 
  
Per recuperare le informazioni sulla risoluzione dei problemi, specificare il parametro OutLoggerVariable, seguito da un nome di variabile scelto:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Non anteporre il carattere $ al nome di variabile. Utilizzare un nome di variabile, ad esempio RegistrationTest (non $RegistrationTest). 
  
Quando si esegue questo comando, verrà visualizzato un output simile al seguente:
  
Fqdn destinazione : atl-cs-001.litwareinc.com : Latenza errore : 00:00:00 Messaggio di errore: questo computer non dispone di certificati assegnati. Diagnosi: è possibile accedere a informazioni molto più dettagliate per questo errore rispetto al solo messaggio di errore mostrato qui.

Per accedere a queste informazioni in formato HTML, utilizzare un comando simile al seguente per salvare le informazioni archiviate nella variabile RegistrationTest in un file HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

In alternativa, è possibile usare il metodo ToXML() per salvare i dati in un file XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Puoi visualizzare questi file usando Windows Internet Explorer, Microsoft Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.
  
Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager genereranno automaticamente questi file di registro per gli errori. Questi registri non verranno generati se l'esecuzione ha esito negativo prima che PowerShell di Skype for Business Server sia in grado di caricare ed eseguire la transazione sintetica. 
  
> [!IMPORTANT]
> Per impostazione predefinita, Skype for Business Server salva i file di registro in una cartella non condivisa. Per rendere questi registri facilmente accessibili, è necessario condividere questa cartella. Ad esempio: \\ atl-watcher-001.litwareinc.com\WatcherNode. 
