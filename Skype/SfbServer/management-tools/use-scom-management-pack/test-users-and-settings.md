---
title: Configurare gli utenti e le impostazioni di test del nodo Watcher
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: 877e7256c31bf5bf66f25e80c9625078cfc15b02
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888855"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurare gli utenti e le impostazioni di test del nodo Watcher
 
**Riepilogo:** Configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.
  
Dopo aver configurato il computer che fungerà da nodo Watcher, è necessario:
  
1. [Configurare gli account utente di test](test-users-and-settings.md#testuser) per l'utilizzo da questi nodi Watcher. Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet **Set-CsTestUserCredential** per abilitare questi account di test per l'uso nel nodo Watcher.
    
2. Aggiornare le impostazioni di configurazione dei nodi Watcher.
    
## <a name="configure-test-user-accounts"></a>Configurare gli account utente di test
<a name="testuser"> </a>

Gli account di test non devono rappresentare persone effettive, ma devono essere account di Active Directory validi. Inoltre, questi account devono essere abilitati per Skype for Business Server, devono avere indirizzi SIP validi e devono essere abilitati per Enterprise Voice (per usare la transazione sintetica Test-CsPstnPeerToPeerCall). 
  
Se usi il metodo di autenticazione TrustedServer, devi solo assicurarti che questi account esistano e configurarli come indicato. È consigliabile assegnare almeno due utenti di test per ogni pool che si vuole testare. Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet Set-CsTestUserCredential e Skype for Business Server Management Shell per consentire agli account di test di lavorare con le transazioni sintetiche. Eseguire questa operazione eseguendo un comando simile al seguente (questi comandi presuppongono che siano stati creati i due account utente di Active Directory e che questi account siano abilitati per Skype for Business Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

È necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password. Se non si include la password, il cmdlet Set-CsTestUserCredential chiederà di immettere le informazioni. Il nome utente può essere specificato usando il formato del nome del dominio profili\nome visualizzato nel blocco di codice precedente.
  
Per verificare che le credenziali dell'utente di test siano state create, eseguire questi comandi da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Le informazioni simili a queste verranno restituite per ogni utente:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurare un nodo Watcher di base con le transazioni sintetiche predefinite

Dopo aver creato gli utenti di test, è possibile creare un nodo Watcher usando un comando simile al seguente:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Questo comando crea un nuovo nodo Watcher che usa le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche. Il nuovo nodo Watcher usa anche gli utenti di test watcher1@litwareinc.com e watcher2@litwareinc.com. Se il nodo Watcher usa l'autenticazione TrustedServer, i due account di test possono essere tutti gli account utente validi abilitati per Active Directory e Skype for Business Server. Se il nodo Watcher usa il metodo di autenticazione Negotiate, questi account utente devono essere abilitati anche per il nodo Watcher usando il cmdlet Set-CsTestUserCredential.
  
Per verificare che l'individuazione automatica del pool di destinazione per l'accesso sia configurata correttamente invece che come destinazione di un pool, usare direttamente questi passaggi:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurazione di test estesi

Se si vuole abilitare il test PSTN, che verifica la connettività con la rete telefonica pubblica commutata, è necessario eseguire altre configurazioni quando si configura il nodo Watcher. Prima di tutto, devi associare gli utenti di test al tipo di test PSTN eseguendo un comando simile a quello di Skype for Business Server Management Shell:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> I risultati di questo comando devono essere archiviati in una variabile. In questo esempio la variabile è denominata $pstnTest. 
  
Puoi quindi usare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Skype for Business Server. Ad esempio, il comando seguente crea una nuova configurazione del nodo Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i due utenti di test creati in precedenza e aggiungendo il tipo di test PSTN:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Il comando precedente non riesce se non sono stati installati i file principali di Skype for Business Server e il database di RTCLocal nel computer del nodo Watcher. 
  
Per testare più criteri vocali, è possibile creare un test esteso per ogni criterio usando il cmdlet **New-CsExtendedTest** . Gli utenti forniti devono essere configurati con i criteri vocali desiderati. I test estesi vengono passati al cmdlet **New-CsWatcherNodeConfiguration** usando i delimitatori virgola, ad esempio:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Poiché il cmdlet **New-CsWatcherNodeConfiguration** è stato chiamato senza usare il parametro tests, verranno abilitate solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) per il nuovo nodo Watcher. Di conseguenza, il nodo Watcher testerà i componenti seguenti:
  
- Registrazione
    
- Messaggistica istantanea
    
- GroupIM
    
- P2PAV (sessioni audio/video peer-to-peer)
    
- AvConference (audio/servizi di conferenza)
    
- Icone di presenza
    
- ABS (servizio Rubrica)
    
- ABWQ (servizio Web Rubrica)
    
I componenti seguenti non verranno testati per impostazione predefinita:
  
- ASConference
    
- AVEdgeConnectivity
    
- Dataconference
    
- DialinConferencing
    
- ExumConnectivity (messaggistica unificata di Exchange)
    
- JoinLauncher
    
- MCXP2PIM (dispositivo mobile legacy Instant Messaging)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (chiamate gateway PSTN, specificate come test esteso)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Aggiunta e rimozione di transazioni sintetiche

Dopo aver configurato un nodo Watcher, è possibile usare il cmdlet Set-CsWatcherNodeConfiguration per aggiungere o rimuovere transazioni sintetiche dal nodo. Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, usa il metodo Add e un comando simile al seguente:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

È possibile aggiungere più test separando i nomi dei test usando le virgole. Ad esempio:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Si verificherà un errore se uno o più di questi test, ad esempio dataconference, sono già stati abilitati nel nodo Watcher. In questo caso, viene visualizzato un messaggio di errore simile al seguente:
  
Set-CsWatcherNodeConfiguration: è presente una sequenza di tasti duplicata "dataconference" per la chiave "urn: schema: Microsoft. Rtc. Management. Settings. WatcherNode. 2010: TestName" o un vincolo di identità univoco.
  
Quando si verifica questo errore, non verrà applicata alcuna modifica. Il comando deve essere eseguito di nuovo con il test duplicato rimosso.
  
Per rimuovere una transazione sintetica da un nodo Watcher, usa il metodo Remove. Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Puoi usare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test. Ad esempio, se si vuole che un nodo Watcher esegua solo il test di messaggistica istantanea, è possibile configurarlo usando questo comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Quando si esegue questo comando, tutte le transazioni sintetiche nel nodo Watcher specificato verranno disabilitate ad eccezione di messaggistica istantanea.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Visualizzazione e test della configurazione dei nodi Watcher

Se si vogliono visualizzare i test assegnati a un nodo Watcher, usare un comando simile al seguente:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Questo comando restituirà informazioni simili a queste, a seconda delle transazioni sintetiche assegnate al nodo:
  
Registrazione IM GroupIM P2PAV AvConference presenza PersistentChatMessage dataconference
> [!TIP]
> Per visualizzare le transazioni sintetiche in ordine alfabetico, USA invece questo comando: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Le informazioni verranno restituite in modo simile al seguente:
  
Identità: atl-cs-001.litwareinc.com <br/>
TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}<br/>
ExtendedTests: {TestUsers = IList<System. String>; Name = test PSTN; Te...}<br/>
TargetFqdn: atl-cs-001.litwareinc.com<br/>
NumeroPorta: 5061<br/>

Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Questo comando testerà ogni nodo Watcher nella distribuzione e confermerà se sono state completate le azioni seguenti:
  
