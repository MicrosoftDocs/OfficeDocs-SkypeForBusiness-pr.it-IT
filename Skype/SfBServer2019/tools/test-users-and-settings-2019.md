---
title: Configurare gli utenti e le impostazioni per il test del nodo Watcher
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: f13680d16a248be339ee7cd4a085d7d0894146dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033675"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurare gli utenti e le impostazioni per il test del nodo Watcher
 
**Riepilogo:** Configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.
  
Dopo avere configurato il computer che fungerà da nodo Watcher, è necessario eseguire le operazioni seguenti:
  
1. [Configurare gli account utente di test](test-users-and-settings-2019.md#testuser) per l'utilizzo da parte di questi nodi Watcher. Se si utilizza il metodo di autenticazione Negotiate, è inoltre necessario utilizzare il cmdlet **Set-CsTestUserCredential** per abilitare questi account di test per l'utilizzo nel nodo Watcher.
    
2. Aggiornare le impostazioni di configurazione del nodo Watcher.
    
## <a name="configure-test-user-accounts"></a>Configurare gli account utente di test
<a name="testuser"> </a>

Gli account di test non devono rappresentare persone effettive, ma devono essere account di Active Directory validi. Inoltre, questi account devono essere abilitati per Skype for Business Server, devono disporre di indirizzi SIP validi e devono essere abilitati per VoIP aziendale (per utilizzare la transazione sintetica Test-CsPstnPeerToPeerCall). 
  
Se si utilizza il metodo di autenticazione TrustedServer, è necessario fare in modo che questi account esistano e configurarli come indicato. È consigliabile assegnare almeno tre utenti di test per ogni pool che si desidera testare. Se si utilizza il metodo di autenticazione Negotiate, è necessario utilizzare anche il cmdlet Set-CsTestUserCredential e Skype for Business Server Management Shell per consentire l'utilizzo di tali account con le transazioni sintetiche. A tale scopo, eseguire un comando simile al seguente (questi comandi presumono che siano stati creati i tre account utente di Active Directory e che questi account siano abilitati per Skype for Business Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

È necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password. Se non si include la password, il cmdlet Set-CsTestUserCredential richiederà di immettere tali informazioni. Il nome utente può essere specificato utilizzando il formato del nome di dominio profili\nome visualizzato nel blocco di codice precedente.
  
Per verificare che le credenziali dell'utente di test siano state create, eseguire questi comandi da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Per ogni utente verranno restituite informazioni simili a quelle seguenti:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurare un nodo Watcher di base con le transazioni sintetiche predefinite

Dopo aver creato gli utenti di test, è possibile creare un nodo Watcher utilizzando un comando simile al seguente:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Questo comando crea un nuovo nodo Watcher che utilizza le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche. Il nuovo nodo Watcher inoltre utilizza gli utenti di test watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com. Se il nodo Watcher utilizza l'autenticazione di TrustedServer, i tre account di test possono essere tutti gli account utente validi abilitati per Active Directory e Skype for Business Server. Se il nodo Watcher utilizza il metodo di autenticazione Negotiate, questi account utente devono essere abilitati anche per il nodo Watcher utilizzando il cmdlet Set-CsTestUserCredential.
  
Per convalidare che l'individuazione automatica del pool di destinazione per l'accesso è configurata correttamente anziché indirizzare un pool direttamente, utilizzare invece questi passaggi:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurazione dei test estesi

Se si desidera abilitare il test PSTN, che verifica la connettività con la rete telefonica pubblica commutata, è necessario eseguire una configurazione aggiuntiva quando si configura il nodo Watcher. Per prima cosa, è necessario associare gli utenti di test al tipo di test PSTN eseguendo un comando simile a questo da Skype for Business Server Management Shell:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> I risultati di questo comando devono essere archiviati in una variabile. In questo esempio, la variabile è denominata $pstnTest. 
  
Successivamente, è possibile utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (memorizzato nella variabile $pstnTest) a un pool di Skype for Business Server. Ad esempio, il comando seguente crea una nuova configurazione del nodo Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i tre utenti di test creati in precedenza e aggiungendo il tipo di test PSTN:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Il comando precedente avrà esito negativo se non sono stati installati i file principali di Skype for Business Server e il database di RTCLocal nel computer del nodo Watcher. 
  
Per testare più criteri vocali, è possibile creare un test esteso per ogni criterio utilizzando il cmdlet **New-CsExtendedTest** . Gli utenti forniti devono essere configurati con i criteri vocali desiderati. I test estesi vengono passati al cmdlet **New-CsWatcherNodeConfiguration** utilizzando delimitatori virgola, ad esempio:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Poiché il cmdlet **New-CsWatcherNodeConfiguration** è stato chiamato senza utilizzare il parametro tests, verranno abilitate solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) per il nuovo nodo Watcher. Di conseguenza, il nodo Watcher verificherà i componenti seguenti:
  
