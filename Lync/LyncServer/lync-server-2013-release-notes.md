---
title: Note sulla versione di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7339b4861fe6e7e93e08d4928f6128916aeea0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Note sulla versione per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-08_

Note sulla versione di Lync Server 2013. Per informazioni sui problemi noti relativi a Lync Server 2013, vedere questo file.

<div>

## <a name="about-this-document"></a>Informazioni sul documento

Questo documento contiene informazioni importanti che è necessario conoscere prima di distribuire e utilizzare Lync Server 2013. Per informazioni dettagliate su Lync Server 2013, vedere la documentazione relativa a [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

In questo documento sono incluse le sezioni seguenti:

  - Client Lync 2013

  - Lync Server

  - Installazione

  - Mobilità

  - Conferenza

  - VoIP aziendale

  - Presenza

  - Applicazione Response Group e applicazione Call Park

  - Pannello di controllo di Lync Server, Generatore di topologie e Strumento di pianificazione

  - Localizzazione

  - Copyright

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Client Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>Il trasferimento di un file in un messaggio istantaneo ha esito negativo se il file è aperto in un'altra applicazione

**Problema**

Se si tenta di trasferire un file, ad esempio un documento di Word, inserendolo in un messaggio istantaneo a un altro utente Lync, il trasferimento avrà esito positivo, ma potrebbe non essere in grado di trasferire il file. Nel client Lync verrà visualizzata un'icona per il tipo di file, ma il file non può essere aperto dal destinatario previsto. Non viene visualizzato alcun messaggio di errore che informa che il trasferimento non ha avuto esito positivo.

**Soluzione alternativa**

Per ovviare a questo problema, chiudere il file o l'applicazione aperta che è aperta prima di tentare di trasferire il file in un messaggio istantaneo.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Se la replica dei dati del servizio di archiviazione di Lync Server non riesce, gli amministratori dovranno controllare i contatori delle prestazioni per gli elementi di coda del servizio di archiviazione

**Problema**

Il servizio di archiviazione di Lync Server utilizza Windows Fabric per la replica. Se i dati vengono eliminati in un front end server primario, ma l'eliminazione di un server front-end secondario ha esito negativo, ad esempio se è presente un arresto o un errore imprevisto nel front end server, i dati possono essere lasciati indietro e "orfani". I dati orfani possono causare la riduzione dello spazio di unità e la riduzione delle prestazioni.

**Soluzione alternativa**

Per ovviare a questo problema, se gli eventi\_Lyss\_DB\_Space\_used Error (ID = 32058) e\_Lyss\_DB\_Space\_used Critical (ID = 32059) vengono generati nel registro eventi, gli amministratori dovrebbero controllare il contatore delle prestazioni sul front end server in **ls: Lyss-servizio di archiviazione API** con nome **Lyss-Current numero di elementi di coda non aggiornati del servizio di archiviazione**. Se il contatore delle prestazioni ha un valore elevato, ad esempio maggiore di 50000, l'amministratore deve eseguire lo strumento CleanuUpStorageServiceData. exe nel Resource Kit di Lync Server 2013, che eliminerà tutti i dati orfani dal pool. Per informazioni dettagliate sullo strumento, vedere la documentazione di Lync Server 2013 Resource Kit.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Ogni volta che viene modificata la configurazione dell'indirizzo IP per un server o un pool, è necessario riavviare i servizi di Lync Server

**Problema**

Quando la configurazione dell'indirizzo IP viene modificata per una distribuzione di Lync Server 2013, ad esempio la modifica da IPv4 a stack doppio o da doppio stack a IPv6, non tutti i componenti server raccolgono la modifica della configurazione fino a quando non vengono riavviati i servizi.

**Soluzione alternativa**

Per ovviare a questo problema, riavviare i servizi Lync Server dopo aver modificato la configurazione dell'indirizzo IP per la distribuzione. A tale scopo, eseguire i cmdlet seguenti in Lync Server Management Shell:

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Il cmdlet per le transazioni sintetiche per le conferenze telefoniche con accesso esterno non è più disponibile nel Management Pack di Lync Server 2013

**Problema**

Il cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** non è più disponibile in Lync Server 2013 Management Pack.

**Soluzione alternativa**

Utilizzo del cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** è supportato solo internamente a un'organizzazione.

Gli amministratori possono continuare a utilizzare il cmdlet in Lync Server Management Shell per la risoluzione dei problemi. Se necessario, un'organizzazione può anche sviluppare un Management Pack privato per eseguire il cmdlet internamente.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>Il servizio di registrazione centralizzato si interrompe se il traffico di rete viene interrotto quando i file di registro vengono copiati nella condivisione di rete

**Problema**

Quando il servizio di registrazione centralizzato è configurato per l'utilizzo di un percorso di rete (il valore del parametro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** è un percorso UNC valido), i file di registro memorizzati nella cache vengono copiati nella condivisione di rete. Se si verifica un'interruzione del traffico di rete durante la copia dei file, si verificherà un'eccezione che provocherà l'arresto del servizio di registrazione centralizzato.

Il servizio è configurato per il riavvio automatico fino a tre volte, quindi il servizio si riprenderà dalle prime tre eccezioni.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema. Per identificare il problema, monitorare il registro eventi per l'ID evento 7031 da "Service Control Manager" che registra quando il servizio "Lync Server di registrazione centralizzata" ha terminato in modo imprevisto. Se questo accade più di tre volte, riavviare manualmente il servizio utilizzando il cmdlet **Start-CsWindowService** .

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Gli elementi della coda del servizio di archiviazione devono essere importati manualmente

**Problema**

Lync Server 2013 archivia i dati relativi alle conferenze e alla messaggistica istantanea, ad esempio i messaggi archiviati e la registrazione dettagli chiamata (CDR), in un database di ogni Front End Server. I dati vengono archiviati nel database mentre vengono elaborati prima di essere recapitati alla destinazione prevista. Per migliorare le prestazioni, Lync Server 2013 Esporta periodicamente gli elementi della coda dal database locale che non vengono elaborati per un periodo di tempo prolungato e li salva nell'archivio file. Se l'archivio file non è disponibile, gli elementi vengono archiviati in ogni Front End Server. La stessa operazione si verifica per evitare la perdita di dati durante il failover del pool.

Durante l'operazione di esportazione, il servizio di archiviazione di Lync Server registra ogni fase del registro eventi con gli ID evento di 32075 (viene avviata l'operazione full Flush), 32076 (Full Flush è stato completato), 32082 (livello di manutenzione Flush è iniziato), 32083 (livello di manutenzione Flush completata), 32089 (si è verificato un errore a causa del riempimento del database). Questi dati non verranno automaticamente riportati nel sistema in modo da essere elaborati e recapitati alla destinazione finale (SQL Server o Exchange Server).

