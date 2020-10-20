---
title: Installare e configurare i nodi Watcher
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Riepilogo: installazione e configurazione dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2020
ms.locfileid: "48599834"
---
# <a name="install-and-configure-watcher-nodes"></a>Installare e configurare i nodi Watcher
 
**Riepilogo:** Installare e configurare i nodi Watcher per le transazioni sintetiche di Skype for Business Server.
  
I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Skype for Business Server. Le transazioni sintetiche sono cmdlet di Windows PowerShell che verificano che gli scenari principali degli utenti, ad esempio la possibilità di accedere o di scambiare messaggi istantanei, funzionino come previsto. Per Skype for Business Server 2015, System Center Operations Manager è in grado di eseguire le transazioni sintetiche illustrate nella tabella seguente, che include tre tipi di transazioni sintetiche:
  
- **Valore predefinito** Transazioni sintetiche eseguite da un nodo Watcher per impostazione predefinita. Quando si crea un nuovo nodo Watcher, è possibile specificare quali transazioni sintetiche verranno eseguite dal nodo. (Questo è lo scopo del parametro tests utilizzato dal cmdlet New-CsWatcherNodeConfiguration). Se non si utilizza il parametro tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite le transazioni sintetiche non predefinite. Questo significa, ad esempio, che il nodo Watcher sarà configurato per eseguire il test Test-CsAddressBookService, ma non verrà configurato per eseguire il test di Test-CsExumConnectivity.
    
- **Non predefinito** Verifica che i nodi Watcher non vengano eseguiti per impostazione predefinita. Per informazioni dettagliate, vedere la descrizione del tipo predefinito. Tuttavia, il nodo Watcher può essere abilitato per l'esecuzione di una qualsiasi delle transazioni sintetiche non predefinite. È possibile eseguire questa operazione quando si crea il nodo Watcher (utilizzando il cmdlet New-CsWatcherNodeConfiguration) o in qualsiasi momento dopo che è stato creato il nodo Watcher. Si noti che molte delle transazioni sintetiche non predefinite richiedono passaggi di installazione aggiuntivi. Per ulteriori informazioni su questi passaggi, vedere [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).
    
- **Esteso** Un tipo speciale di transazione sintetica non predefinita. Diversamente da altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio. Questa operazione è utile quando si verificano comportamenti, ad esempio più route vocali PSTN (Public Switched Telephone Network) per un pool. È possibile configurarlo semplicemente aggiungendo più istanze di un test esteso a un nodo Watcher.
    
Per informazioni dettagliate sul processo di aggiunta di altre transazioni sintetiche a un nodo Watcher, vedere [Configure a Watcher node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). È inoltre possibile utilizzare Skype for Business Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.
  
Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:
  
