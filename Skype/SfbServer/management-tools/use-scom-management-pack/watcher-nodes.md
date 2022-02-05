---
title: Come installare e configurare i nodi Watcher
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: Descrive il processo di installazione e configurazione dei nodi Watcher per Skype for Business Server sintetiche.
---

# <a name="learn-to-install-configure-watcher-nodes"></a>Informazioni su come installare, configurare i nodi Watcher
 
**Riepilogo:** Installare e configurare nodi Watcher per Skype for Business Server sintetiche.
  
I nodi Watcher sono computer che eseguono periodicamente Skype for Business Server transazioni sintetiche. Le transazioni sintetiche Windows PowerShell cmdlet che verificano che gli scenari chiave degli utenti, ad esempio la possibilità di accedere o scambiare messaggi istantanei, funzionino come previsto. Per Skype for Business Server 2015, System Center Operations Manager può eseguire le transazioni sintetiche illustrate nella tabella seguente, che include tre tipi di transazioni sintetiche:
  
- **Impostazione predefinita** Transazioni sintetiche che un nodo Watcher viene eseguito per impostazione predefinita. Quando si crea un nuovo nodo Watcher, è possibile specificare quali transazioni sintetiche verranno eseguite dal nodo. Questo è lo scopo del parametro Tests utilizzato dal cmdlet New-CsWatcherNodeConfiguration. Se non si utilizza il parametro Tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite transazioni sintetiche non predefinite. Ciò significa, ad esempio, che il nodo Watcher verrà configurato per eseguire il test di Test-CsAddressBookService, ma non verrà configurato per eseguire il test Test-CsExumConnectivity test.
    
- **Non predefinito** Test che i nodi Watcher non vengono eseguiti per impostazione predefinita. Per informazioni dettagliate, vedere la descrizione del tipo Predefinito. Tuttavia, il nodo Watcher può essere abilitato per eseguire qualsiasi transazione sintetica non predefinita. È possibile eseguire questa operazione quando si crea il nodo Watcher (utilizzando il cmdlet New-CsWatcherNodeConfiguration) o in qualsiasi momento dopo la creazione del nodo Watcher. Si noti che molte delle transazioni sintetiche non predefinite richiedono passaggi di configurazione aggiuntivi. Per ulteriori informazioni su questi passaggi, vedere [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).
    
- **Esteso** Tipo speciale di transazione sintetica non predefinita. Diversamente da altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio. Ciò è utile quando si verifica un comportamento, ad esempio più route vocali PSTN (Public Switched Telephone Network) per un pool. Puoi configurarlo semplicemente aggiungendo più istanze di un test esteso a un nodo Watcher.
    
Per informazioni dettagliate sul processo di aggiunta di altre transazioni sintetiche a un nodo [Watcher, vedere Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). È inoltre possibile utilizzare Skype for Business Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.
  
Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:
  