**Soluzione alternativa**

Per importare i dati nel sistema, gli amministratori dovranno utilizzare lo strumento ImportStorageServiceData in Lync Server Resource Kit, che consente di aggiungere i dati di nuovo nel sistema per essere elaborati e recapitati alla destinazione finale.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Le ricerche delle query Web della Rubrica non avranno esito positivo se il valore predefinito di UseNormalizationRules viene impostato su false.

**Problema**

Se il valore predefinito di UseNormalizationRules viene impostato su false, le ricerche di query Web della Rubrica non avranno esito positivo. Dopo la modifica del valore predefinito, gli utenti di Lync client non saranno in grado di utilizzare la query Web della Rubrica di Lync per cercare gli utenti.

**Soluzione alternativa**

Se il valore predefinito per UseNormalizationRules è impostato su false in modo che gli utenti possano utilizzare i numeri di telefono definiti in servizi di dominio Active Directory senza Lync Server 2013 che applica le regole di normalizzazione, risolvere il problema eseguendo le operazioni seguenti:

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire una delle operazioni seguenti:
    
      - Se la distribuzione include solo server Lync Server 2013, eseguire il seguente cmdlet a livello globale per modificare i valori di UseNormalizationRules e IgnoreGenericRules su true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se nella distribuzione è inclusa una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool Lync Server 2013 nella topologia:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendere che la replica CMS venga eseguita in tutti i pool.

4.  Modificare il file delle regole di normalizzazione del telefono per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Lync Server 2013. Se il file non è presente, creare un file vuoto denominato "\_società numeri\_\_di telefono di\_normalizzazione Rules. txt".

5.  Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.

6.  Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 nella distribuzione.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>L'evento di errore 21054 del server della Rubrica viene generato una volta al giorno per ogni pool Lync 2013

**Problema**

Lync Server 2013 Address Book Server genererà l'evento di errore 21054 una volta al giorno quando si eseguono le operazioni di manutenzione giornaliera. L'errore viene generato anche ogni volta che un amministratore esegue il cmdlet **Update-csAddressBook** , anche quando l'aggiornamento ha esito positivo. Tuttavia, questo evento di errore può essere ignorato senza problemi quando l'aggiornamento ha esito positivo.

**Soluzione alternativa**

Quando si verifica questo evento di errore, eseguire il cmdlet seguente:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Se il cmdlet segnala che non sono presenti oggetti non indicizzati o abbandonati, l'evento di errore 21054 può essere ignorato senza problemi.

Inoltre, l'indicatore di integrità chiave (KHI) "gli utenti della rubrica correttamente indicizzati" deve essere disattivato in System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Le richieste potrebbero non riuscire quando IPv6 è configurato in un pool di server perimetrali

**Problema**

Quando IPv6 è configurato in un pool di server perimetrali, alcune richieste al pool di server perimetrali potrebbero avere esito negativo.

**Soluzione alternativa**

Per ovviare a questo problema, non configurare un pool di server perimetrali con IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>Il cmdlet Invoke-csPoolFailback potrebbe avere esito negativo durante il failback del pool

**Problema**

Quando si tenta di eseguire il failover di un pool, il cmdlet **Invoke-csPoolFailback** potrebbe avere esito negativo con l'errore "Impossibile completare il processo di idratazione dopo ripetuti tentativi".

**Soluzione alternativa**

Per ovviare a questo problema, eseguire di nuovo il cmdlet e attendere che il cmdlet abbia esito positivo. Tenere presente che il processo di failback può richiedere alcuni minuti per il completamento. Possono essere necessari fino a 60 minuti per un pool con 20.000 utenti.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>La perdita di dati può verificarsi quando si aggiunge un front end server a un pool già esistente, ovvero ibrido, Skype for business online

**Problema**

È possibile che si verifichi questo problema in un ambiente in cui un pool ha più di un front end server e si riavvia uno dei Front End Server oppure si aggiunge un nuovo front end server che precedentemente non faceva parte del pool.

Gli utenti i cui dati vengono archiviati possono riscontrare una perdita di dati fino a quando non viene stabilita una distribuzione stabile dell'archiviazione dei dati per il pool. Questo periodo di potenziale perdita di dati è limitato a 15 minuti per le conversazioni da persona a persona e a 30 minuti per le conferenze.

**Soluzione alternativa**

Quando si esegue la manutenzione, invece di avviare Front End Server nel pool uno alla volta, è necessario eseguire il failover del pool in un altro pool e quindi effettuare le attività di manutenzione nei server. È inoltre possibile rendere il servizio non disponibile prima di eseguire le attività di manutenzione e quindi ripristinare la disponibilità al termine della manutenzione.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Gli amministratori non possono ottenere il numero di licenziatari utilizzando il cmdlet Get-CsClientAccessLicense

**Problema**

Gli amministratori non possono ottenere un utilizzo accurato della licenza client utilizzando il cmdlet **Get-CsClientAccessLicense** .

**Soluzione alternativa**

Per controllare il tipo di licenza del server, è possibile eseguire il cmdlet **Get-CsService** per recuperare i nomi di dominio completi (FDQNs) di tutti i database. Se il nome di dominio completo del server front end è uguale al nome di dominio completo del database back-end, la licenza è una licenza Standard Edition. In caso contrario, la licenza è una licenza Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>Il numero del Licenziatario client non è stato segnalato accuratamente

**Problema**

Quando si determinano i conteggi delle licenze client, è possibile che si verifichino le seguenti condizioni:

1.  **Conteggio delle licenze non accurato per gli utenti mobili**
    
    Il conteggio delle licenze si basa sul numero di indirizzi IP univoci per gli utenti basati su dispositivo. Il numero di licenze sarà limitato nei modi seguenti:
    
      - Le licenze verranno contate se l'indirizzo IP dell'utente cambia durante le sessioni di Lync. Ciò può verificarsi quando un utente si connette a Lync Server da più di una posizione con un client desktop.
    
      - Le licenze verranno sottovalutate se un utente si connette a un client per dispositivi mobili, perché non è possibile determinare l'indirizzo IP per il dispositivo.

2.  **Le licenze vengono conteggiate due volte per le chiamate PSTN (Public Switched Telephone Network) al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate a linee PSTN**
    
    Negli scenari seguenti verranno conteggiate due licenze aggiuntive invece di una, in quanto il numero di telefono e l'utente di Lync vengono conteggiati per determinare il numero di licenze utilizzate. Per ottenere dati di licenza accurati, rimuovere manualmente le licenze generate da un numero di telefono.
    
      - Una telefonata PSTN a Lync
    
      - Una chiamata Lync a una linea PSTN
    
      - Chiamata PSTN a Lync e quindi Lync inoltra la chiamata a una linea PSTN. Viene conteggiata una delle linee PSTN.

3.  **Non viene conteggiata una licenza per un telefono Lync connesso**
    
    Quando un utente utilizza un telefono con certificazione Lync, se il telefono entra e rimane connesso, mantenendo lo stato di accesso, il telefono non verrà conteggiato come utilizzo di una licenza se la query per le licenze si verifica dopo che il telefono è connesso.

4.  **Licenze conteggiate per i telefoni PSTN che partecipano alle conferenze**
    
    Quando un utente entra a far parte di una conferenza con un telefono PSTN, viene conteggiata una licenza per partecipare alla conferenza. Tuttavia, non è necessaria alcuna licenza per partecipare a una conferenza con un telefono PSTN.

**Soluzione alternativa**

1.  **Conteggio delle licenze non accurato per gli utenti mobili**
    
      - È possibile identificare manualmente gli indirizzi IP che appartengono allo stesso dispositivo e quindi rimuoverne uno nel conteggio delle licenze.
    
      - Non esiste alcuna soluzione per questo problema con i dispositivi mobili che si connettono al client Lync.

2.  **Le licenze vengono conteggiate due volte per le chiamate PSTN al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate a linee PSTN**
    
    Sarà necessario identificare manualmente il numero di telefono PSTN e rimuovere il conteggio delle licenze generato.

3.  **Non viene conteggiata una licenza per un telefono Lync connesso**
    
    È possibile configurare il telefono Lync per disconnettersi e quindi eseguire di nuovo l'accesso, a intervalli regolari, ad esempio ogni 3 mesi.

4.  **Licenze conteggiate per i telefoni PSTN che partecipano alle conferenze**
    
    È possibile identificare manualmente il numero di telefono PSTN utilizzato per partecipare alla conferenza e rimuovere la licenza generata dal numero di telefono.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo l'aggiornamento a Silverlight 5

**Problema**

Se si utilizza il pannello di controllo di Lync Server in un ambiente VMware, è possibile che il pannello di controllo di Lync Server smetta di funzionare dopo l'aggiornamento di Microsoft Silverlight alla versione 5.

**Soluzione alternativa**

Per risolvere questo problema, effettuare una delle operazioni seguenti:

  - Disinstallare Silverlight 5 e installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).

  - Accedere al pannello di controllo di Lync Server da un computer che non sia un computer virtuale VMware.
    
    A tale scopo, è possibile avviare il pannello di controllo di Lync Server dal menu **Start** di Windows nel server, se gli strumenti di amministrazione di Lync Server sono installati nel computer.
    
    È inoltre possibile accedere al pannello di controllo di Lync Server tramite un Web browser. L'URL sarà\<simile a FQDN\_\_\>del pool di front-end di https:///CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Le informazioni degli utenti nel servizio Rubrica non vengono aggiornate dopo che il nome distinto per l'utente è stato modificato in Active Directory

**Problema**

Se il nome distinto di un utente (noto anche come DN) viene modificato in servizi di dominio Active Directory, eventuali modifiche aggiuntive non verranno aggiornate nel servizio Rubrica (ABS). Questo non ha effetto sull'accesso o sulla presenza dell'utente, ma impedirà la comunicazione per l'utente se viene modificato anche l'indirizzo SIP, in quanto le ricerche restituiranno un indirizzo SIP obsoleto.

**Soluzione alternativa**

Per ovviare a questo problema, non modificare il DN di un utente. Se si ripristina il nome distinto per l'utente al valore precedente, gli aggiornamenti verranno riflessi nel servizio Rubrica.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Installazione

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>L'utilizzo di caratteri non ASCII può comportare la mancata avvio di Lync Server

**Problema**

Il programma di installazione avrà esito negativo se il nome della cartella di destinazione include caratteri non ASCII (inclusi UNICODE, set di caratteri a doppio byte (DBCS), UTF-8 e UTF-16). Inoltre, il programma di installazione può avere esito positivo, ma il server non verrà avviato se i caratteri non ASCII sono contenuti in una delle seguenti operazioni:

  - Nome computer

  - Nome di dominio

  - Nome utente

  - URI SIP dell'utente

  - Nome dell'account del servizio

**Soluzione alternativa**

Utilizzare solo caratteri ASCII nel nome della cartella di destinazione, del nome del computer, del nome di dominio, del nome utente, dell'URI SIP dell'utente e dei nomi degli account di servizio.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5" deve essere installato prima di installare Lync Server 2013

**Problema**

L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" (), descritto nell'articolo 264886[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)della Microsoft Knowledge base, deve essere installato prima di installare Lync Server 2013.

**Soluzione alternativa**

Scaricare e installare l'hotfix dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 non è in grado di installare la versione di Windows Server 2012 OS RTM di ITA

**Problema**

L'installazione di Lync Server 2013 ha esito negativo su ITA Windows Server 2012 a causa di un errore di installazione di Windows Fabric.

L'installazione di Windows Fabric ha esito negativo perché le tracce Fabric vengono create con il formato ora HH: MM: SS. Tuttavia, in ITA Windows Server, il formato dell'ora è HH. MM.SS.

**Soluzione alternativa**