|**Nome del cmdlet (nome test)**|**Descrizione**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Conferma che gli utenti sono in grado di cercare utenti non presenti nell'elenco dei contatti.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Conferma che gli utenti sono in grado di cercare utenti che non sono presenti nell'elenco dei contatti tramite HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Conferma che gli utenti siano in grado di creare conferenze audio/video e di parteciparvi.  <br/> |
|Test-CsGroupIM (servizi di conferenza di messaggistica istantanea)  <br/> |Conferma che gli utenti siano in grado di inviare messaggi istantanei in conferenze e partecipare a conversazioni istantanee con tre o più persone.  <br/> |
|Test-CsIM (MESSAGGISTICA ISTANTANEA P2P)  <br/> |Conferma che gli utenti siano in grado di inviare messaggi istantanei peer-to-peer.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Conferma che gli utenti siano in grado di effettuare chiamate audio peer-to-peer (solo segnalazione).  <br/> |
|Test-CsPresence (Presence)  <br/> |Conferma che gli utenti sono in grado di visualizzare la presenza di altri utenti.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Conferma che gli utenti sono in grado di accedere a Skype for business.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Conferma che gli utenti siano in grado di effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Conferma che gli utenti sono in grado di creare e partecipare a una conferenza di condivisione di applicazioni.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Conferma che i server perimetrali audio video sono in grado di accettare le connessioni per le chiamate peer-to-peer e le conferenze telefoniche.  <br/> |
|Test-CsDataConference (dataconference)  <br/> |Conferma che gli utenti possono partecipare a una conferenza di collaborazione dati (una riunione online che include attività come lavagne e sondaggi).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Conferma che gli utenti sono in grado di comporre i numeri di telefono per partecipare a conferenze.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Conferma che gli utenti sono in grado di comporre i numeri di telefono per partecipare a conferenze.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Conferma che un utente può connettersi alla messaggistica unificata di Exchange.  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Conferma che gli utenti sono in grado di creare e partecipare a riunioni pianificate (tramite un collegamento a un indirizzo Web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Conferma che gli utenti di dispositivi mobili siano in grado di registrarsi e inviare messaggi istantanei.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Conferma che il server di interoperabilità video è attivo e che è in grado di gestire le connessioni in ingresso su un trunk SIP video.  <br/> **Nota:** Il supporto di MCX per i client mobili legacy non è più disponibile in Skype for Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Conferma che gli utenti possono scambiare messaggi tramite il servizio chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Conferma che gli utenti possono partecipare a conferenze tramite il Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Conferma che è possibile accedere ai contatti di un utente tramite l'archivio contatti unificato. L'archivio contatti unificato consente agli utenti di gestire un singolo gruppo di contatti a cui è possibile accedere tramite Skype for Business Server 2015, client di messaggistica e collaborazione di Outlook e/o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Conferma che è possibile inviare un messaggio istantaneo attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).  <br/> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019.  |

Non è necessario installare i nodi Watcher per l'utilizzo di System Center Operations Manager. Se non si installano questi nodi, è comunque possibile ottenere avvisi in tempo reale dai componenti di Skype for Business Server 2015 ogni volta che si verifica un problema. (Il componente e il Management Pack degli utenti non utilizzano i nodi Watcher). Tuttavia, i nodi Watcher sono obbligatori se si desidera monitorare gli scenari end-to-end tramite Active Monitoring Management Pack.
  
> [!NOTE]
> Gli amministratori possono anche eseguire manualmente transazioni sintetiche, senza utilizzare o installare Operations Manager. A seconda delle dimensioni della distribuzione di Skype for Business Server, le transazioni sintetiche possono utilizzare una quantità elevata di memoria del computer e il tempo del processore. Per questo motivo, si consiglia di utilizzare un computer dedicato come nodo Watcher. Ad esempio, non è necessario configurare un server front-end di Skype for Business Server che funga da nodo Watcher. I nodi Watcher devono soddisfare gli stessi requisiti hardware di base di qualsiasi altro computer della topologia del server Skype for business. 
  
> [!NOTE]
> Un nodo di monitoraggio di Lync Server 2013 legacy non può essere collocato nello stesso computer di un nodo di monitoraggio di Skype for Business Server 2015, perché i file di sistema di base per Lync Server 2013 e Skype for Business Server 2015 non possono essere installati nello stesso calcolatore. Tuttavia, i nodi di monitoraggio di Skype for Business Server 2015 possono monitorare contemporaneamente Skype for Business Server 2015 e Lync Server 2013. Le transazioni sintetiche predefinite sono supportate per entrambe le versioni di prodotto. 
  
I nodi di Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per consentirne la verifica:
  
- Connettività ai pool per gli utenti all'interno dell'organizzazione.
    
- Connettività tramite reti perimetrali per gli utenti remoti che lavorano all'esterno dell'organizzazione.
    
- Connettività a Survivable Branch Appliance.
    
- Connettività a Lync Server 2013 all'interno dell'organizzazione e tramite reti perimetrali.
    