- Il ruolo di registrar richiesto è installato.
    
- Viene creata la chiave del registro di sistema necessaria (completata quando è stato eseguito il cmdlet Set-CsWatcherNodeConfiguration).
    
- I server stanno usando la versione corretta di Skype for Business Server.
    
- Le porte sono configurate correttamente.
    
- Gli utenti di test assegnati hanno le credenziali necessarie.
    
## <a name="managing-watcher-nodes"></a>Gestione dei nodi Watcher
<a name="testuser"> </a>

Oltre a modificare le transazioni sintetiche eseguite in un nodo Watcher, puoi anche usare il cmdlet **set-CsWatcherNodeConfiguration** per eseguire due altre attività importanti: abilitare e disabilitare il nodo Watcher e configurare il nodo Watcher per usare URL Web interni o URL Web esterni durante l'esecuzione dei test.
  
Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate. A volte, tuttavia, potresti voler sospendere tali transazioni. Ad esempio, se il nodo Watcher è temporaneamente disconnesso dalla rete, non c'è alcun motivo per eseguire le transazioni sintetiche. Senza connettività di rete, le transazioni non riusciranno. Per disabilitare temporaneamente un nodo Watcher, eseguire un comando simile a questo da Skype for Business Server Management Shell:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Questo comando consente di disabilitare l'esecuzione di transazioni sintetiche nel nodo Watcher watcher 001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, impostare di nuovo la proprietà Enabled su true ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La proprietà Enabled può essere usata per attivare o disattivare i nodi Watcher. Se si vuole eliminare definitivamente un nodo Watcher, usare il cmdlet **Remove-CsWatcherNodeConfiguration** :
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Questo comando rimuove tutte le impostazioni di configurazione del nodo Watcher dal computer specificato, impedendo che il computer esegua automaticamente le transazioni sintetiche. Tuttavia, il comando non disinstalla i file dell'agente del centro di sistema o i file di sistema di Skype for Business Server.
  