Per ovviare a questo problema, aggiornare il registro di sistema prima di installare Lync Server 2013. La chiave del registro di sistema che deve essere aggiornata è\_:\\gli utenti di HKEY. STimeFormat\\internazionale\\del\\pannello di controllo predefinito. Per modificare il valore di sTimeFormat in HH: mm: SS, utilizzare l'interfaccia della riga di comando di Windows PowerShell come indicato di seguito:

1.  Avviare Windows PowerShell ed eseguire i cmdlet seguenti:
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Per visualizzare il valore corrente, eseguire il cmdlet seguente:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Prendere nota del valore corrente per sTimeFormat in modo che possa essere ripristinato al termine dell'installazione.

3.  Per impostare il nuovo valore, eseguire il cmdlet seguente:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Dopo che Lync Server 2013 è stato installato correttamente, ripristinare il valore originale di sTimeFormat eseguendo il cmdlet seguente:
    
        - Set-ItemProperty $a-Name sTimeFormat-value "<valore annotato al passaggio 3. sopra> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilità

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problemi relativi ai client mobili durante il processo di failover del server

**Problema**

Quando un server Lync ha esito negativo e il processo di failover inizia, i problemi seguenti possono influire sugli utenti dei client mobili:

  - Nessuna chiamata o segnale di Lync in arrivo per un massimo di 10 minuti dopo l'inizio del failover.

  - Non è in grado di accettare le richieste chat in arrivo

  - Non è possibile partecipare a riunioni se il server non riuscito è il server principale dell'utente

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema. Una volta completata la procedura di failover, la funzionalità normale verrà ripristinata.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Se un utente mobile rifiuta una chiamata in arrivo da un altro endpoint Lync, la chiamata viene visualizzata come una conversione persa nei client mobili di Lync

**Problema**

Se un utente mobile rifiuta una chiamata in arrivo e la chiamata ha avuto origine da un altro endpoint Lync, la chiamata viene visualizzata come una conversazione persa nel client mobile di Lync anziché una chiamata nell'elenco delle chiamate di dispositivo.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Il client per dispositivi mobili potrebbe non visualizzare il nome visualizzato di un contatto federato durante la ricerca di contatti

**Problema**

Il nome visualizzato per i contatti federati potrebbe non essere visualizzato in alcuni scenari, ad esempio durante la ricerca di un contatto federato nell'elenco dei contatti. Questo problema può verificarsi quando non è presente alcuna sottoscrizione di presenza attiva per il contatto dal client di Lync mobile.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>Nel client per dispositivi mobili, le informazioni sull'invito e sul timestamp sono mancanti da una conversazione persa che è un invito a una conferenza

**Problema**

Nel client per dispositivi mobili, quando una conversazione persa è un invito a una conferenza, le informazioni sull'invito e sul timestamp sono mancanti dal messaggio di conversazione persa.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Gli utenti di client mobili che effettuano chiamate tramite VoIP non sono in grado di lasciare la segreteria telefonica per gli utenti la cui segreteria telefonica è configurata in Exchange 2010 o versioni precedenti

**Problema**

Se un utente di client mobili utilizza VoIP per effettuare chiamate, l'utente non sarà in grado di lasciare messaggi di segreteria telefonica per gli utenti configurati per l'utilizzo della segreteria telefonica in Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.

**Soluzione alternativa**

Per ovviare a questo problema, utilizzare Exchange 2010 con SP1 o versione successiva di Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Quando si utilizza il blocco con l'URL per la configurazione della versione client sui client mobili, potrebbe essere visualizzato un messaggio di errore non corretto

**Problema**

Quando si utilizza il **blocco con l'URL** per la configurazione della versione client nei client mobili, è possibile che venga visualizzato un messaggio di errore non corretto quando la versione client non è supportata.

**Soluzione alternativa**

Per ovviare a questo problema, configurare la configurazione della versione client in modo da utilizzare **Block** anziché **Block con URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Conferenza

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Il software antivirus in esecuzione nei server front end di Lync Server 2013 può causare il riciclo dei domini applicazione, che interrompe temporaneamente il servizio per Lync Web App 2013, Lync Mobile 2010 e i client Lync Mobile 2013

**Problema**

Il software antivirus può attivare il riavvio del dominio dell'applicazione, che può comportare la perdita dello stato del servizio Lync Mobility Service 2013 e delle applicazioni client API Web per le comunicazioni unificate (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013).

**Soluzione alternativa**

Per ovviare a questo problema, escludere le cartelle contenenti componenti Web e .NET Framework dall'analisi antivirus. Per ulteriori informazioni, vedere l'articolo 312592 della Microsoft Knowledge Base "PRB: riavviamenti di applicazioni casuali con" applicazione di riavvio "in ASP.NET, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)" at.

Le cartelle seguenti devono essere escluse:

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX EXT

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA EXT

  - % WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>I controlli ActiveX o il supporto nativo di XMLHTTP devono essere abilitati in Windows Internet Explorer per partecipare a conferenze con esito positivo

**Problema**

Se un utente ha disabilitato sia i controlli ActiveX sia il supporto nativo di XMLHTTP nelle impostazioni del browser Internet di Windows Internet Explorer, l'utente non sarà in grado di partecipare a una riunione se Internet Explorer è selezionato come browser predefinito.

**Soluzione alternativa**

Abilitare i controlli ActiveX o "supporto nativo di XMLHTTP" in Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Il servizio Web Conferencing di Lync Server non può essere ripristinato dalla modalità critica

**Problema**

Se la modalità critica è attivata per l'archiviazione, in caso di errori di sistema, la modalità critica inizierà e le conferenze non funzioneranno più per i partecipanti. Dopo che l'amministratore ha risolto gli errori del sistema, ad esempio la risoluzione di un problema di database, il servizio di conferenza dati non viene ripristinato automaticamente e l'amministratore deve riavviare manualmente il servizio di conferenza per le conferenze da riprendere.

**Soluzione alternativa**

Un amministratore deve riavviare manualmente il servizio di conferenza dopo che è stato risolto il problema del sistema.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Il servizio Web Conferencing ignora il proxy HTTP per i server Office Web App esterni

**Problema**

