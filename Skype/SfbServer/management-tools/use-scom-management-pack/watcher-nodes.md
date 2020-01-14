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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Riepilogo: installare e configurare i nodi Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: 8c7ea0465d9a53bd8972c823ef7bfc7d7ee9b4bc
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104485"
---
# <a name="install-and-configure-watcher-nodes"></a>Installare e configurare i nodi Watcher
 
**Riepilogo:** Installare e configurare i nodi Watcher per le transazioni sintetiche di Skype for Business Server.
  
I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Skype for Business Server. Le transazioni sintetiche sono cmdlet di Windows PowerShell che verificano che gli scenari principali degli utenti, ad esempio la possibilità di accedere o di scambiare messaggi istantanei, funzionino come previsto. Per Skype for Business Server 2015, System Center Operations Manager può eseguire le transazioni sintetiche illustrate nella tabella seguente, che include tre tipi di transazione sintetici:
  
- **Impostazione predefinita** Transazioni sintetiche eseguite da un nodo Watcher per impostazione predefinita. Quando si crea un nuovo nodo Watcher, è possibile specificare le transazioni sintetiche che verranno eseguite da node. Questo è lo scopo del parametro tests usato dal cmdlet New-CsWatcherNodeConfiguration. Se non si usa il parametro tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite le transazioni sintetiche non predefinite. Questo significa, ad esempio, che il nodo Watcher sarà configurato per eseguire il Test CsAddressBookService, ma non sarà configurato per eseguire il test di test CsExumConnectivity.
    