- Registrazione
    
- IM
    
- GroupIM
    
- P2PAV (Sessioni audio/video peer-to-peer)
    
- AvConference (Conferenze audio)
    
- Presenza
    
- ABS (Servizio Rubrica)
    
- ABWQ (Servizio Web Rubrica)
    
Per impostazione predefinita, i componenti seguenti non verranno testati:
  
- ASConference
    
- AVEdgeConnectivity
    
- Dataconference
    
- DialinConferencing
    
- ExumConnectivity (Messaggistica unificata di Exchange)
    
- JoinLauncher
    
- MCXP2PIM (messaggistica istantanea del dispositivo mobile legacy)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (chiamate del gateway PSTN, specificate come test esteso)
    
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

Si verificherà un errore se uno o più di questi test (ad esempio, dataconference) sono già stati abilitati nel nodo Watcher. In questo caso verrà visualizzato un messaggio di errore simile al seguente:
  
Set-CsWatcherNodeConfiguration: è presente una sequenza di tasti ' dataconference ' duplicata per il vincolo ' urn: schema: Microsoft. Rtc. Management. Settings. WatcherNode. 2010: TestName ' o l'identità univoca.
  
Quando si verifica questo errore, non vengono apportate modifiche. Il comando deve essere eseguito di nuovo con il test duplicato rimosso.
  
Per rimuovere una transazione sintetica da un nodo Watcher, utilizzare il metodo Remove. Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

È possibile utilizzare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test. Ad esempio, se si desidera che un nodo Watcher esegua solo il test di messaggistica istantanea, è possibile configurarlo utilizzando il comando seguente:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Quando si esegue questo comando, tutte le transazioni sintetiche sul nodo Watcher specificato verranno disabilitate tranne che per la messaggistica istantanea.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Visualizzazione e verifica della configurazione del nodo Watcher

Se si desidera visualizzare i test assegnati a un nodo Watcher, utilizzare un comando simile al seguente:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Questo comando restituirà informazioni simili a quelle, a seconda delle transazioni sintetiche che sono state assegnate al nodo:
  
Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage dataconference
> [!TIP]
> Per visualizzare le transazioni sintetiche in ordine alfabetico, utilizzare invece il comando seguente: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Verranno restituite informazioni simili alle seguenti:
  
Identity: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...} ExtendedTests: {TestUsers = IList<System. String>; Name = test PSTN; Te...} TargetFqdn: atl-cs-001.litwareinc.com NumeroPorta: 5061To verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Questo comando consente di testare ogni nodo Watcher nella distribuzione e di verificare se sono state completate le azioni seguenti:
  
- Il ruolo di registrazione obbligatorio è installato
    
- La chiave del registro di sistema necessaria viene creata (completata quando è stato eseguito il cmdlet Set-CsWatcherNodeConfiguration)
    
- I server eseguono la versione corretta di Skype for Business Server
    
- Le porte sono configurate correttamente
    
- Gli utenti di test assegnati dispongono delle credenziali necessarie
    
## <a name="managing-watcher-nodes"></a>Gestione dei nodi Watcher
<a name="testuser"> </a>