Per impostazione predefinita, i nodi Watcher usano gli URL Web esterni di un'organizzazione durante l'esecuzione di test. Tuttavia, i nodi Watcher possono essere configurati anche per l'uso degli URL Web interni dell'organizzazione. Ciò consente agli amministratori di verificare l'accesso URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'uso di URL interni anziché di URL esterni, imposta la proprietà UseInternalWebURls su true ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

La reimpostazione di questa proprietà sul valore predefinito false ($False) farà sì che il Watcher usi ancora una volta gli URL esterni:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Istruzioni per la configurazione speciale per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così com'è. Nella maggior parte dei casi, non appena viene aggiunta la transazione sintetica alle impostazioni di configurazione dei nodi Watcher, il nodo Watcher può iniziare a usare tale transazione sintetica durante le sessioni di test. Esistono tuttavia alcune transazioni sintetiche che richiedono istruzioni di configurazione speciali, come descritto nelle sezioni seguenti.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transazione sintetica per i servizi di conferenza dati

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, probabilmente non sarà possibile eseguire la transazione sintetica per i servizi di conferenza dati a meno che non si disattivi prima di tutto Windows Internet Explorer® impostazioni proxy del browser Internet per la rete Account del servizio completando la procedura seguente:
  
1. Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.
    
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
      
    Questo messaggio indica che sono state disabilitate le impostazioni proxy di Internet Explorer per l'account del servizio di rete.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transazione sintetica di messaggistica unificata di Exchange

La transazione sintetica della messaggistica unificata di Exchange verifica che gli utenti di test possano connettersi agli account della segreteria telefonica in Exchange.
  
Gli utenti di test dovranno essere preconfigurati con gli account della segreteria telefonica. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transazione sintetica della chat persistente

Per usare la transazione sintetica della chat persistente, è necessario prima di tutto creare un canale e concedere agli utenti di test le autorizzazioni per usarlo.
  
È possibile usare la transazione sintetica della chat persistente per configurare questo canale: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

È necessario eseguire questa attività di configurazione deve essere eseguita dall'interno dell'organizzazione:
  
- Se eseguito da un computer non server, l'utente che esegue il cmdlet deve essere un membro del ruolo CsPersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC).
    
- Se eseguito dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transazione sintetica chiamata peer-to-peer PSTN

La transazione sintetica Test-CsPstnPeerToPeerCall verifica la possibilità di effettuare e ricevere chiamate tramite una rete PSTN (Public Switched Telephone Network).
  
Per eseguire questa transazione sintetica, è necessario configurare:
  
- Due utenti di test abilitati per UC (un chiamante e un ricevitore).
    
- Numeri DID (Direct inwarding Dialing) per ogni account utente.
    
- Criteri VoIP e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.
    
- Un gateway PSTN che accetta chiamate e elementi multimediali che instradano le chiamate al pool Home di un destinatario, in base al numero composto.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transazione sintetica archivio contatti unificato

La transazione sintetica archivio contatti unificato verifica la possibilità di Skype for Business Server di recuperare i contatti per conto di un utente da Exchange.
  
Per usare questa transazione sintetica, è necessario che siano soddisfatte le condizioni seguenti:
  
- Lyss-Exchange Server to Server Authentication deve essere configurato.
    
- Test gli utenti devono avere una cassetta postale di Exchange valida.
    
Una volta soddisfatte queste condizioni, è possibile eseguire il cmdlet di Windows PowerShell seguente per eseguire la migrazione degli elenchi di contatti degli utenti di test a Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Potrebbe essere necessario un po' di tempo prima che gli elenchi di contatti degli utenti di test vengano migrati in Exchange. Per monitorare lo stato di avanzamento della migrazione, è possibile eseguire la stessa riga di comando senza il flag-Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Questa riga di comando avrà esito positivo dopo il completamento della migrazione.
  
### <a name="xmpp-synthetic-transaction"></a>Transazione sintetica XMPP

La transazione sintetica di messaggistica istantanea (XMPP) Extensible Messaging and Presence richiede la configurazione della funzionalità XMPP con uno o più domini federati.
  
Per abilitare la transazione sintetica XMPP, devi specificare un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile. Ad esempio:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In questo esempio, è necessario che sia presente una regola di Skype for Business Server per instradare i messaggi per litwareinc.com a un gateway XMPP.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transazione sintetica video Interop Server (VIS)

La transazione sintetica video Interop Server (VIS) richiede il download e l'installazione dei file di supporto delle transazioni sintetiche ([VISSTSupportPackage. msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)). 
  
Per installare VISSTSupportPackage. msi, verificare che le dipendenze (in requisiti di sistema) per MSI siano già installate. Eseguire VISSTSupportPackage. msi per eseguire un'installazione semplice. Msi installa tutti i file nel percorso seguente: "pacchetto di supporto per le transazioni sintetiche%ProgramFiles%\VIS".
  