- **Non predefinito** Verifica che i nodi Watcher non vengano eseguiti per impostazione predefinita. Per informazioni dettagliate, vedere la descrizione del tipo predefinito. Tuttavia, il nodo Watcher può essere abilitato per eseguire tutte le transazioni sintetiche non predefinite. Questa operazione può essere eseguita quando si crea il nodo Watcher (usando il cmdlet New-CsWatcherNodeConfiguration) o in qualsiasi momento dopo la creazione del nodo Watcher. Tieni presente che molte delle transazioni sintetiche non predefinite richiedono passaggi di configurazione aggiuntivi. Per altre informazioni su questa procedura, vedere [istruzioni per la configurazione speciale per le transazioni sintetiche](test-users-and-settings.md#special_synthetictrans).
    
- **Esteso** Un tipo speciale di transazione sintetica non predefinita. A differenza di altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio. Questa funzionalità è utile per verificare il comportamento, ad esempio più route vocali PSTN (Public Switched Telephone Network) per un pool. Puoi configurare questa operazione semplicemente aggiungendo più istanze di un test esteso a un nodo Watcher.
    
Per informazioni dettagliate sul processo per l'aggiunta di altre transazioni sintetiche a un nodo Watcher, vedere [configurare un nodo Watcher per l'esecuzione di transazioni sintetiche](watcher-nodes.md#enable_synthetic_trans). Puoi anche usare Skype for Business Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.
  
Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:
  
|**Nome cmdlet (nome test)**|**Descrizione**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Conferma che gli utenti possono cercare gli utenti non presenti nell'elenco contatti.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Conferma che gli utenti possono cercare gli utenti non presenti nell'elenco contatti tramite HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Conferma che gli utenti possono creare e partecipare a una conferenza audio/video.  <br/> |
|Test-CsGroupIM (servizi di conferenza di messaggistica istantanea)  <br/> |Conferma che gli utenti possono inviare messaggi istantanei in conferenze e partecipare a conversazioni di messaggistica istantanea con tre o più persone.  <br/> |
|Test-CsIM (messaggistica istantanea P2P)  <br/> |Conferma che gli utenti possono inviare messaggi istantanei peer-to-peer.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Conferma che gli utenti possono inserire chiamate audio peer-to-peer (solo segnalazione).  <br/> |
|Test-CsPresence (presenza)  <br/> |Conferma che gli utenti possono visualizzare la presenza di altri utenti.  <br/> |
|Test-CsRegistration (registrazione)  <br/> |Conferma che gli utenti possono accedere a Skype for business.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Conferma che gli utenti possono effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Conferma che gli utenti possono creare e partecipare a una conferenza di condivisione applicazioni.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Conferma che i server Edge audio video sono in grado di accettare connessioni per chiamate peer-to-peer e conferenze telefoniche.  <br/> |
|Test-CsDataConference (dataconference)  <br/> |Conferma che gli utenti possono partecipare a una conferenza di collaborazione dati (una riunione online che include attività come lavagne e sondaggi).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Conferma che gli utenti possono chiamare i numeri di telefono per partecipare alle conferenze.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Conferma che gli utenti possono chiamare i numeri di telefono per partecipare alle conferenze.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Conferma che un utente può connettersi alla messaggistica UNIFICAta di Exchange.  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Conferma che gli utenti possono creare e partecipare a riunioni pianificate (tramite un collegamento a un indirizzo Web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Conferma che gli utenti di dispositivi mobili sono in grado di registrare e inviare messaggi istantanei.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Conferma che il video Interop server è alto e può gestire le connessioni in ingresso su un trunk SIP video.  <br/> **Nota:** Il supporto MCX per i client mobili legacy non è più disponibile in Skype for Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Conferma che gli utenti possono scambiare messaggi usando il servizio di chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Conferma che gli utenti possono partecipare a conferenze tramite il Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Conferma che è possibile accedere ai contatti di un utente tramite l'archivio contatti unificato. L'archivio contatti unificato consente agli utenti di gestire un singolo set di contatti a cui è possibile accedere tramite Skype for Business Server 2015, client di messaggistica e collaborazione di Outlook e/o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Conferma che un messaggio istantaneo può essere inviato attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).  <br/> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.  |

Non è necessario installare i nodi Watcher per usare System Center Operations Manager. Se non si installano questi nodi, è comunque possibile ottenere avvisi in tempo reale dai componenti di Skype for Business Server 2015 ogni volta che si verifica un problema. Il Management Pack per i componenti e gli utenti non usa i nodi Watcher. Tuttavia, i nodi Watcher sono obbligatori se vuoi monitorare gli scenari end-to-end usando il Management Pack di monitoraggio attivo.
  
> [!NOTE]
> Gli amministratori possono anche eseguire manualmente le transazioni sintetiche, senza usare o installare Operations Manager. A seconda delle dimensioni della distribuzione di Skype for Business Server, le transazioni sintetiche possono usare una grande quantità di memoria computer e tempo processore. Per questo motivo, ti consigliamo di usare un computer dedicato come nodo Watcher. Ad esempio, non devi configurare un server front-end di Skype for Business Server per fungere da nodo Watcher. I nodi Watcher devono soddisfare gli stessi requisiti hardware di base di qualsiasi altro computer della topologia di Skype for Business Server. 
  
> [!NOTE]
> Un nodo di monitoraggio legacy di Lync Server 2013 non può essere installato nello stesso computer di un nodo di Watcher di Skype for Business Server 2015 perché i file di sistema principali per Lync Server 2013 e Skype for Business Server 2015 non possono essere installati nello stesso PC. Tuttavia, i nodi di Watcher per Skype for Business Server 2015 possono monitorare contemporaneamente Skype for Business Server 2015 e Lync Server 2013. Le transazioni sintetiche predefinite sono supportate per entrambe le versioni di prodotto. 
  
I nodi di Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per verificare:
  
- Connettività ai pool per gli utenti all'interno dell'organizzazione.
    
- Connettività tramite reti perimetrali per gli utenti remoti che lavorano all'esterno dell'organizzazione.
    
- Connettività agli elettrodomestici di filiale.
    
- Connettività a Lync Server 2013 all'interno dell'organizzazione e tramite reti perimetrali.
    
Per semplificare l'amministrazione, sono disponibili diverse opzioni di autenticazione per l'interno e l'esterno dell'organizzazione. Per informazioni dettagliate, vedere [configurare un nodo Watcher per l'esecuzione di transazioni sintetiche](watcher-nodes.md#enable_synthetic_trans).
  
Per configurare un computer per fungere da nodo Watcher, è necessario prima di tutto completare i prerequisiti seguenti: 
  
- Installare System Center Operations Manager e importare i Management Pack di Skype for Business Server 2015. È inoltre necessario verificare prima di tutto che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'installazione di Skype for Business Server 2015.
    
- Installare gli elementi seguenti nel computer del nodo Watcher:
    
  - Versione completa di .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3,0
    
Dopo aver soddisfatto i prerequisiti, è possibile configurare il nodo Watcher eseguendo la procedura seguente:
  
1. Installare i file di base di Skype for Business Server 2015 nel computer del nodo Watcher.
    
2. Installare System Center Operations Manager Agent nel computer del nodo Watcher.
    
3. Eseguire il file eseguibile di WatcherNode. msi.
    
4. Usa il cmdlet **New-CsWatcherNodeConfiguration** per configurare gli account utente di test che devono essere usati dal nodo Watcher.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installare i file di base di Skype for Business Server 2015 e il database di RTCLocal

Per installare i file di base di Skype for Business Server 2015 in un computer, eseguire la procedura seguente. Il database di RTCLocal verrà installato automaticamente quando si installano i file di base. Tieni presente che non è necessario installare SQL Server nei nodi Watcher. SQL Server Express verrà installato automaticamente.
  
Per installare i file di base di Skype for Business Server 2015 e il database di RTCLocal:
  
1. Nel computer del nodo Watcher fare clic sul pulsante Start, scegliere tutti i programmi, accessori, fare clic con il pulsante destro del mouse su prompt dei comandi e quindi scegliere Esegui come amministratore.
    
2. Nella finestra della console digitare il comando seguente e premere INVIO. Assicurarsi di immettere il percorso appropriato per i file di installazione di Skype for Business Server: D:\Setup.exe/BootstrapLocalMgmtTo verificare che i componenti principali di Skype for Business Server siano installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi fare clic su **Skype for Business Server Management Shell**. In Skype for Business Server Management Shell digitare il comando di Windows PowerShell seguente e premere INVIO:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La prima volta che si esegue questo comando non verranno restituiti dati perché non sono stati ancora configurati computer di nodi Watcher. Se il comando viene eseguito senza restituire un errore, è possibile supporre che la configurazione di Skype for Business Server sia stata completata correttamente. 
  
Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando seguente per verificare l'installazione di Skype for Business Server 2015:
  
Get-CsPinPolicyYou riceverà informazioni simili a queste, a seconda del numero di criteri PIN configurati per l'uso nell'organizzazione:
  
Identità: globale
  
Descrizione
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: false
  
PINLifetime: 0
  
MaximumLogonAttempts
  
Se vengono visualizzate informazioni sui criteri PIN, i componenti principali sono stati installati correttamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installare i file dell'agente Operation Manager in un nodo Watcher

In modo analogo alla configurazione di Skype for Business Server per gli avvisi relativi ai componenti, un nodo di Watcher per Skype for Business Server 2015 richiede l'installazione dei file dell'agente di System Center Operations Manager. In questo modo le transazioni sintetiche verranno eseguite e gli avvisi verranno segnalati al server di gestione radice di System Center Operations Manager.
  
Per installare i file dell'agente, seguire le procedure elencate in [configurare i computer di Skype for Business Server che verranno monitorati](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurare un nodo Watcher per l'esecuzione di transazioni sintetiche
<a name="enable_synthetic_trans"> </a>

Dopo aver installato i file dell'agente di System Center Operations Manager, è necessario configurare il nodo Watcher stesso. La procedura da eseguire in questo modo varia a seconda che il computer del nodo Watcher si trovi all'interno della rete perimetrale o all'esterno della rete perimetrale. 
  
Quando si configura un nodo Watcher, è necessario scegliere anche il tipo di metodo di autenticazione che deve essere impiegato da tale nodo. Skype for Business Server 2015 consente di scegliere uno dei due metodi di autenticazione: Trusted Server o Authentication Credential. La tabella seguente mostra le differenze tra questi due metodi:
  
||**Descrizione**|**Percorsi supportati**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa un certificato per rappresentare un server interno e ignorare i problemi di autenticazione.  <br/> Utile per gli amministratori che preferiscono gestire un singolo certificato, invece di molte password utente in ogni nodo Watcher.  <br/> |All'interno dell'organizzazione.  <br/> Con questo metodo, il nodo Watcher deve essere nello stesso dominio dei pool da monitorare. Se il nodo Watcher e i pool si trovano in domini diversi, usare invece l'autenticazione delle credenziali.  <br/> |
|Negoziare  <br/> |Archivia i nomi utente e le password in modo sicuro in Gestione credenziali di Windows in ogni nodo Watcher.  <br/> Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher all'esterno dell'organizzazione. Questi nodi Watcher non possono essere trattati come endpoint attendibili per l'autenticazione.  <br/> |All'esterno dell'organizzazione.  <br/> All'interno dell'organizzazione.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurare un nodo Watcher per l'uso dell'autenticazione server attendibile
<a name="enable_synthetic_trans"> </a>

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'uso di autenticazione server attendibile può ridurre notevolmente le attività di amministrazione mantenendo un singolo certificato, invece di usare numerose password per gli account utente.
  
Per configurare l'autenticazione attendibile del server, è necessario prima di tutto creare un pool di applicazioni attendibili per ospitare il computer del nodo Watcher. Dopo aver creato il pool di applicazioni attendibili, è necessario configurare le transazioni sintetiche nel nodo Watcher per l'esecuzione come applicazioni attendibili.
  
> [!NOTE]
> Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Skype for Business Server 2015, ma non è una parte incorporata del prodotto. Lo stato attendibile indica che l'applicazione non verrà contestata per l'autenticazione ogni volta che viene eseguita.
  
Per creare un pool di applicazioni attendibili, aprire Skype for Business Server Management Shell ed eseguire un comando simile al seguente:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Per informazioni dettagliate sui parametri del comando precedente, digitare quanto segue dal prompt di Skype for Business Server Management Shell: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Dopo aver creato il pool di applicazioni attendibili, è possibile configurare il computer del nodo Watcher per eseguire transazioni sintetiche come applicazione attendibile usando il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando questo comando viene completato e viene creata l'applicazione attendibile, è necessario eseguire il cmdlet **Enable-CsTopology** per verificare che le modifiche abbiano effetto:
  
```PowerShell
Enable-CsTopology
```

L'account del computer del nodo Watcher richiede la possibilità di eseguire query su CMS per alcune transazioni sintetiche. Per consentire questa funzionalità, aggiungere l'account del computer del nodo Watcher al gruppo di sicurezza RTCUniversalReadOnlyAdmins. Una volta che si è verificata la replica di Active Directory, riavviare il computer.
  
Per verificare che sia stata creata la nuova applicazione attendibile, digitare quanto segue al prompt di Skype for Business Server Management Shell:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurare un certificato predefinito nel nodo Watcher
<a name="enable_synthetic_trans"> </a>

Ogni nodo Watcher che usa l'autenticazione TrustedServer deve avere un certificato predefinito assegnato tramite la distribuzione guidata di Skype for Business Server. 
  
Per assegnare un certificato predefinito:
  
1. Fare clic sul pulsante Start, scegliere tutti i programmi, fare clic su Skype for Business Server 2015 e quindi fare clic su Skype for Business Server Deployment Wizard. 
    
2. Nella distribuzione guidata di Skype for Business Server, fai clic su Installa o Aggiorna Skype for Business Server System, quindi fai clic su Esegui sotto la richiesta di titolo, installa o assegna certificato. 
    
> [!NOTE]
> Se il pulsante Esegui è disabilitato, potrebbe essere necessario fare prima clic su Esegui in Installa archivio configurazione locale. 
  
Esegui una delle operazioni seguenti:
  
- Se si dispone già di un certificato che può essere usato come certificato predefinito, fare clic su predefinito nella procedura guidata certificato e quindi fare clic su Assegna. Seguire i passaggi della procedura guidata assegnazione certificati per assegnare il certificato.
    
- Se è necessario richiedere un certificato per l'uso del certificato predefinito, fare clic su Richiedi e quindi seguire i passaggi della richiesta guidata certificato per richiedere tale certificato. Se si usano i valori predefiniti per il certificato del server Web, si ottiene un certificato che è possibile assegnare come certificato predefinito.
    
## <a name="install-and-configure-a-watcher-node"></a>Installare e configurare un nodo Watcher
<a name="enable_synthetic_trans"> </a>

Dopo aver riavviato il computer del nodo Watcher e configurato un certificato, è necessario eseguire il file WatcherNode. msi. È necessario eseguire WatcherNode. msi in qualsiasi computer in cui sono installati sia i file dell'agente Operations Manager che i componenti principali di Skype for Business Server 2015. 
  
Per installare e configurare un nodo Watcher:
  
1. Aprire Skype for Business Server Management Shell facendo clic sul pulsante Start, scegliendo tutti i programmi, facendo clic su Skype for Business Server 2015 e quindi scegliendo Skype for Business Server Management Shell. 
    
2. In Management Shell digitare il comando seguente e quindi premere INVIO (assicurarsi e specificare il percorso effettivo della copia di WatcherNode. msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> È anche possibile eseguire WatcherNode. msi n da una finestra di comando. Per aprire una finestra di comando, fare clic su Start, fare clic con il pulsante destro del mouse su prompt dei comandi e quindi scegliere Esegui come amministratore. Quando viene visualizzata la finestra di comando, digitare lo stesso comando illustrato nel passaggio 2 sopra. 
  
> [!IMPORTANT]
> Nel comando precedente la coppia nome/valore Authentication = TrustedServer fa distinzione tra maiuscole e minuscole. Deve essere digitato esattamente come illustrato. Ad esempio, questo comando non riuscirà perché non usa l'involucro della lettera corretta: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

La modalità TrustedServer può essere usata solo con i computer che si trovano all'interno della rete perimetrale. Quando un nodo Watcher viene eseguito in modalità TrustedServer, gli amministratori non devono gestire le password degli utenti di test nel computer.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurare un nodo Watcher per l'uso di Negotiate
<a name="enable_synthetic_trans"> </a>

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è necessario seguire una procedura leggermente diversa per configurare il nodo Watcher in modo da eseguire transazioni sintetiche: in particolare, non è consigliabile creare un pool di applicazioni attendibili o un Trusted applicazione. Questo significa che dovrai completare le due attività successive.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aggiornare l'appartenenza al gruppo di amministratori di sola lettura RTC Local

Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account del servizio di rete al gruppo amministratori locali di sola lettura RTC nel computer del nodo Watcher eseguendo la procedura seguente nel nodo Watcher:
  
1. Fare clic su Start, fare clic con il pulsante destro del mouse su computer e quindi scegliere Gestisci.
    
2. In Server Manager espandere configurazione, espandere utenti e gruppi locali e quindi fare clic su gruppi.
    
3. Nel riquadro gruppi fare doppio clic su amministratori locali di sola lettura RTC.
    
4. Nella finestra di dialogo Proprietà amministratori locali di sola lettura RTC fare clic su Aggiungi.
    
5. Nella finestra di dialogo Seleziona utenti, computer, account di servizio o gruppi fare clic su percorsi.
    
6. Nella finestra di dialogo posizioni selezionare il nome del computer del nodo Watcher e quindi fare clic su OK.
    
7. Nella casella Immettere i nomi degli oggetti da selezionare digitare servizio di rete e quindi fare clic su OK.
    
8. Nella finestra di dialogo Proprietà amministratori locali di sola lettura RTC fare clic su OK e quindi chiudere Gestione server.
    
9. Riavviare il computer del nodo Watcher.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installare i file di configurazione del nodo Watcher

Il passaggio successivo consiste nell'eseguire il file WatcherNode. msi: 
  
1. Aprire Microsoft Skype for Business Server 2015 Management Shell. Fare clic sul pulsante Start, scegliere tutti i programmi, fare clic su Microsoft Skype for Business Server 2015 e quindi fare clic su Skype for Business Server Management Shell. 
    
2. In Skype for Business Server Management Shell digitare il comando seguente e quindi premere INVIO (assicurarsi di specificare il percorso effettivo della copia di WatcherNode. msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Come accennato in precedenza, Watchernode. msi può essere eseguito anche da una finestra di comando. Per aprire una finestra di comando, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**. Quando viene visualizzata la finestra di comando, digitare lo stesso comando illustrato nel passaggio 2 sopra. 
  
La modalità di negoziazione viene usata ogni volta che il nodo Watcher non può essere configurato come pool di applicazioni attendibili. In questa modalità, gli amministratori dovranno gestire le password degli utenti di test nel nodo Watcher.
  