|**Nome del cmdlet (nome test)**|**Descrizione**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Verifica che gli utenti siano in grado di cercare gli utenti che non sono presenti nell'elenco dei contatti.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Verifica che gli utenti siano in grado di cercare gli utenti che non sono presenti nell'elenco dei contatti tramite HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Conferma che gli utenti siano in grado di creare conferenze audio/video e di parteciparvi.  <br/> |
|Test-CsGroupIM (conferenza di messaggistica istantanea)  <br/> |Conferma che gli utenti siano in grado di inviare messaggi istantanei in conferenze e partecipare a conversazioni istantanee con tre o più persone.  <br/> |
|Test-CsIM (messaggistica istantanea P2P)  <br/> |Conferma che gli utenti siano in grado di inviare messaggi istantanei peer-to-peer.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Conferma che gli utenti siano in grado di effettuare chiamate audio peer-to-peer (solo segnalazione).  <br/> |
|Test-CsPresence (Presence)  <br/> |Verifica che gli utenti siano in grado di visualizzare la presenza di altri utenti.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Verifica che gli utenti siano in grado di accedere a Skype for Business.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Conferma che gli utenti siano in grado di effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Verifica che gli utenti siano in grado di creare e partecipare a una conferenza di condivisione applicazioni.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Verifica che i server Perimetrali audio video siano in grado di accettare connessioni per chiamate peer-to-peer e conferenze telefoniche.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Conferma che gli utenti possono partecipare a una conferenza di collaborazione dati (una riunione online che include attività quali lavagne e sondaggi).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Verifica che gli utenti siano in grado di comporre numeri di telefono per partecipare alle conferenze.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Verifica che gli utenti siano in grado di comporre numeri di telefono per partecipare alle conferenze.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Conferma che un utente può connettersi a Exchange messaggistica unificata.  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |Verifica che gli utenti siano in grado di creare e partecipare a riunioni pianificate (tramite un collegamento all'indirizzo Web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Conferma che gli utenti di dispositivi mobili siano in grado di registrarsi e inviare messaggi istantanei.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Verifica che Video Interop Server sia in grado di gestire le connessioni in ingresso su un trunk SIP video.  <br/> **Nota:** Il supporto MCX per i client mobili legacy non è più disponibile Skype for Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Verifica che gli utenti possano scambiare messaggi utilizzando il servizio Persistent Chat.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Conferma che gli utenti possono partecipare alle conferenze tramite il Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Verifica che sia possibile accedere ai contatti di un utente tramite l'archivio contatti unificato. L'archivio contatti unificato consente agli utenti di gestire un singolo set di contatti a cui è possibile accedere utilizzando Skype for Business Server 2015, un client di messaggistica e collaborazione Outlook e/o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Verifica che sia possibile inviare un messaggio istantaneo attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).  <br/> I gateway XMPP e i proxy sono disponibili Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.  |

Non è necessario installare nodi Watcher per utilizzare System Center Operations Manager. Se non si installano questi nodi, è comunque possibile ricevere avvisi in tempo reale dai componenti Skype for Business Server 2015 ogni volta che si verifica un problema. Il Management Pack per componenti e utenti non utilizza nodi Watcher. Tuttavia, i nodi Watcher sono necessari se si desidera monitorare gli scenari end-to-end utilizzando Active Monitoring Management Pack.
  
> [!NOTE]
> Gli amministratori possono anche eseguire le transazioni sintetiche manualmente, senza utilizzare o installare Operations Manager. A seconda delle dimensioni della distribuzione Skype for Business Server, le transazioni sintetiche possono utilizzare una grande quantità di memoria del computer e tempo del processore. Per questo, ti consigliamo di usare un computer dedicato come nodo Watcher. Ad esempio, non è consigliabile configurare un Skype for Business Server Front End Server in modo che agirà come nodo Watcher. I nodi Watcher devono soddisfare gli stessi requisiti hardware di base di qualsiasi altro computer della Skype for Business Server topologia. 
  
> [!NOTE]
> Un nodo Watcher legacy di Lync Server 2013 non può essere collocato nello stesso computer di un nodo Watcher di Skype for Business Server 2015 perché i file di sistema di base per Lync Server 2013 e Skype for Business Server 2015 non possono essere installati nello stesso computer. Tuttavia, Skype for Business Server watcher 2015 possono monitorare contemporaneamente Skype for Business Server 2015 e Lync Server 2013. Le transazioni sintetiche predefinite sono supportate per entrambe le versioni del prodotto. 
  
I nodi Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per verificare:
  
- Connettività ai pool per gli utenti all'interno dell'organizzazione.
    
- Connettività tramite reti perimetrali per utenti remoti che lavorano all'esterno dell'organizzazione.
    
- Connettività a Survivable Branch Appliance.
    
- Connettività a Lync Server 2013 all'interno dell'azienda e tramite reti perimetrali.
    
Per semplificare l'amministrazione, sono disponibili diverse opzioni di autenticazione all'interno e all'esterno dell'organizzazione. Per informazioni dettagliate, [vedere Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Per configurare un computer in modo che agirà come nodo Watcher, è innanzitutto necessario completare i prerequisiti seguenti: 
  
- Installare System Center Operations Manager e importare i Management Pack Skype for Business Server 2015. È inoltre necessario verificare che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'Skype for Business Server 2015.
    
- Installare gli elementi seguenti nel computer del nodo Watcher:
    
  - La versione completa di .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Dopo aver soddisfatto i prerequisiti, è possibile configurare il nodo Watcher seguendo questi passaggi:
  
1. Installare i Skype for Business Server 2015 core nel computer del nodo Watcher.
    
2. Installare System Center Operations Manager nel computer del nodo Watcher.
    
3. Eseguire il Watchernode.msi file eseguibile.
    
4. Utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per configurare gli account utente di test da utilizzare per il nodo Watcher.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installare i Skype for Business Server 2015 Core Files e rtcLocal Database

Per installare i Skype for Business Server 2015 core in un computer, eseguire la procedura seguente. Il database RTCLocal verrà installato automaticamente quando si installano i file di base. Tenere presente che non è necessario installare SQL Server nei nodi Watcher. SQL Server Express verrà installato automaticamente.
  
Per installare i file Skype for Business Server 2015 core e il database RTCLocal:
  
1. Nel computer del nodo Watcher, fare clic sul pulsante Start, scegliere Tutti i programmi e Accessori, fare clic con il pulsante destro del mouse su Prompt dei comandi e quindi scegliere Esegui come amministratore.
    
2. Nella finestra della console digitare il comando seguente e premere INVIO. Assicurarsi di immettere il percorso appropriato per i file di installazione di Skype for Business Server: D:\Setup.exe /BootstrapLocalMgmtPer verificare che i componenti Skype for Business Server di base siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere Tutti i **programmi,** **fare clic su Skype for Business Server 2015**, quindi fare clic su **Skype for Business Server Management Shell**. In Skype for Business Server Management Shell digitare il comando Windows PowerShell seguente e premere INVIO:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La prima volta che si esegue questo comando, non verranno restituiti dati perché non è stato ancora configurato alcun computer nodo Watcher. Se il comando viene eseguito senza restituire un errore, è possibile presupporre che l Skype for Business Server'installazione sia stata completata correttamente. 
  
Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando seguente per verificare l'installazione di Skype for Business Server 2015:
  
Get-CsPinPolicyYou riceveranno informazioni simili a queste, a seconda del numero di criteri PIN configurati per l'utilizzo nell'organizzazione:
  
Identity : Global
  
Descrizione :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Se vengono visualizzate informazioni sui criteri PIN, i componenti di base sono stati installati correttamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installare i file agente di Operation Manager in un nodo Watcher

Analogamente alla configurazione Skype for Business Server per la creazione di report degli avvisi dei componenti, un nodo Watcher di Skype for Business Server 2015 richiede System Center i file agente di Operations Manager per essere installato. Ciò consente l'esecuzione delle transazioni sintetiche e la segnalazione degli avvisi al server di gestione radice System Center Operations Manager.
  
Per installare i file agente, seguire le procedure elencate in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurare un nodo Watcher per l'esecuzione di transazioni sintetiche
<a name="enable_synthetic_trans"> </a>

Dopo aver System Center i file dell'agente Operations Manager, è necessario configurare il nodo Watcher stesso. I passaggi da eseguire per eseguire questa operazione variano a seconda che il computer del nodo Watcher si trova all'interno della rete perimetrale o all'esterno della rete perimetrale. 
  
Quando si configura un nodo Watcher, è inoltre necessario scegliere il tipo di metodo di autenticazione da utilizzare per tale nodo. Skype for Business Server 2015 consente di scegliere uno dei due metodi di autenticazione seguenti: Trusted Server o Credential Authentication. Nella tabella seguente vengono illustrate le differenze tra questi due metodi:
  
|&nbsp;|**Descrizione**|**Percorsi supportati**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Utilizza un certificato per rappresentare un server interno e ignorare le sfide di autenticazione.  <br/> Utile per gli amministratori che preferiscono gestire un singolo certificato, anziché molte password utente in ogni nodo Watcher.  <br/> |All'interno dell'azienda.  <br/> Con questo metodo, il nodo Watcher deve essere nello stesso dominio dei pool monitorati. Se il nodo Watcher e i pool sono in domini diversi, usa invece l'autenticazione delle credenziali.  <br/> |
|Negozia  <br/> |Archivia in modo sicuro i nomi utente e le password in Windows gestione credenziali in ogni nodo Watcher.  <br/> Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher esterni all'organizzazione. Questi nodi Watcher non possono essere considerati come endpoint attendibili per l'autenticazione.  <br/> |All'esterno dell'organizzazione.  <br/> All'interno dell'azienda.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurare un nodo Watcher per l'utilizzo dell'autenticazione server attendibile
<a name="enable_synthetic_trans"> </a>

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'utilizzo dell'autenticazione server trusted può ridurre notevolmente le attività di amministrazione mantenendo un singolo certificato, anziché utilizzare numerose password degli account utente.
  
Per configurare l'autenticazione del server trusted, è innanzitutto necessario creare un pool di applicazioni attendibili per ospitare il computer del nodo Watcher. Dopo aver creato il pool di applicazioni attendibili, è necessario configurare le transazioni sintetiche in tale nodo Watcher per l'esecuzione come applicazioni attendibili.
  
> [!NOTE]
> Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Skype for Business Server 2015, ma non è una parte incorporata del prodotto. Lo stato attendibile indica che all'applicazione non verrà richiesta l'autenticazione a ogni esecuzione.
  
Per creare un pool di applicazioni attendibili, aprire Skype for Business Server Management Shell ed eseguire un comando simile al seguente:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Per informazioni dettagliate sui parametri nel comando precedente, digitare quanto segue dal prompt Skype for Business Server Management Shell: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Dopo aver creato il pool di applicazioni attendibili, è possibile configurare il computer del nodo Watcher per l'esecuzione di transazioni sintetiche come applicazione attendibile utilizzando il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando questo comando viene completato e viene creata l'applicazione attendibile, è necessario eseguire il cmdlet **Enable-CsTopology** per assicurarsi che le modifiche siano effettive:
  
```PowerShell
Enable-CsTopology
```

L'account computer del nodo Watcher richiede la possibilità di eseguire query su CMS per alcune transazioni sintetiche. Per consentire questa funzionalità, aggiungere l'account computer del nodo Watcher al gruppo di sicurezza RTCUniversalReadOnlyAdmins. Dopo aver verificato la replica ad Active Directory, riavviare il computer.
  
Per verificare che la nuova applicazione attendibile sia stata creata, digitare quanto segue al prompt Skype for Business Server Management Shell:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurare un certificato predefinito nel nodo Watcher
<a name="enable_synthetic_trans"> </a>

A ogni nodo Watcher che utilizza l'autenticazione TrustedServer deve essere assegnato un certificato predefinito tramite la Skype for Business Server guidata. 
  
Per assegnare un certificato predefinito:
  
1. Fare clic sul pulsante Start, scegliere Tutti i programmi, Skype for Business Server 2015 e quindi fare clic Skype for Business Server distribuzione guidata. 
    
2. Nella Distribuzione guidata Skype for Business Server, fare clic su Installa o aggiorna Skype for Business Server sistema e quindi fare clic su Esegui sotto l'intestazione Richiesta, installazione o assegnazione certificato. 
    
> [!NOTE]
> Se il pulsante Esegui è disabilitato, può essere necessario prima fare clic su Esegui al di sotto di Installazione dell'archivio di configurazione locale. 
  
Eseguire una delle operazioni seguenti:
  
- Se si dispone già di un certificato che può essere utilizzato come certificato predefinito, fare clic su Predefinito nella procedura guidata Certificato e quindi fare clic su Assegna. Seguire i passaggi indicati nella procedura guidata Assegnazione certificato per assegnarlo.
    
- Se è necessario richiedere un certificato per l'utilizzo del certificato predefinito, fare clic su Richiesta e quindi seguire i passaggi della procedura guidata Richiesta di certificato per richiedere tale certificato. Se si utilizzano i valori predefiniti per il certificato del server Web, si ottiene un certificato che può essere assegnato come predefinito.
    
## <a name="install-and-configure-a-watcher-node"></a>Installare e configurare un nodo Watcher
<a name="enable_synthetic_trans"> </a>

Dopo aver riavviato il computer del nodo Watcher e configurato un certificato, è necessario eseguire il file Watchernode.msi. È necessario eseguire Watchernode.msi in qualsiasi computer in cui siano installati sia i file dell'agente operations Manager che i componenti Skype for Business Server 2015 core. 
  
Per installare e configurare un nodo Watcher:
  
1. Aprire la Skype for Business Server Management Shell facendo clic sul pulsante Start, scegliendo Tutti i programmi, Skype for Business Server 2015 e quindi facendo clic su Skype for Business Server Management Shell. 
    
2. In Management Shell digitare il comando seguente e quindi premere INVIO (assicurarsi di specificare il percorso effettivo della copia di Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> È inoltre possibile eseguire Watchernode.msi n da una finestra di comando. Per aprire una finestra di comando, fare clic sul pulsante Start, fare clic con il pulsante destro del mouse su Prompt dei comandi e quindi scegliere Esegui come amministratore. All'apertura della finestra di comando, digitare lo stesso comando mostrato nel passaggio 2 precedente. 
  
> [!IMPORTANT]
> Nel comando precedente, la coppia nome/valore Authentication=TrustedServer fa distinzione tra maiuscole e minuscole. Deve essere digitato esattamente come mostrato. Ad esempio, questo comando avrà esito negativo perché non utilizza l'uso corretto di maiuscole e minuscole: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

La modalità TrustedServer può essere utilizzata solo con i computer che si trovano all'interno della rete perimetrale. Quando un nodo Watcher viene eseguito in modalità TrustedServer, gli amministratori non devono gestire le password utente di prova nel computer.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurare un nodo Watcher per l'utilizzo di Negotiate
<a name="enable_synthetic_trans"> </a>

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è necessario seguire una procedura leggermente diversa per configurare tale nodo Watcher per l'esecuzione di transazioni sintetiche: in particolare, non è consigliabile creare un pool di applicazioni attendibili o un'applicazione attendibile. Ciò significa che sarà necessario completare le due attività seguenti.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aggiornare l'appartenenza al gruppo RTC Local Read-Only Administrators

Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account Servizio di rete al gruppo RTC Local Read-only Administrators nel computer del nodo Watcher completando la procedura seguente nel nodo Watcher:
  
1. Fare clic sul pulsante Start, fare clic su Computer con il pulsante destro del mouse e quindi scegliere Gestione.
    
2. In Server Manager espandere Configurazione e Utenti e gruppi locali, quindi fare clic su Gruppi.
    
3. Nel riquadro Gruppi fare doppio clic su RTC Local Read-only Administrators.
    
4. Nella finestra delle proprietà del gruppo RTC Local Read-only Administrators fare clic su Aggiungi.
    
5. Nella finestra di dialogo Selezione utenti, computer, account di servizio o gruppi fare clic su Percorsi.
    
6. Nella finestra di dialogo Percorsi selezionare il nome del computer che funge da nodo Watcher e quindi fare clic su OK.
    
7. Nella casella Immettere i nomi degli oggetti da selezionare digitare Servizio di rete e quindi fare clic su OK.
    
8. Nella finestra delle proprietà del gruppo RTC Local Read-only Administrators Properties fare clic su OK e quindi chiudere Server Manager.
    
9. Riavviare il computer che funge da nodo Watcher.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installare i file di configurazione del nodo Watcher

Il passaggio successivo consiste nell'eseguire il file Watchernode.msi: 
  
1. Aprire Microsoft Skype for Business Server 2015 Management Shell. Fare clic sul pulsante Start, scegliere Tutti i programmi, Microsoft Skype for Business Server 2015 e quindi fare clic Skype for Business Server Management Shell. 
    
2. In Skype for Business Server Management Shell digitare il comando seguente e quindi premere INVIO (assicurarsi di specificare il percorso effettivo della copia di Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Come accennato in precedenza, Watchernode.msi può essere eseguito anche da una finestra di comando. Per aprire una finestra di comando, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**. All'apertura della finestra di comando, digitare lo stesso comando mostrato nel passaggio 2 precedente. 
  
La modalità Negotiate viene usata ogni volta che non è possibile configurare il nodo Watcher come pool di applicazioni attendibili. In questa modalità, gli amministratori dovranno gestire le password utente di prova nel nodo Watcher.
  