Oltre a modificare le transazioni sintetiche eseguite su un nodo Watcher, è anche possibile utilizzare il cmdlet **set-CsWatcherNodeConfiguration** per eseguire altre due attività importanti: abilitazione e disabilitazione del nodo Watcher e configurazione del nodo Watcher per l'utilizzo di URL Web interni o URL Web esterni durante l'esecuzione dei test.
  
Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate. A volte, tuttavia, potrebbe essere necessario sospendere tali transazioni. Se il nodo Watcher è temporaneamente disconnesso dalla rete, ad esempio, non vi è alcun motivo per eseguire le transazioni sintetiche. Senza la connettività di rete, tali transazioni avranno esito negativo. Per disabilitare temporaneamente un nodo Watcher, eseguire un comando simile a questo da Skype for Business Server Management Shell:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Questo comando consente di disabilitare l'esecuzione delle transazioni sintetiche sul nodo Watcher ATL watcher 001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, reimpostare la proprietà Enabled su True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> È possibile utilizzare la proprietà Enabled per attivare o disattivare i nodi Watcher. Per eliminare in modo definitivo un nodo Watcher, utilizzare il cmdlet **Remove-CsWatcherNodeConfiguration**:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Questo comando rimuove tutte le impostazioni di configurazione del nodo Watcher dal computer specificato, in modo da evitare che il computer esegua automaticamente transazioni sintetiche. Tuttavia, il comando non disinstalla i file dell'agente centrale di sistema o i file di sistema di Skype for Business Server.
  
Per impostazione predefinita, i nodi Watcher utilizzano gli URL Web esterni di un'organizzazione durante la gestione dei test. Tuttavia, i nodi Watcher possono anche essere configurati per l'utilizzo degli URL Web interni dell'organizzazione. Ciò consente agli amministratori di verificare l'accesso agli URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'utilizzo di URL interni anziché di URL esterni, impostare la proprietà UseInternalWebURls su true ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

La reimpostazione di questa proprietà sul valore predefinito false ($False) provocherà nuovamente l'utilizzo degli URL esterni da parte di Watcher:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Istruzioni di configurazione speciali per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così com'è. Nella maggior parte dei casi, non appena viene aggiunta la transazione sintetica alle impostazioni di configurazione del nodo Watcher, il nodo Watcher può iniziare a utilizzare tale transazione sintetica durante le sessioni di test. Tuttavia, esistono alcune transazioni sintetiche che richiedono istruzioni di installazione speciali, come descritto nelle sezioni seguenti.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transazioni sintetiche di conferenza dati

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è probabile che non sia possibile eseguire la transazione sintetica di conferenza dati a meno che non sia stata disabilitata per la prima volta le impostazioni del proxy del browser Internet di Windows Internet® Explorer per la rete. Account del servizio completando i passaggi seguenti:
  
1. Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.
    
2. Nella finestra della console digitare il comando seguente e quindi premere INVIO. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Nella finestra di comando verrà visualizzato il messaggio seguente:
  
BITSAdmin è obsoleto e non è garantito che sia disponibile nelle versioni future di Windows. Gli strumenti di amministrazione per il servizio BITS sono ora forniti dai cmdlet di PowerShell BITS.
  
Impostazioni proxy Internet per l'account NetworkService impostato su NO_PROXY. 
  
(Connection = default)
  
Questo messaggio indica che sono state disabilitate le impostazioni del proxy di Internet Explorer per l'account di servizio di rete.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transazione sintetica di messaggistica unificata di Exchange

La transazione sintetica di messaggistica unificata di Exchange verifica che gli utenti di test siano in grado di connettersi agli account della segreteria telefonica ospitati in Exchange.
  
Gli utenti di test dovranno essere preconfigurati con gli account della segreteria telefonica. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transazioni sintetiche di chat persistente

Per utilizzare la transazione sintetica per la chat persistente, è necessario innanzitutto creare un canale e fornire le autorizzazioni agli utenti di test per utilizzarlo.
  