Se è stato distribuito un server Office Web Apps esterno al servizio Web Conferencing (ovvero un server che non è presente nella rete aziendale interna) in Internet, la rete perimetrale e il servizio Web Conferencing richiede un proxy HTTP per connettersi a questo, il L'individuazione del server Office Web Apps avrà esito negativo. Il servizio Web Conferencing ignora l'impostazione del proxy HTTP, come definito in Generatore di topologie per il programma di installazione del server Office Web Apps. Di conseguenza, il client Lync non sarà in grado di eseguire la condivisione di Microsoft PowerPoint 2010 con altri partecipanti alla conferenza. Se si sta installando Lync Server in locale e si configura anche il server Office Web Apps in locale nella rete interna, non è necessaria una configurazione proxy.

**Soluzione alternativa**

L'unica soluzione alternativa consiste nel non disporre di una configurazione di distribuzione che richiede l'utilizzo del proxy HTTP per comunicare con un server Office Web Apps esterno.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>L'aggiunta di video a una conferenza di un provider di servizi di audioconferenza non è supportata

**Problema**

L'aggiunta di un video non è supportata se l'utente è aggiunto a una conferenza di un provider di servizi di audioconferenza per l'audio.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologie con IPv6 abilitato forzare l'aggiornamento automatico del plug-in Silverlight di Lync Web App per garantire che le funzionalità di condivisione dello schermo possano funzionare da Lync Web App

**Problema**

Quando una topologia è configurata con IPv6 abilitato, gli utenti non possono condividere la propria schermata dal client Lync Web App se è già installata una versione precedente del plug-in di condivisione dello schermo.

**Soluzione alternativa**

Per forzare un aggiornamento alla versione più recente del plug-in di condivisione dello schermo quando si accede a una riunione tramite Lync Web App, modificare il valore di **MinSupportedBuildVersion** da "4.0.7457.0" a "4.0.7577.380" in entrambi i file seguenti:

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\int\\plugins\\client ReachAppShPluginProperties. XML

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\ext\\client\\plugins ReachAppShPluginProperties. XML

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>In alcuni casi, un client Lync in esecuzione su un computer configurato per l'utilizzo di IPv4 e IPv6 dual stack potrebbe non supportare funzionalità che si basano sulla subnet IP del computer, ad esempio E911, bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione

<div class="">


> [!NOTE]  
> Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Quando un client Lync è in esecuzione in un computer abilitato per IPv4 e IPv6 dual stack e basato sulla risoluzione DNS del server proxy, il client può utilizzare l'indirizzo IPv6 del computer per l'accesso. Dopo tale operazione, il client Lync supporterà solo le funzionalità supportate per IPv6, che esclude E911, il bypass multimediale, il controllo di ammissione di chiamata e il routing in base alla posizione.

**Soluzione alternativa**

Per ovviare a questo problema, disabilitare il supporto IPv6 sul computer client.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Se VoIP aziendale non è configurato per un utente, l'utente dovrà utilizzare il formato E164 per effettuare una chiamata in uscita da una conferenza.

**Problema**

Se VoIP aziendale non è configurato per un utente, sarà necessario utilizzare il formato E164 per effettuare una chiamata in uscita da una conferenza. Se non si utilizza il formato E164, l'utente non sarà in grado di eseguire la chiamata in uscita dalla conferenza.

**Soluzione alternativa**

Per ovviare a questo problema, gli utenti che non sono abilitati per VoIP aziendale devono eseguire la chiamata in uscita da una conferenza utilizzando numeri nel formato E164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Presenza

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non è rifiutato quando dovrebbe esserlo.

**Problema**

Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non è rifiutato quando dovrebbe esserlo.

**Soluzione alternativa**

Per ovviare a questo problema, è possibile disattivare l'archivio contatti unificato per l'utente. A tale scopo, eseguire i cmdlet seguenti:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Ad esempio:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Gli utenti di Office Communications Server 2007 R2 ospitati in locale non sono in grado di visualizzare lo stato di presenza degli utenti di Skype for business online nelle distribuzioni ibride-ibrido

**Problema**

È possibile che il problema si verifichi in una distribuzione ibrida quando si utilizza un Director di Lync Server 2013.

Lo stato di presenza per gli utenti ospitati in Skype for business online viene visualizzato come presenza sconosciuta per gli utenti locali. Inoltre, gli utenti ospitati in Skype for business online non sono in grado di visualizzare lo stato di presenza per gli utenti locali di Office Communications Server R2.

**Soluzione alternativa**

Per ovviare a questo problema, cambiare il server principale (msRTCSIP-presencehomeserver) degli utenti di Skype for business online in modo che puntino a un pool locale di Lync Server 2013 anziché al server Director di Lync 2013. È possibile modificare questa impostazione nel front end server locale.

Questa soluzione consente di visualizzare correttamente lo stato di presenza degli utenti ospitati in Office Communications Server 2007 R2 per gli utenti di Skype for business online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Applicazione Response Group, applicazione Parcheggio di chiamata e raccolta di chiamate di gruppo

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Un chiamante potrebbe udire un secondo di musica in attesa durante la creazione di una chiamata con la parte di recupero

<div class="">


> [!NOTE]  
> Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Quando viene recuperata una chiamata tramite il prelievo delle chiamate di gruppo, il chiamante può udire un secondo di musica durante l'esecuzione della chiamata con la parte Retriever.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Un agente di Response Group può accedere e disconnettersi tramite una console di agente Lync Server 2010 ai soli gruppi di agenti formali di Lync Server 2010.

**Problema**

Un agente di Response Group di Lync Server 2013 può accedere e disconnettersi tramite una console di agente di Lync Server 2010 ai soli gruppi di agenti formali di Lync Server 2010. Nella console di agente Lync Server 2010 gli utenti possono visualizzare solo il Response Group di Lync Server 2010 a cui appartengono. Non è possibile visualizzare nessuno dei gruppi di risposta di Lync Server 2013 a cui appartengono.

**Soluzione alternativa**

Se l'agente Response Group è un utente di Lync Server 2013 e parte di un gruppo di agenti formali di Lync Server 2013, l'utente deve accedere alla console di agente di Lync Server 2013 direttamente tramite un collegamento Web in un browser per accedere e disconnettersi dai gruppi di agenti di Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Un agente di Response Group di Lync Server 2010 non è in grado di effettuare chiamate per conto di un Response Group di Lync Server 2013

**Problema**

Un utente di Lync Server 2010 che è un agente di un Response Group di Lync Server 2013 non è in grado di effettuare una chiamata per conto del Response Group. Il Response Group di Lync Server 2013 non sarà disponibile nel client Lync per effettuare una chiamata.