Per altre informazioni su come eseguire la transazione sintetica di VIS, vedere la documentazione relativa al cmdlet [test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Modifica della frequenza di esecuzione per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

Per impostazione predefinita, le transazioni sintetiche verranno eseguite con gli utenti configurati ogni 15 minuti. Le transazioni sintetiche vengono eseguite sequenzialmente all'interno di un set di utenti per evitare che due transazioni sintetiche siano in conflitto tra loro. Un intervallo più lungo è necessario per consentire il completamento di tutte le transazioni sintetiche.
  
Se è consigliabile eseguire più di frequente le transazioni sintetiche, il numero di transazioni sintetiche eseguito con un determinato set di utenti dovrebbe essere ridotto in modo che i test possano essere completati nell'intervallo di tempo desiderato con alcuni buffer per i ritardi di rete occasionali. Se è consigliabile eseguire più transazioni sintetiche, creare più set di utenti per eseguire altre transazioni sintetiche.
  
Per modificare la frequenza con cui vengono eseguite le transazioni sintetiche, eseguire le operazioni seguenti:
  
1. Aprire System Center Operations Manager. Fare clic su sezione Creazione. Fare clic su sezione regole (in creazione).
    
2. Nella sezione regole individuare la regola con il nome "regola di raccolta delle prestazioni di base delle transazioni sintetiche principali".
    
3. Fare clic con il pulsante destro del mouse sulla regola e selezionare sostituzioni, selezionare Sostituisci la regola e quindi selezionare "per tutti gli oggetti della classe: Watcher del pool".
    
4. Nella finestra Proprietà override selezionare Nome parametro "frequenza" e impostare il valore di override su quello desiderato.
    
5. Nella stessa finestra selezionare il Management Pack a cui deve essere applicato questo override.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Uso della registrazione avanzata per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

Le transazioni sintetiche risultano estremamente utili per identificare i problemi con il sistema. Ad esempio, il cmdlet Test-CsRegistration potrebbe avvisare gli amministratori del fatto che gli utenti avevano difficoltà a registrarsi con Skype for Business Server. Tuttavia, potrebbero essere necessari dettagli aggiuntivi per determinare la causa effettiva di un errore.
  
Per questo motivo, le transazioni sintetiche garantiscono una registrazione avanzata. Con la registrazione avanzata, per ogni attività eseguita da una transazione sintetica, vengono registrate le informazioni seguenti:
  
- L'ora in cui è stata avviata l'attività.
    
- L'ora di completamento dell'attività.
    
- Azione eseguita (ad esempio, creazione, partecipazione o uscita da una conferenza; accesso a Skype for Business Server; invio di un messaggio istantaneo).
    
- Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività.
    
- Messaggi di registrazione SIP.
    
- Record di eccezioni o codici di diagnostica generati durante l'esecuzione dell'attività.
    
- Il risultato risultante dall'eseguire l'attività.
    
Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica, ma non vengono visualizzate o salvate automaticamente in un file di log. Se si esegue manualmente una transazione sintetica, è possibile usare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni. Da qui è possibile usare uno dei due metodi per salvare e/o visualizzare i messaggi di errore nel log RTF in formato XML o HTML. 
  
Per recuperare le informazioni sulla risoluzione dei problemi, specificare il parametro OutLoggerVariable, seguito da un nome di variabile scelto:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Non precedere il nome della variabile con il carattere $. Usare un nome di variabile, ad esempio RegistrationTest (non $RegistrationTest). 
  
Quando si esegue questo comando, viene visualizzato l'output simile al seguente:
  
FQDN di destinazione: atl-cs-001.litwareinc.com risultato: latenza errore: messaggio di errore 00:00:00: il computer in cui non sono presenti certificati assegnati. Diagnosi: è possibile accedere a informazioni molto più dettagliate per questo errore che non solo il messaggio di errore visualizzato qui.

Per accedere a queste informazioni in formato HTML, usare un comando simile a quello per salvare le informazioni archiviate nella variabile RegistrationTest in un file HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

In alternativa, puoi usare il metodo ToXML () per salvare i dati in un file XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Puoi visualizzare questi file usando Windows Internet Explorer, Microsoft Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.
  
Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager generano automaticamente questi file di log per gli errori. Questi registri non verranno generati se l'esecuzione non riesce prima che Skype for Business Server PowerShell sia in grado di caricare ed eseguire la transazione sintetica. 
  
> [!IMPORTANT]
> Per impostazione predefinita, Skype for Business Server Salva i file di log in una cartella non condivisa. Per rendere questi registri facilmente accessibili, è consigliabile condividere questa cartella. Ad esempio: \\ATL-watcher-001. litwareinc. com\WatcherNode. 