È possibile utilizzare la transazione sintetica Persistent Chat per configurare questo canale: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

È necessario eseguire questa operazione di installazione deve essere eseguita dall'interno dell'organizzazione:
  
- Se si esegue da un computer non server, l'utente che esegue il cmdlet deve essere un membro del ruolo CsPersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC).
    
- Se viene eseguito dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transazione sintetica delle chiamate peer-to-peer PSTN

La transazione sintetica Test-CsPstnPeerToPeerCall verifica la possibilità di effettuare e ricevere chiamate tramite una rete PSTN (Public Switched Telephone Network).
  
Per eseguire questa transazione sintetica, è necessario configurare:
  
- Due utenti di test abilitati per le comunicazioni unificate (un chiamante e un destinatario).
    
- Numeri DID (Direct Inward Dialing) per ogni account utente.
    
- Criteri VoIP e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.
    
- Un gateway PSTN che accetta la chiamata e il supporto che instraderà le chiamate al pool di casa del destinatario, in base al numero composto.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transazioni sintetiche dell'archivio contatti unificato

La transazione sintetica archivio contatti unificato verifica la capacità di Skype for Business Server di recuperare i contatti per conto di un utente da Exchange.
  
Per utilizzare questa transazione sintetica, devono essere soddisfatte le condizioni seguenti:
  
- È necessario configurare l'autenticazione di Lyss-Exchange Server to server.
    
- Gli utenti di test devono disporre di una cassetta postale di Exchange valida.
    
Dopo aver soddisfatto queste condizioni, è possibile eseguire il seguente cmdlet di Windows PowerShell per eseguire la migrazione degli elenchi di contatti degli utenti di test a Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Potrebbe essere necessario un po' di tempo prima che gli elenchi dei contatti degli utenti di test vengano migrati in Exchange. Per monitorare lo stato di avanzamento della migrazione, è possibile eseguire la stessa riga di comando senza il flag-Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Questa riga di comando avrà esito positivo dopo il completamento della migrazione.
  
### <a name="xmpp-synthetic-transaction"></a>Transazione sintetica XMPP

La transazione sintetica per la messaggistica istantanea con protocollo XMPP (Extensible Messaging and Presence Protocol) richiede che la caratteristica XMPP venga configurata con uno o più domini federati.
  
Per abilitare la transazione sintetica XMPP, è necessario fornire un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile. Ad esempio:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In questo esempio, deve esistere una regola di Skype for Business Server per instradare i messaggi per litwareinc.com a un gateway XMPP.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../migration/migrating-xmpp-federation.md) .
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transazione sintetica video Interop Server (VIS)

La transazione sintetica video Interop Server (VIS) richiede il download e l'installazione dei file di supporto per le transazioni sintetiche ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Per installare VISSTSupportPackage. msi, verificare che le dipendenze (in requisiti di sistema) per il MSI siano già installate. Eseguire VISSTSupportPackage. msi per eseguire un'installazione semplice. Con estensione msi vengono installati tutti i file nel percorso seguente: "pacchetto di supporto per le transazioni sintetiche di%ProgramFiles%\VIS".
  