**Soluzione alternativa**

Per ovviare a questo problema, è necessario spostare l'utente di Lync Server 2010 in Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>La rimozione di un Response Group da Lync Server 2010 dopo che è stata eseguita la migrazione a Lync Server 2013 impedirà al Response Group di accettare le chiamate in arrivo

**Problema**

Se un Response Group di cui è stata eseguita la migrazione da Lync Server 2010 a Lync Server 2013 è stato rimosso da Lync Server 2010 tramite il pannello di controllo di Lync Server o Lync Server Management Shell, il Response Group in Lync Server 2013 smetterà di ricevere chiamate in arrivo.

**Soluzione alternativa**

Per ovviare a questo problema, non rimuovere i Response Group da Lync Server 2010 che sono stati migrati da Lync Server 2010 a Lync Server 2013.

Se il Response Group è già stato rimosso, è necessario ridistribuirlo in Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Quando un nuovo flusso di lavoro gestito è impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo

**Problema**

Quando un nuovo flusso di lavoro gestito è impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo. Questo problema si verifica quando il flusso di lavoro è impostato su inattivo quando viene creato, ma non influisce su un flusso di lavoro modificato per impostarlo su inattivo dopo che è stato distribuito.

**Soluzione alternativa**

Durante la creazione e la distribuzione di un flusso di lavoro, impostare il flusso di lavoro come attivo e quindi distribuirlo. Dopo la distribuzione del flusso di lavoro, è possibile modificare il flusso di lavoro e impostarlo su inattivo.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>Se il Response Group è stato importato nel pool di backup, la rimozione di un Response Group dal pool del proprietario impedirà al gruppo di risposta del pool di backup di accettare le chiamate in arrivo durante il failover.

**Problema**

Se un Response Group di proprietà del pool primario è stato importato nel pool di backup senza sovrascrivere il proprietario e il Response Group è stato rimosso dal pool di proprietari, il Response Group nel pool di backup non accetterà chiamate in arrivo durante il failover.

**Soluzione alternativa**

Sarà necessario ridistribuire il Response Group nel pool primario. Sarà quindi necessario esportare la configurazione di Response Group dal pool primario e importarla di nuovo nel pool di backup.

È inoltre possibile ricreare il Response Group nel pool di backup. In questo caso, il pool di backup sarà il pool proprietario del Response Group.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Non è possibile recuperare una chiamata parcheggiata dall'applicazione Parcheggio di chiamata se la richiesta di recupero viene fatta per conto di un Response Group

**Problema**

Quando si verificano le condizioni seguenti, una richiesta di recupero per una chiamata parcheggiata avrà esito negativo:

  - Un agente fa parte di un Response Group anonimo

  - L'agente tenta di recuperare una chiamata parcheggiata dall'applicazione Parcheggio di chiamata tramite il Response Group anonimo

  - L'agente tenta di recuperare la chiamata componendo il numero dell'orbita tramite l'opzione chiama per conto di o tramite la stessa opzione nel client di operatore di Lync

**Soluzione alternativa**

Non vi sono soluzioni alternative per questo problema. La chiamata parcheggiata deve essere recuperata senza farlo per conto di un Response Group.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Pannello di controllo di Lync Server, Generatore di topologie e Strumento di pianificazione

<div>

## <a name="planning-tool-limitations"></a>Limitazioni dello strumento di pianificazione

<div class="">


> [!NOTE]  
> Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Durante la pianificazione della distribuzione, lo strumento di pianificazione presenta le limitazioni seguenti:

  - È supportato un massimo di 10 siti centrali

  - Ogni sito centrale può avere un massimo di 14 siti di succursale

  - Ogni sito centrale può avere un massimo di 240.000 utenti

Inoltre, quando si calcola la topologia consigliata, lo strumento di pianificazione non include i valori seguenti:

  - Il numero di utenti ospitati online

  - La percentuale di utenti abilitati per la Federazione XMPP

  - Percentuale di utenti che utilizzano Lync Web App

**Soluzione alternativa**

Non esiste alcuna soluzione per questi problemi. Per ulteriori informazioni sullo strumento di pianificazione, vedere [progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>Lo strumento di pianificazione potrebbe non utilizzare gli indirizzi IP definiti in precedenza per la rete perimetrale quando si aggiornano le opzioni

**Problema**

Dopo aver completato la progettazione utilizzando lo strumento di pianificazione, se si apportano modifiche alle opzioni di rete Edge, è possibile aggiungere indirizzi IP aggiuntivi alla struttura anziché aggiornare gli indirizzi IP esistenti. Ciò può verificarsi quando si visualizzano i dettagli del diagramma della rete perimetrale, selezionare **fare clic qui per aggiornare le opzioni**e quindi nella finestra di dialogo Opzioni di configurazione selezionare rete perimetrale seleziona **desidero utilizzare gli stessi nomi FQDN e indirizzi IP, ma porte diverse per i servizi perimetrali nel server perimetrale**. L'applicazione di eventuali modifiche può comportare l'aggiunta di nuovi indirizzi IP e server perimetrali alla struttura.

**Soluzione alternativa**

Non esiste alcuna soluzione per questo problema in questo momento.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Nel pannello di controllo di Lync Server, "spostare tutti gli utenti nel pool" potrebbe non funzionare come previsto

**Problema**

Quando si utilizza il pannello di controllo di Lync Server per spostare tutti gli utenti da un pool a un altro in un ambiente di Active Directory complesso, ad esempio uno con più controller di dominio e domini padre/figlio, potrebbe essere restituito un messaggio di errore che indica che l'utente specificato non è un utente legacy, utilizzare invece il cmdlet Move-CsUser. Questo è il risultato di tempi di replica più lunghi in ambienti di Active Directory complessi.

**Soluzione alternativa**

Per risolvere questo problema, effettuare una delle operazioni seguenti:

  - Utilizzare filtri nel pannello di controllo di Lync Server per cercare gli utenti legacy, selezionarli e quindi utilizzare il **comando Sposta utenti selezionati nel pool** anziché **spostare tutti gli utenti nel pool**.

  - Utilizzare Lync Server Management Shell per spostare gli utenti legacy in batch utilizzando i cmdlet di Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo che il plug-in del browser Microsoft Silverlight è stato aggiornato alla versione 5

**Problema**

Se si utilizza il pannello di controllo di Lync Server in un ambiente VMware, è possibile che il pannello di controllo di Lync Server smetta di funzionare dopo aver aggiornato Silverlight alla versione 5.

**Soluzione alternativa**

Per risolvere questo problema, effettuare una delle operazioni seguenti:

  - Disinstallare Silverlight 5 e quindi installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).

  - Aprire il pannello di controllo di Lync Server da un computer che non sia un computer virtuale VMware.
    
    Per aprire il pannello di controllo di Lync Server da un computer remoto, installare gli strumenti di amministrazione di Lync Server nel computer e quindi avviare il pannello di controllo di Lync Server dal menu **Start** di Windows.
    
    È inoltre possibile aprire il pannello di controllo di Lync Server digitando l'URL in un Web browser. L'URL sarà\<simile a FQDN\_\_\>del pool di front-end di https:///CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Un amministratore non è in grado di eseguire il cmdlet Uninstall-csMirrorDB dopo aver rimosso il database del mirroring in Generatore di topologie