Per semplificare l'amministrazione, sono disponibili diverse opzioni di autenticazione per l'interno e l'esterno dell'organizzazione. Per informazioni dettagliate, vedere [Configure a Watcher node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Per configurare un computer come nodo Watcher, è necessario prima completare i prerequisiti seguenti: 
  
- Installare System Center Operations Manager e importare i Management Pack di Skype for Business Server 2015. È inoltre necessario verificare innanzitutto che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'installazione di Skype for Business Server 2015.
    
- Installare gli elementi seguenti nel computer del nodo Watcher:
    
  - La versione completa di .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Dopo aver soddisfatto i prerequisiti, è possibile configurare il nodo Watcher attenendosi alla procedura seguente:
  
1. Installare i file principali di Skype for Business Server 2015 nel computer del nodo Watcher.
    
2. Installare System Center Operations Manager Agent nel computer del nodo Watcher.
    
3. Eseguire il file eseguibile Watchernode.msi.
    
4. Utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per configurare gli account utente di test che devono essere utilizzati dal nodo Watcher.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installare i file principali di Skype for Business Server 2015 e il database di RTCLocal

Per installare i file principali di Skype for Business Server 2015 in un computer, eseguire la procedura seguente. Il database di RTCLocal verrà installato automaticamente quando si installano i file di base. Si noti che non è necessario installare SQL Server nei nodi Watcher. SQL Server Express verrà installato automaticamente.
  
Per installare i file principali di Skype for Business Server 2015 e il database di RTCLocal:
  
1. Nel computer del nodo Watcher, fare clic sul pulsante Start, scegliere Tutti i programmi e Accessori, fare clic con il pulsante destro del mouse su Prompt dei comandi e quindi scegliere Esegui come amministratore.
    
2. Nella finestra della console digitare il comando seguente e premere INVIO. Assicurarsi di immettere il percorso appropriato per i file di installazione di Skype for Business Server: D:\Setup.exe/BootstrapLocalMgmtTo verificare che i componenti di base di Skype for Business Server siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server Management Shell**. In Skype for Business Server Management Shell, digitare il comando di Windows PowerShell seguente e premere INVIO:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La prima volta che si esegue questo comando, non verranno restituiti dati perché non sono stati ancora configurati i computer dei nodi Watcher. Se il comando viene eseguito senza restituire un errore, è possibile presumere che il programma di installazione di Skype for Business Server sia stato completato correttamente. 
  
Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando riportato di seguito per verificare l'installazione di Skype for Business Server 2015:
  
Get-CsPinPolicyYou riceverà informazioni simili a quelle, a seconda del numero di criteri PIN configurati per l'utilizzo nell'organizzazione:
  
Identità: globale
  
Descrizione
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: false
  
PINLifetime: 0
  
MaximumLogonAttempts
  
Se vengono visualizzate informazioni sui criteri PIN, i componenti di base sono stati installati correttamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installare i file dell'agente Operation Manager in un nodo Watcher

Analogamente al programma di installazione di Skype for Business Server per gli avvisi del componente di Reporting, un nodo di monitoraggio di Skype for Business Server 2015 richiede l'installazione dei file dell'agente System Center Operations Manager. In questo modo le transazioni sintetiche devono essere eseguite e gli avvisi devono essere segnalati al server di gestione radice di System Center Operations Manager.
  
Per installare i file dell'agente, seguire le procedure elencate in [configurare i computer Skype for Business Server che verranno monitorati](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche
<a name="enable_synthetic_trans"> </a>

Dopo l'installazione dei file dell'agente System Center Operations Manager, è necessario configurare il nodo Watcher stesso. I passaggi da eseguire in questo modo variano a seconda che il computer del nodo Watcher sia all'interno della rete perimetrale o all'esterno della rete perimetrale. 
  
Quando si configura un nodo Watcher, è necessario scegliere anche il tipo di metodo di autenticazione da utilizzare per tale nodo. Skype for Business Server 2015 consente di scegliere uno dei due metodi di autenticazione: Trusted Server o Credential Authentication. Nella tabella seguente vengono illustrate le differenze tra i due metodi seguenti:
  
||**Descrizione**|**Posizioni supportate**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Utilizza un certificato per rappresentare un server interno e ignorare i problemi di autenticazione.  <br/> Utile per gli amministratori che preferiscono gestire un singolo certificato, anziché molte password utente in ogni nodo Watcher.  <br/> |All'interno dell'organizzazione.  <br/> Con questo metodo, il nodo Watcher deve trovarsi nello stesso dominio dei pool monitorati. Se il nodo Watcher e i pool sono in domini diversi, utilizzare invece l'autenticazione delle credenziali.  <br/> |
|Negozia  <br/> |Archivia i nomi utente e le password in modo sicuro in Gestione credenziali di Windows su ogni nodo Watcher.  <br/> Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher all'esterno dell'organizzazione. Questi nodi Watcher non possono essere considerati come endpoint attendibili per l'autenticazione.  <br/> |All'esterno dell'organizzazione.  <br/> All'interno dell'organizzazione.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurare un nodo Watcher per l'utilizzo dell'autenticazione del server attendibile
<a name="enable_synthetic_trans"> </a>

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'utilizzo dell'autenticazione basata su server attendibili può ridurre notevolmente le attività di amministrazione mantenendo un singolo certificato anziché utilizzare numerose password degli account utente.
  
Per configurare l'autenticazione basata su server attendibili, è necessario innanzitutto creare un pool di applicazioni attendibili per ospitare il computer del nodo Watcher. Dopo aver creato il pool di applicazioni attendibili, è necessario configurare le transazioni sintetiche sul nodo Watcher per l'esecuzione come applicazioni attendibili.
  
> [!NOTE]
> Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Skype for Business Server 2015, ma non è una parte incorporata del prodotto. Lo stato attendibile indica che all'applicazione non verrà richiesta l'autenticazione a ogni esecuzione.
  
Per creare un pool di applicazioni attendibili, aprire la shell di gestione di Skype for Business Server ed eseguire un comando simile al seguente:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Per informazioni dettagliate sui parametri nel comando precedente, digitare il testo seguente dal prompt di Skype for Business Server Management Shell: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Dopo aver creato il pool di applicazioni attendibili, è possibile configurare il computer del nodo Watcher per eseguire transazioni sintetiche come applicazione attendibile utilizzando il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando il comando viene completato e viene creata l'applicazione attendibile, è necessario eseguire il cmdlet **Enable-CsTopology** per assicurarsi che le modifiche abbiano effetto:
  
```PowerShell
Enable-CsTopology
```

L'account computer del nodo Watcher richiede la possibilità di eseguire query su CMS per alcune transazioni sintetiche. Per consentire questa funzionalità, aggiungere l'account computer del nodo Watcher al gruppo di sicurezza RTCUniversalReadOnlyAdmins. Dopo la replica di Active Directory, riavviare il computer.
  
Per verificare che la nuova applicazione attendibile sia stata creata, digitare quanto segue al prompt di Skype for Business Server Management Shell:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurare un certificato predefinito nel nodo Watcher
<a name="enable_synthetic_trans"> </a>

Ogni nodo Watcher che utilizza l'autenticazione di TrustedServer deve disporre di un certificato predefinito assegnato tramite la distribuzione guidata di Skype for Business Server. 
  
Per assegnare un certificato predefinito:
  
1. Fare clic sul pulsante Start, scegliere tutti i programmi, fare clic su Skype for Business Server 2015 e quindi fare clic su Skype for Business Server Deployment Wizard. 
    
2. Nella distribuzione guidata di Skype for Business Server, fare clic su Installa o aggiorna il sistema di Skype for Business Server, quindi fare clic su Esegui nella sezione richiesta, installazione o assegnazione di un certificato. 
    
> [!NOTE]
> Se il pulsante Esegui è disabilitato, può essere necessario prima fare clic su Esegui al di sotto di Installazione dell'archivio di configurazione locale. 
  
Eseguire una delle operazioni seguenti:
  
- Se si dispone già di un certificato che può essere utilizzato come certificato predefinito, fare clic su predefinita nella procedura guidata per il certificato e quindi fare clic su Assegna. Seguire i passaggi indicati nella procedura guidata Assegnazione certificato per assegnarlo.
    
- Se è necessario richiedere un certificato per l'utilizzo del certificato predefinito, fare clic su richiesta e quindi seguire i passaggi della procedura guidata per richiedere il certificato. Se si utilizzano i valori predefiniti per il certificato del server Web, si ottiene un certificato che può essere assegnato come predefinito.
    
## <a name="install-and-configure-a-watcher-node"></a>Installare e configurare un nodo Watcher
<a name="enable_synthetic_trans"> </a>

Dopo aver riavviato il computer del nodo Watcher e configurato un certificato, è necessario eseguire il file Watchernode.msi. È necessario eseguire Watchernode.msi in qualsiasi computer in cui sono installati sia i file dell'agente di Operations Manager che i componenti di base di Skype for Business Server 2015. 
  
Per installare e configurare un nodo Watcher:
  
1. Aprire Skype for Business Server Management Shell facendo clic sul pulsante Start, scegliendo tutti i programmi, facendo clic su Skype for Business Server 2015 e quindi su Skype for Business Server Management Shell. 
    
2. Nella shell di gestione, digitare il comando seguente e quindi premere INVIO (accertarsi di specificare il percorso effettivo della copia del Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> È inoltre possibile eseguire Watchernode.msi n da una finestra di comando. Per aprire una finestra di comando, fare clic sul pulsante Start, fare clic con il pulsante destro del mouse su Prompt dei comandi e quindi scegliere Esegui come amministratore. Quando viene visualizzata la finestra di comando, digitare lo stesso comando mostrato nel passaggio 2, in alto. 
  
> [!IMPORTANT]
> Nel comando precedente, la coppia nome/valore Authentication = TrustedServer è distinzione tra maiuscole e minuscole. È necessario digitarlo esattamente come illustrato. Ad esempio, questo comando avrà esito negativo perché non utilizza la combinazione di maiuscole e minuscole: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

La modalità TrustedServer può essere utilizzata solo con i computer che si trovano all'interno della rete perimetrale. Quando un nodo Watcher viene eseguito in modalità TrustedServer, gli amministratori non devono mantenere le password degli utenti di test nel computer.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurazione di un nodo Watcher per l'utilizzo di Negotiate
<a name="enable_synthetic_trans"> </a>

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è necessario eseguire una procedura leggermente diversa per configurare il nodo Watcher in modo da eseguire transazioni sintetiche: in particolare, non è necessario creare un pool di applicazioni attendibili o un'applicazione attendibile. Questo significa che sarà necessario completare le due attività successive.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aggiornare l'appartenenza al gruppo RTC Local Read-Only Administrators

Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account di servizio di rete al gruppo RTC Local Read-Only Administrators nel computer del nodo Watcher eseguendo la procedura seguente nel nodo Watcher:
  
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
  
1. Aprire Microsoft Skype for Business Server 2015 Management Shell. Fare clic sul pulsante Start, scegliere tutti i programmi, Microsoft Skype for Business Server 2015 e quindi fare clic su Skype for Business Server Management Shell. 
    
2. In Skype for Business Server Management Shell, digitare il comando seguente e quindi premere INVIO (accertarsi di specificare il percorso effettivo della copia di Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Come accennato in precedenza, Watchernode.msi può essere eseguito anche da una finestra di comando. Per aprire una finestra di comando, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**. Quando viene visualizzata la finestra di comando, digitare lo stesso comando mostrato nel passaggio 2, in alto. 
  
La modalità Negotiate viene usata ogni volta che non è possibile configurare il nodo Watcher come pool di applicazioni attendibili. In questa modalità, gli amministratori dovranno gestire le password utente di prova nel nodo Watcher.
  