Per ulteriori informazioni su come eseguire la transazione sintetica VIS, fare riferimento alla documentazione relativa al cmdlet [test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Modifica della frequenza di esecuzione per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

Per impostazione predefinita, le transazioni sintetiche verranno eseguite con gli utenti configurati ogni 15 minuti. Le transazioni sintetiche vengono eseguite sequenzialmente all'interno di un set di utenti per evitare che due transazioni sintetiche entrino in conflitto tra loro. Un intervallo più lungo è necessario per garantire il completamento di tutte le transazioni sintetiche.
  
Se si desidera eseguire più frequentemente transazioni sintetiche, è necessario ridurre il numero di transazioni sintetiche eseguite con un determinato gruppo di utenti, in modo che i test possano essere completati nell'intervallo di tempo desiderato con alcuni buffer per i ritardi di rete occasionali. Se è consigliabile eseguire più transazioni sintetiche, creare più set di utenti per l'esecuzione di ulteriori transazioni sintetiche.
  
Per modificare la frequenza di esecuzione delle transazioni sintetiche, eseguire la procedura seguente:
  
1. Aprire System Center Operations Manager. Fare clic su sezione Creazione e modifica. Fare clic su regole sezione (in creazione e modifica)
    
2. Nella sezione regole individuare la regola con il nome "regola di raccolta delle prestazioni del Runner di transazione sintetica principale"
    
3. Fare clic con il pulsante destro del mouse sulla regola e selezionare sostituzioni, selezionare Sostituisci la regola e quindi selezionare "per tutti gli oggetti della classe: pool Watcher"
    
4. Nella finestra proprietà di sostituzione selezionare il nome del parametro "Frequency" e impostare il valore di sostituzione su quello desiderato.
    
5. Nella stessa finestra selezionare il Management Pack a cui deve essere applicata la sostituzione.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Utilizzo della registrazione dettagliata per le transazioni sintetiche
<a name="special_synthetictrans"> </a>

Le transazioni sintetiche risultano estremamente utili per identificare i problemi del sistema. Ad esempio, il cmdlet Test-CsRegistration può avvisare gli amministratori del fatto che gli utenti hanno avuto difficoltà a registrarsi con Skype for Business Server. Tuttavia, potrebbero essere necessari ulteriori dettagli per determinare la causa effettiva di un errore.
  
Per questo motivo, le transazioni sintetiche offrono una registrazione avanzata. Con una registrazione completa, per ogni attività eseguita da una transazione sintetica, vengono registrate le informazioni seguenti:
  
- L'ora di inizio dell'attività.
    
- Data e ora di fine dell'attività.
    
- Azione eseguita, ad esempio la creazione, l'aggiunta o l'uscita di una conferenza, l'accesso a Skype for Business Server, l'invio di un messaggio istantaneo.
    
- Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività
    
- Messaggi di registrazione SIP.
    
- Record di eccezioni o codici diagnostici generati durante l'esecuzione dell'attività.
    
- Risultato netto dell'esecuzione dell'attività.
    
Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica, ma non vengono visualizzate o salvate automaticamente in un file di registro. Se si esegue manualmente una transazione sintetica, è possibile utilizzare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni. Da qui, è possibile utilizzare uno dei due metodi per salvare e/o visualizzare i messaggi di errore nel log RTF in formato XML o HTML. 
  
Per recuperare le informazioni sulla risoluzione dei problemi, specificare il parametro OutLoggerVariable, seguito da un nome di variabile che si sceglie:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : Non anteporre il nome della variabile al carattere $. Utilizzare un nome di variabile, ad esempio RegistrationTest (non $RegistrationTest). 
  
Quando si esegue questo comando, viene visualizzato un output simile al seguente:
  
FQDN di destinazione: atl-cs-001.litwareinc.com result: latenza errore: 00:00:00 messaggio di errore: questo computer non dispone di alcun certificato assegnato. Diagnosi: è possibile accedere a informazioni molto più dettagliate per questo errore rispetto al messaggio di errore riportato di seguito. Per accedere a queste informazioni in formato HTML, utilizzare un comando simile al seguente per salvare le informazioni archiviate nella variabile RegistrationTest in un file HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

In alternativa, è possibile usare il metodo ToXML() per salvare i dati in un file XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

È possibile visualizzare questi file utilizzando Windows Internet Explorer, Microsoft Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.
  
Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager genereranno automaticamente questi file di registro per gli errori. Questi registri non verranno generati se l'esecuzione ha esito negativo prima che Skype for Business Server PowerShell sia in grado di caricare ed eseguire la transazione sintetica. 
  
> [!IMPORTANT]
> Per impostazione predefinita, in Skype for Business Server i file di registro vengono salvati in una cartella non condivisa. Per rendere tali registri facilmente accessibili, è necessario condividere questa cartella. Ad esempio: \\ATL-watcher-001. litwareinc. com\WatcherNode. 