**Problema**

Quando un amministratore disabilita un database del mirroring in Generatore di topologie e quindi Elimina il database del mirroring in Generatore di topologie, nell'elenco da fare viene visualizzato un messaggio che consente all'amministratore di eseguire il cmdlet **Uninstall-csMirrorDatabase** per rimuovere il mirroring da SQL Server. Quando l'amministratore tenta di eseguire il cmdlet, ha esito negativo.

**Soluzione alternativa**

Per rimuovere il mirroring SQL di un pool in Generatore di topologie, è innanzitutto necessario utilizzare un cmdlet per rimuovere il mirror in SQL Server. È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Il parametro *DropExistingDatabasesOnMirror* consente di eliminare dal mirror i database coinvolti. Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:

1.  In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

2.  Cancellare il **mirroring dell'archivio SQL** e fare clic su **OK**.

3.  Pubblicare la topologia.

<div class="">


> [!IMPORTANT]  
> Ogni volta che si apportano modifiche a una relazione di mirroring del database back-end, è necessario riavviare tutti i Front End Server nel pool.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Gli errori di convalida vengono restituiti in Generatore di topologie quando un amministratore tenta di rimuovere una distribuzione con un pool Front end a cui è associato un archivio di controllo.

**Problema**

Se un amministratore tenta di utilizzare il comando **Rimuovi distribuzione** in Generatore di topologie per rimuovere una distribuzione che include un pool Front end con un archivio di controllo associato, viene visualizzato un errore di convalida in Generatore di topologie e l'azione non verrà eseguita.

**Soluzione alternativa**

Per risolvere questo problema, effettuare una delle operazioni seguenti:

  - Rimuovere l'archivio di controllo prima di tentare di rimuovere la distribuzione.

  - Aggiungere un archivio di controllo per il pool Front end e quindi rimuoverlo.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>Le informazioni sulla distribuzione del server Chat persistente sono incoerenti tra lo strumento di pianificazione e il generatore di topologie

**Problema**

Quando Lync Server 2013, lo strumento di pianificazione genera il diagramma della topologia del sito per una distribuzione di server Chat persistente con ripristino di emergenza abilitato, il diagramma della topologia del sito include più siti (fisici), con i server di chat persistente assegnati equamente a ogni sito. In Generatore di topologie, tutti i server di chat persistente sono rappresentati come appartenenti a un singolo sito (logico) e sono elencati nello stesso nodo del pool di Persistent Chat Server.

**Soluzione alternativa**

Attualmente, non si dispone di una soluzione alternativa per questo problema. L'utente deve analizzare l'output dello strumento di pianificazione per la distribuzione del server Chat persistente e modificare il piano per soddisfare le proprie esigenze specifiche.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localizzazione

<div>

## <a name="monitoring"></a>Monitoraggio

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>La procedura guidata per la distribuzione dei rapporti di monitoraggio Visualizza caratteri non corretti in determinate circostanze quando si utilizza la versione dell'Asia orientale di Lync Server

**Problema**

Quando si utilizza una versione dell'Asia orientale di Lync Server 2013, ad esempio cinese (semplificato), cinese (tradizionale), giapponese o coreano, in un sistema operativo in cui le impostazioni locali del sistema non sono impostate su una lingua dell'Asia orientale, la procedura guidata per la distribuzione dei rapporti di monitoraggio visualizzare i punti interrogativi o altri caratteri invece dei messaggi localizzati.

**Soluzione alternativa**

Per risolvere il problema, impostare le impostazioni locali per il sistema operativo e Lync Server 2013 sulla stessa lingua, in cui verranno visualizzati correttamente tutti i messaggi.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Pannello di controllo di Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>In alcuni casi, il primo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server scompare quando si fa clic sull'ultimo elemento della barra di spostamento superiore

**Problema**

Esistono tre casi noti in cui se si fa clic sull'ultimo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server, il primo elemento nella barra di spostamento superiore scomparirà:

  - Nella versione francese della pagina "Féderation et accès externe", l'elemento "Stratégie accès externe" scomparirà quando si fa clic su "Partenaires fédérés XMPP".

  - Nella versione in lingua tedesca, nella pagina "client", l'elemento "Clientversionskonfiguration" scompare quando si fa clic su "se".

  - Nella versione russa, nella pagina "Конфигурация сети", la voce "Глобально" scompare quando si fa clic su "Маршрут региона".

**Soluzione alternativa**

Per ovviare a questo problema, aggiornare la pagina del pannello di controllo di Lync Server nel browser. La pagina verrà caricata nel browser con tutti gli elementi nella barra di spostamento superiore visualizzata.

</div>

</div>

<div>

## <a name="address-book"></a>Rubrica

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>L'indicizzazione nella Rubrica non funziona come previsto in alcune lingue

<div class="">


> [!NOTE]  
> Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

Se le proprietà di un utente contengono un campo indicizzato e questo campo contiene solo caratteri che non possono essere indicizzati, l'utente non verrà visualizzato nelle ricerche eseguite nella rubrica.

Non è possibile indicizzare i caratteri e le impostazioni locali seguenti:

  - Caratteri cirillici, greci e armeni in maiuscolo

  - Caratteri accentati in maiuscolo

  - Thai

  - Lao

  - Myanmar

  - Devanagari

  - Etiope

  - Tibetano

  - Bengali

  - Gujarati

  - Telugu

  - Tutti gli altri script indiani

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, utilità di pianificazione Web e componenti Web

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Il fallback della lingua per alcune lingue in Lync Web Scheduler, accesso esterno, Join Launcher, Persistent Chat Room Management e OCTab potrebbe non funzionare come previsto

**Problema**

Quando si selezionano impostazioni locali neutre in un Web browser (in Internet Explorer, ad esempio, il nome della lingua senza ulteriori specifiche, \[come\]"norvegese no", anziché le impostazioni locali che specificano la lingua, lo script e le impostazioni locali (ad esempio \["norvegese,\]Bokmål (Norvegia) NB-no") potrebbe causare un comportamento di visualizzazione imprevisto per alcune lingue in Lync Web Scheduler, accesso esterno, Join Launcher, Persistent Chat Room Management e OCTab. Ad esempio, gli utenti potrebbero visualizzare la pagina in lingua inglese quando viene selezionata una delle lingue seguenti:

  - Norvegese

  - Portoghese

  - Serbo

**Soluzione alternativa**

Se si desidera selezionare una lingua con impostazioni locali neutre, assicurarsi sempre di aggiungere la lingua a una determinata lingua (con codice di script e/o di paese) come ulteriore linguaggio nell'elenco delle preferenze della lingua del browser.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>È disponibile un supporto limitato per le impostazioni locali azeri e Usbeco quando si utilizza Lync Web Scheduler, accesso esterno, Join Launcher, gestione chat room Persistent e OCTab in alcuni Web browser

<div class="">


> [!NOTE]  
> Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Quando si utilizza Internet Explorer 8 o Internet Explorer 9 e si imposta la lingua del browser su Azero (alfabeto latino) o Usbeco (alfabeto latino), le pagine di avvio di accesso esterno e join verranno visualizzate in inglese o nella lingua preferita impostata nel browser.

Quando si utilizzano i browser Firefox o Chrome e si imposta la lingua del browser su Azero (alfabeto latino) o Usbeco (alfabeto latino), Lync Web App, Lync Web Scheduler e RGS OCTab verranno visualizzati in inglese o la lingua preferita per il browser.

Le impostazioni locali dell'Uzbeco (alfabeto latino) non sono supportate nel browser Safari.

**Soluzione alternativa**

Non esiste una soluzione alternativa per questi problemi.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>La freccia a discesa mancante per l'elenco "partecipa a riunione da" nella versione rumena di Lync Web App

**Problema**

Quando un utente che utilizza la versione rumena di Lync Web App esegue i passaggi seguenti, la freccia a discesa non viene visualizzata per l'elenco a discesa **partecipa a riunione** :

1.  Selezionare **Ricordami su questo computer** nella scheda **generale** .

2.  Selezionare la scheda **telefono** .

3.  Fare clic sull'elenco a discesa per **partecipare a una riunione**.
    
    Gli utenti non vedranno una freccia che indica che sono disponibili altre opzioni rispetto all'impostazione predefinita di **Lync Web App**, tra cui: **non aggiungere audio** (in Romeno, "nu se asociaža la Componenta audio") e **nuovo numero**"(in Romeno," Număr Nou ").

**Soluzione alternativa**

Anche se la freccia di questo elenco a discesa non è visualizzata, gli utenti possono comunque selezionare le impostazioni aggiuntive nell'elenco facendo clic sul valore predefinito.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Quando si utilizza la versione turca di Lync Web Scheduler, non è possibile salvare una riunione quando si utilizza l'opzione "persone scelte dall'utente" in "chi è un relatore"

**Problema**

Quando si crea o si modifica una riunione nella versione turca dell'utilità di pianificazione Web di Lync, l'opzione "persone scelte" in "chi è un relatore" non è supportata. Quando questa opzione è selezionata, la riunione non può essere salvata. Viene invece visualizzato un messaggio di errore che indica che non è possibile rendere relatori una o più persone.

**Soluzione alternativa**

Per ovviare a questo problema, gli utenti possono utilizzare l'opzione predefinita "persone della mia azienda" o qualsiasi altra scelta, ad esempio "solo organizzatore" o "tutti compresi quelli esterni alla propria azienda". L'organizzatore può abbassare di livello o promuovere i ruoli corretti in un secondo momento, dopo aver partecipato alla riunione.

In alternativa, gli utenti che capiscono un'altra lingua possono cambiare la selezione della lingua nel browser in una delle altre lingue supportate da 43 e tentare di utilizzare l'opzione "persone scelte dall'utente".

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Copyright

Questo documento supporta una versione preliminare di un prodotto software che può essere modificato in modo sostanziale prima del rilascio finale commerciale ed è l'informazione riservata e proprietaria di Microsoft Corporation. Viene divulgato in base a un accordo di non divulgazione tra il destinatario e Microsoft. Microsoft esclude ogni garanzia espressa o implicita in questo documento. Le informazioni contenute in questo documento, tra cui l'URL e altri riferimenti al sito Internet, sono soggette a modifiche senza preavviso. I rischi conseguenti all'uso o ai risultati dell'uso di questo documento sono a carico degli utenti. Se non diversamente specificato, le società, le organizzazioni, i prodotti, i nomi di dominio, gli indirizzi di posta elettronica, i loghi, le persone, i luoghi e gli eventi descritti negli esempi riportati sono fittizi. Nessuna associazione con una società, un'organizzazione, un prodotto, un nome di dominio, un indirizzo di posta elettronica, un logo, una persona, un luogo o un evento reale è intenzionale o deve essere dedotto. Il rispetto di tutte le applicabili leggi in materia di copyright è esclusivamente a carico dell'utente. Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, su fotocopia, come registrazione o altro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.

Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright o altra proprietà intellettuale.

© 2012 Microsoft Corporation. Tutti i diritti riservati.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server sono marchi o marchi registrati di Microsoft Corporation negli Stati Uniti e/o negli altri paesi/aree geografiche.

Tutti gli altri marchi citati nel presente documento sono di proprietà dei rispettivi titolari.

</div>

</div>

<span> </span>

</div>

</div>

</div>

