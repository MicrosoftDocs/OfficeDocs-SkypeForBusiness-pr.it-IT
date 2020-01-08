---
title: 'Lync Server 2013: Note sulla versione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Note sulla versione per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-08_

Introduzione alle note sulla versione di Lync Server 2013. Per informazioni sui problemi noti relativi a Lync Server 2013, vedere questo file.

<div>

## <a name="about-this-document"></a>Informazioni sul documento

Questo documento contiene informazioni importanti che è necessario conoscere prima di distribuire e utilizzare Lync Server 2013. Per informazioni dettagliate su Lync Server 2013, vedere la documentazione di [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

Questo documento contiene le sezioni seguenti:

  - Client Lync 2013

  - Lync Server

  - Installazione

  - Mobilità

  - Servizi di conferenza

  - VoIP aziendale

  - Icone di presenza

  - Applicazione Response Group e applicazione Parcheggio di chiamata

  - Pannello di controllo, Generatore di topologie e Strumento di pianificazione di Lync Server

  - Localizzazione

  - Copyright

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Client Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>Il trasferimento di un file in un messaggio istantaneo non riesce se il file è aperto in un'altra applicazione

**Problema**

Se si tenta di trasferire un file, ad esempio un documento di Word, inserendolo in un messaggio istantaneo a un altro utente di Lync, il trasferimento verrà visualizzato correttamente, ma potrebbe effettivamente non riuscire a trasferire il file. Un'icona per il tipo di file verrà visualizzata nel client Lync, ma il file non può essere aperto dal destinatario previsto. Non viene visualizzato alcun messaggio di errore che informa che il trasferimento non è stato eseguito correttamente.

**Soluzione**

Per risolvere il problema, chiudere il file aperto o l'applicazione aperto prima di provare a trasferire il file in un messaggio istantaneo.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Se la replica dei dati del servizio di archiviazione di Lync Server non riesce, gli amministratori dovranno verificare i contatori delle prestazioni per gli elementi della coda del servizio di archiviazione

**Problema**

Il servizio di archiviazione di Lync Server usa il tessuto Windows per la replica. Se i dati vengono eliminati in un server front-end principale, ma l'eliminazione in un server front-end secondario non riesce, ad esempio se si verifica un arresto o un errore imprevisto nel server front-end, i dati possono essere lasciati indietro e "orfani". I dati orfani possono causare prestazioni in grado di degradare e sprecare spazio su disco.

**Soluzione**

Per aggirare il problema, se gli eventi LYSS\_DB\_Space\_used\_Error (ID = 32058) e Lyss\_DB\_Space\_used\_Critical (ID = 32059) vengono generati nel log eventi, gli amministratori dovrebbero controllare il contatore delle prestazioni nel server front-end in **ls: Lyss-API del servizio** di archiviazione con un nome di **Lyss-numero corrente di elementi della coda non aggiornati del servizio di archiviazione**. Se questo contatore delle prestazioni ha un valore elevato, ad esempio maggiore di 50000, l'amministratore deve eseguire lo strumento CleanuUpStorageServiceData. exe nel Resource Kit di Lync Server 2013, che eliminerà tutti i dati orfani dal pool. Per informazioni dettagliate sullo strumento, vedere la documentazione di Lync Server 2013 Resource Kit.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Ogni volta che viene modificata la configurazione di un indirizzo IP per un server o un pool, è necessario riavviare i servizi di Lync Server

**Problema**

Quando la configurazione dell'indirizzo IP viene modificata per una distribuzione di Lync Server 2013, ad esempio la modifica da IPv4 a dual stack o da doppio stack a IPv6, non tutti i componenti del server prelevano la modifica della configurazione finché i servizi non vengono riavviati.

**Soluzione**

Per risolvere il problema, riavviare i servizi Lync Server dopo la modifica della configurazione dell'indirizzo IP per la distribuzione. A questo scopo, eseguire i cmdlet seguenti in Lync Server Management Shell:

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Il cmdlet di transazione sintetica per i servizi di conferenza telefonica con accesso esterno non è più disponibile in Lync Server 2013 Management Pack

**Problema**

Il cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** non è più disponibile nel Management Pack di Lync Server 2013.

**Soluzione**

Uso del cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** è supportato solo internamente a un'organizzazione.

Gli amministratori possono continuare a usare il cmdlet in Lync Server Management Shell per scopi di risoluzione dei problemi. Se necessario, un'organizzazione può anche sviluppare un Management Pack privato per eseguire il cmdlet internamente.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>Il servizio di registrazione centralizzato si arresta se il traffico di rete viene interrotto quando i file di log vengono copiati in condivisione di rete

**Problema**

Quando il servizio di registrazione centralizzato è configurato per l'uso di un percorso di rete (il valore del parametro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** è un percorso UNC valido), i file di log memorizzati nella cache vengono copiati nella condivisione di rete. Se si verificano interruzioni nel traffico di rete mentre i file vengono copiati, si verificherà un'eccezione che causerà l'interruzione del servizio di registrazione centralizzata.

Il servizio è configurato per il riavvio automatico di un massimo di tre volte, in modo che il servizio recuperi le prime tre eccezioni.

**Soluzione**

Non c'è soluzione alternativa per questo problema. Per identificare il problema, monitorare il log eventi per l'ID evento 7031 da "Gestione controllo servizi" che registra quando il servizio "Lync Server Central Logging Service Agent" ha terminato in modo imprevisto. Se si verificano più di tre volte, riavviare manualmente il servizio usando il cmdlet **Start-CsWindowService** .

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Gli elementi della coda del servizio di archiviazione devono essere importati manualmente

**Problema**

Lync Server 2013 archivia i dati relativi alle conferenze e alla messaggistica istantanea, ad esempio i messaggi archiviati e la registrazione dei dettagli delle chiamate (CDR), in un database di ogni server front-end. I dati vengono archiviati nel database mentre vengono elaborati prima di essere recapitati alla destinazione desiderata. Per migliorare le prestazioni, Lync Server 2013 Esporta periodicamente gli elementi della coda dal database locale che non vengono elaborati per un periodo di tempo prolungato e li salva nell'archivio file. Se l'archivio file non è disponibile, gli elementi vengono archiviati in ogni server front-end. La stessa operazione si verifica per evitare la perdita di dati durante il failover del pool.

Durante l'operazione di esportazione, il servizio di archiviazione di Lync Server registra ogni fase del log eventi con gli ID evento di 32075 (viene avviata l'operazione di svuotamento completo), 32076 (il colore completo è completato), 32082 (livello di manutenzione a filo), 32083 (livello di manutenzione a filo) è completato), 32089 (lo svuotamento si è verificato a causa della compilazione del database). Questi dati non verranno automaticamente importati nel sistema per essere elaborati e recapitati alla destinazione finale (SQL Server o Exchange Server).

**Soluzione**

Per importare i dati nel sistema, gli amministratori dovranno usare lo strumento ImportStorageServiceData nel Resource Kit di Lync Server, che aggiungerà di nuovo i dati nel sistema per essere elaborati e recapitati alla destinazione finale.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Le ricerche tramite query Web della Rubrica non avranno esito negativo se il valore predefinito per UseNormalizationRules viene modificato in falso

**Problema**

Se il valore predefinito per UseNormalizationRules è impostato su false, le ricerche di query Web della Rubrica non avranno esito negativo. Dopo la modifica del valore predefinito, gli utenti del client Lync non saranno in grado di usare la query Web della Rubrica Lync per cercare gli utenti.

**Soluzione**

Se il valore predefinito per UseNormalizationRules è impostato su false, in modo che gli utenti possano usare i numeri di telefono definiti in servizi di dominio Active Directory senza Lync Server 2013 applicando regole di normalizzazione, aggirare il problema eseguendo le operazioni seguenti:

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Esegui una delle operazioni seguenti:
    
      - Se la distribuzione include solo server Lync Server 2013, eseguire il cmdlet seguente a livello globale per modificare i valori di UseNormalizationRules e IgnoreGenericRules in true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se la distribuzione include una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool di Lync Server 2013 nella topologia:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendere che la replica di CMS si verifichi in tutti i pool.

4.  Modificare il file delle regole di normalizzazione del telefono per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Lync Server 2013. Se il file non è presente, creare un file vuoto denominato "regole di\_\_normalizzazione\_\_del numero di telefono aziendale. txt".

5.  Attendere diversi minuti per tutti i pool di front-end per leggere i nuovi file.

6.  Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 della distribuzione.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>Evento di errore 21054 del server della Rubrica viene generato una volta al giorno per ogni pool Lync 2013

**Problema**

Lync Server 2013 Address Book Server genera l'evento di errore 21054 una volta al giorno durante l'esecuzione della manutenzione giornaliera. L'errore viene generato anche ogni volta che un amministratore esegue il cmdlet **Update-csAddressBook** , anche quando l'aggiornamento è riuscito. Tuttavia, questo evento di errore può essere ignorato in modo sicuro quando l'aggiornamento è riuscito.

**Soluzione**

Quando si verifica questo evento di errore, eseguire il cmdlet seguente:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Se il cmdlet segnala che non sono presenti oggetti non indicizzati o abbandonati, l'evento di errore 21054 può essere ignorato in modo sicuro.

Inoltre, l'indicatore di integrità chiave (KHI) "utenti della rubrica correttamente indicizzati" deve essere disattivato in System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Le richieste potrebbero non riuscire quando IPv6 è configurato in un pool di Edge

**Problema**

Quando IPv6 è configurato in un pool di Edge, alcune richieste al pool Edge potrebbero non riuscire.

**Soluzione**

Per risolvere il problema, non configurare un pool di Edge con IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>Il cmdlet Invoke-csPoolFailback potrebbe non riuscire durante il failback del pool

**Problema**

Quando si tenta di non eseguire il backup di un pool, il cmdlet **Invoke-csPoolFailback** potrebbe non riuscire con l'errore "non è possibile completare il processo di idratazione dopo ripetuti tentativi".

**Soluzione**

Per risolvere il problema, eseguire di nuovo il cmdlet e attendere che il cmdlet abbia esito positivo. Tieni presente che il processo di failback può richiedere diversi minuti per il completamento. Potrebbe essere necessario un massimo di 60 minuti per un pool con utenti di 20.000.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>La perdita di dati può verificarsi quando si aggiunge un server front-end a un pool già esistente-Hybrid, Skype for business online

**Problema**

Questo problema può verificarsi in un ambiente in cui un pool ha più di un server front-end e si riavvia uno dei server front-end oppure si aggiunge un nuovo server front-end che in precedenza non faceva parte del pool.

Gli utenti i cui dati vengono archiviati possono verificare la perdita di dati fino a quando non viene stabilita una distribuzione stabile dell'archiviazione dei dati per il pool. Questo periodo di potenziale perdita di dati è limitato a 15 minuti per le conversazioni tra persone e 30 minuti per le conferenze.

**Soluzione**

Quando si esegue la manutenzione, invece di avviare i server front-end nel pool uno alla volta, è consigliabile eseguire il failover del pool in un altro pool e quindi svolgere le attività di manutenzione nei server. È anche possibile rendere il servizio non disponibile prima di eseguire attività di manutenzione e quindi ripristinare la disponibilità al termine della manutenzione.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Gli amministratori non possono ottenere il conteggio delle licenze usando il cmdlet Get-CsClientAccessLicense

**Problema**

Gli amministratori non possono ottenere un uso accurato della licenza client usando il cmdlet **Get-CsClientAccessLicense** .

**Soluzione**

Per controllare il tipo di licenza del server, è possibile eseguire il cmdlet **Get-CsService** per recuperare i nomi di dominio completi (FDQNs) di tutti i database. Se il nome di dominio completo del server front-end è uguale al nome di dominio completo del database back-end, la licenza è una licenza Standard Edition. In caso contrario, la licenza è una licenza di Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>Il conteggio delle licenze client non viene segnalato in modo accurato

**Problema**

Quando si determina il conteggio delle licenze client, è possibile che si verifichino le condizioni seguenti:

1.  **Conteggio delle licenze impreciso per gli utenti di dispositivi mobili**
    
    Il conteggio delle licenze si basa sul numero di indirizzi IP univoci per gli utenti basati su dispositivi. Il conteggio delle licenze sarà limitato nei modi seguenti:
    
      - Se l'indirizzo IP per l'utente cambia durante le sessioni di Lync, verranno conteggiate le licenze. Questo problema può verificarsi quando un utente si connette a Lync Server da più di una posizione con un client desktop.
    
      - Le licenze verranno sottovalutate se un utente si connette a un client per dispositivi mobili, perché non è possibile determinare l'indirizzo IP per il dispositivo.

2.  **Le licenze vengono conteggiate due volte per le chiamate PSTN (Public Switched Telephone Network) a client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate alle linee PSTN**
    
    Negli scenari seguenti verranno conteggiate due licenze aggiuntive anziché una, perché vengono conteggiati sia il numero di telefono che l'utente di Lync per determinare il numero di licenze usate. Per ottenere dati di licenza accurati, rimuovere manualmente le licenze generate da un numero di telefono.
    
      - Una telefonata PSTN a Lync
    
      - Una chiamata Lync a una linea PSTN
    
      - Una chiamata PSTN a Lync e quindi Lync inoltra la chiamata a una linea PSTN. Verrà conteggiata una delle righe PSTN.

3.  **Una licenza non verrà conteggiata per un telefono Lync connesso**
    
    Quando un utente usa un telefono con certificazione Lync, se il telefono si connette e rimane connesso, che mantiene lo stato di accesso, il telefono non verrà conteggiato come utilizzo di una licenza se la query per le licenze si verifica dopo l'accesso del telefono.

4.  **Licenze contate per i telefoni PSTN che partecipano a conferenze**
    
    Quando un utente partecipa a una conferenza con un telefono PSTN, la licenza verrà conteggiata in modo impreciso per partecipare alla conferenza. Tuttavia, non è necessaria alcuna licenza per partecipare a una conferenza con un telefono PSTN.

**Soluzione**

1.  **Conteggio delle licenze impreciso per gli utenti di dispositivi mobili**
    
      - È possibile identificare manualmente gli indirizzi IP che appartengono allo stesso dispositivo e quindi rimuoverne uno nel conteggio delle licenze.
    
      - Non esiste alcuna soluzione alternativa per questo problema con i dispositivi mobili che si connettono al client Lync.

2.  **Le licenze vengono conteggiate due volte per le chiamate PSTN al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate alle linee PSTN**
    
    Sarà necessario identificare manualmente il numero di telefono PSTN e rimuovere il conteggio delle licenze generato per l'utente.

3.  **Una licenza non verrà conteggiata per un telefono Lync connesso**
    
    È possibile configurare il telefono Lync per disconnettersi e quindi accedere di nuovo a intervalli regolari, ad esempio ogni 3 mesi.

4.  **Licenze contate per i telefoni PSTN che partecipano a conferenze**
    
    È possibile identificare manualmente il numero di telefono PSTN usato per partecipare alla conferenza e rimuovere la licenza generata dal numero di telefono.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo l'aggiornamento a Silverlight 5

**Problema**

Se si usa il pannello di controllo di Lync Server in un ambiente VMware, il pannello di controllo di Lync Server potrebbe smettere di funzionare dopo l'aggiornamento di Microsoft Silverlight alla versione 5.

**Soluzione**

Per risolvere il problema, eseguire una delle operazioni seguenti:

  - Disinstallare Silverlight 5 e installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).

  - Accedere al pannello di controllo di Lync Server da un computer che non è un computer virtuale VMware.
    
    A questo scopo, è possibile avviare il pannello di controllo di Lync Server dal menu **Start** di Windows sul server, se nel computer sono installati gli strumenti di amministrazione di Lync Server.
    
    È anche possibile accedere al pannello di controllo di Lync Server tramite un Web browser. L'URL sarà\<simile a FQDN\_\_\>del pool di frontend https:///CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Le informazioni utente nel servizio Rubrica non vengono aggiornate dopo la modifica del nome distinto per l'utente in Active Directory

**Problema**

Se il nome distinto di un utente (noto anche come DN) viene modificato in servizi di dominio Active Directory, le eventuali modifiche aggiuntive non verranno aggiornate nel servizio Rubrica (ABS). Questa operazione non ha alcun effetto sull'accesso o sulla presenza per l'utente, ma impedirà la comunicazione per l'utente se viene modificato anche l'indirizzo SIP, perché la ricerca restituirà un indirizzo SIP obsoleto.

**Soluzione**

Per risolvere il problema, non modificare il DN di un utente. Se si ripristina il DN per l'utente con il valore precedente, gli aggiornamenti verranno riflessi nel servizio Rubrica.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Installazione

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>L'uso di caratteri non ASCII può causare il mancato avvio di Lync Server

**Problema**

Il programma di installazione non riesce se il nome della cartella di destinazione include caratteri non ASCII (inclusi UNICODE, set di caratteri a doppio byte (DBCS), UTF-8 e UTF-16). Inoltre, la configurazione può avere esito positivo, ma il server non si avvia se i caratteri non ASCII sono contenuti in uno degli elementi seguenti:

  - Nome computer

  - Nome di dominio

  - Nome utente

  - URI SIP utente

  - Nome dell'account del servizio

**Soluzione**

Usare solo caratteri ASCII nel nome della cartella di destinazione, il nome del computer, il nome di dominio, il nome utente, l'URI SIP dell'utente e i nomi degli account del servizio.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5" deve essere installato prima di installare Lync Server 2013

**Problema**

L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" (), descritto nell'articolo della Microsoft[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)Knowledge base 264886 (), deve essere installato prima di installare Lync Server 2013.

**Soluzione**

Scaricare e installare l'hotfix dall'area download Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 non riesce a installare in un sistema operativo ITA Windows Server 2012 versione RTM

**Problema**

L'installazione di Lync Server 2013 non riesce su ITA Windows Server 2012 a causa di un errore di installazione in tessuto Windows.

L'installazione di un tessuto Windows non riesce perché le tracce tessuto vengono create con il formato ora di HH: MM: SS. Tuttavia, in ITA Windows Server, il formato dell'ora è HH. MM.SS.

**Soluzione**

Per risolvere il problema, aggiornare il registro di sistema prima di installare Lync Server 2013. La chiave del registro di sistema che deve essere aggiornata è\_:\\gli utenti di HKEY. Pannello\\\\di controllo predefinito\\sTimeFormat internazionale. Modificare il valore di sTimeFormat in HH: mm: SS usando l'interfaccia della riga di comando di Windows PowerShell come indicato di seguito:

1.  Avviare Windows PowerShell ed eseguire i cmdlet seguenti:
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Per visualizzare il valore corrente, eseguire il cmdlet seguente:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Prendere nota del valore corrente di sTimeFormat in modo che possa essere ripristinato al termine dell'installazione.

3.  Per impostare su nuovo valore, eseguire il cmdlet seguente:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Dopo che Lync Server 2013 è stato installato correttamente, ripristinare il valore originale per sTimeFormat eseguendo il cmdlet seguente:
    
        - Set-ItemProperty $a-Name sTimeFormat-value "<valore annotato al passaggio 3. sopra> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilità

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problemi per i client mobili durante il processo di failover del server

**Problema**

Quando un server Lync non riesce e il processo di failover inizia, i problemi seguenti possono influire sugli utenti del client mobile:

  - Nessuna chiamata Lync in arrivo o segnale per un massimo di 10 minuti dopo l'inizio del failover.

  - Non è possibile accettare le richieste di chat in arrivo

  - Non è possibile partecipare alle riunioni se il server non riuscito è il server principale per l'utente

**Soluzione**

Non c'è soluzione alternativa per questo problema. La funzionalità normale verrà ripristinata al termine del processo di failover.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Se un utente mobile rifiuta una chiamata in arrivo da un altro endpoint Lync, la chiamata viene visualizzata come conversione mancata nei client mobili di Lync

**Problema**

Se un utente mobile rifiuta una chiamata in arrivo e la chiamata ha avuto origine da un altro endpoint Lync, la chiamata viene visualizzata come conversazione persa nel client mobile di Lync invece che in una chiamata nell'elenco delle chiamate di dispositivo.

**Soluzione**

Non c'è soluzione alternativa per questo problema.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Il client per dispositivi mobili potrebbe non visualizzare il nome visualizzato di un contatto federato durante la ricerca di contatti

**Problema**

Il nome visualizzato per i contatti federati potrebbe non essere visualizzato in alcuni scenari, ad esempio durante la ricerca di un contatto federato nell'elenco contatti. Questo problema può verificarsi quando non esiste un abbonamento a presenza attiva per il contatto dal client di Lync mobile.

**Soluzione**

Non c'è soluzione alternativa per questo problema.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>Nel client mobile, le informazioni sull'invito e il timestamp mancano da una conversazione persa che è un invito a una conferenza

**Problema**

Nel client per dispositivi mobili, quando una conversazione persa è un invito a una conferenza, le informazioni sull'invito e il timestamp mancano nel messaggio di conversazione persa.

**Soluzione**

Non c'è soluzione alternativa per questo problema.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Gli utenti di client mobili che effettuano chiamate tramite VoIP non possono uscire dalla segreteria telefonica per gli utenti la cui segreteria telefonica è configurata in Exchange 2010 o versioni precedenti

**Problema**

Se un utente di client per dispositivi mobili USA VoIP per effettuare chiamate, l'utente non potrà uscire dalla segreteria telefonica per gli utenti configurati per l'uso della segreteria telefonica in Microsoft Exchange Server 2007 o in Microsoft Exchange Server 2010.

**Soluzione**

Per risolvere il problema, usare Exchange 2010 con SP1 o versione successiva di Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Quando si usa il blocco con l'URL per la configurazione della versione client nei client mobili, potrebbe essere visualizzato un messaggio di errore non corretto

**Problema**

Quando si usa il **blocco con l'URL** per la configurazione della versione client nei client mobili, potrebbe essere visualizzato un messaggio di errore non corretto quando la versione client non è supportata.

**Soluzione**

Per risolvere il problema, configurare la configurazione della versione client per l'uso di **Block** invece di **Block con URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Servizi di conferenza

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Il software antivirus in esecuzione nei server front end di Lync Server 2013 può causare il riciclo di domini applicazione, che interrompe temporaneamente il servizio per Lync Web App 2013, Lync Mobile 2010 e i client di Lync Mobile 2013

**Problema**

Il software antivirus può attivare il riavvio del dominio dell'applicazione, che può comportare la perdita del proprio stato nelle applicazioni client API Web di 2013 Lync (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013).

**Soluzione**

Per risolvere il problema, escludere le cartelle che contengono componenti Web e .NET Framework da analisi antivirus. Per informazioni dettagliate, vedere l'articolo 312592 della Microsoft Knowledge Base "PRB: riavvii di un'applicazione casuale con" l'applicazione sta riavviando " [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)errore in ASP.NET," at.

Le cartelle seguenti devono essere escluse:

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX EXT

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA EXT

  - % WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>I controlli ActiveX o il supporto XMLHTTP nativo devono essere abilitati in Windows Internet Explorer per partecipare correttamente alle conferenze

**Problema**

Se un utente ha disabilitato sia i controlli ActiveX che il supporto XMLHTTP nativo nelle impostazioni del browser Internet di Windows Internet Explorer, l'utente non sarà in grado di partecipare a una riunione se Internet Explorer è selezionato come browser predefinito.

**Soluzione**

Abilitare i controlli ActiveX o "supporto XMLHTTP nativo" in Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Il servizio di conferenza Web di Lync Server non può essere recuperato dalla modalità critica

**Problema**

Se la modalità critica viene attivata per l'archiviazione, in caso di errori di sistema, verrà avviata la modalità critica e le conferenze non funzioneranno più per i partecipanti. Dopo che l'amministratore ha risolto gli errori di sistema, ad esempio la risoluzione di un problema di database, il servizio di conferenza dati non viene ripristinato automaticamente e l'amministratore deve riavviare manualmente il servizio di conferenza per la ripresa dei servizi di conferenza.

**Soluzione**

Un amministratore deve riavviare manualmente il servizio di conferenza telefonica dopo che l'errore di sistema è stato risolto.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Il servizio Web Conferencing ignora il proxy HTTP per i server esterni di Office Web App

**Problema**

Se è stato distribuito un server di Office Web Apps esterno al servizio di Web Conferencing (ovvero un server non presente nella rete aziendale interna) in Internet, la rete perimetrale e il servizio di Web Conferencing richiede un proxy HTTP per connettersi a questo, il L'individuazione di Office Web Apps Server non riuscirà. Il servizio Web Conferencing ignora l'impostazione proxy HTTP, come definito in Generatore di topologia per la configurazione del server Office Web Apps. Di conseguenza, il client Lync non sarà in grado di eseguire la condivisione di Microsoft PowerPoint 2010 con altri partecipanti alla conferenza. Se si sta installando Lync Server locale e si configura anche il server Office Web Apps locale nella rete interna, non è necessaria una configurazione proxy.

**Soluzione**

L'unica soluzione alternativa consiste nel non avere una configurazione di distribuzione che richieda l'uso del proxy HTTP per comunicare con un server esterno di Office Web Apps.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>L'aggiunta di video a una conferenza del provider di servizi di audioconferenza non è supportata

**Problema**

L'aggiunta di un video non è supportata se l'utente è associato a una conferenza per l'audio di un provider di servizi di audioconferenza.

**Soluzione**

Non c'è soluzione alternativa per questo problema.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Le topologie con IPv6 sono abilitate per forzare l'aggiornamento automatico del plug-in Silverlight Web App per garantire la funzionalità di condivisione dello schermo da Lync Web App

**Problema**

Quando una topologia è configurata con IPv6 enabled, gli utenti non possono condividere lo schermo dal client Lync Web App se è già installata una versione precedente del plug-in di condivisione dello schermo.

**Soluzione**

Per forzare un aggiornamento alla versione più recente del plug-in di condivisione dello schermo quando si partecipa a una riunione tramite Lync Web App, modificare il valore di **MinSupportedBuildVersion** da "4.0.7457.0" a "4.0.7577.380" in entrambi i file seguenti:

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\int\\client\\plugins ReachAppShPluginProperties. XML

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\ext\\client\\plugins ReachAppShPluginProperties. XML

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>VoIP aziendale

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>In alcuni casi, un client Lync eseguito in un computer configurato per l'uso di IPv4 e IPv6 dual stack potrebbe non supportare funzionalità che si basano sulla subnet IP del computer, ad esempio E911, bypass multimediale, controllo di ammissione alle chiamate e routing basato sulla posizione

<div class="">


> [!NOTE]  
> Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Quando un client Lync viene eseguito in un computer abilitato per lo stack duale IPv4 e IPv6 e in base alla risoluzione DNS del server proxy, il client può usare l'indirizzo IPv6 del computer per l'accesso. Dopo aver eseguito questa operazione, il client Lync supporterà solo le funzionalità supportate per IPv6, che escludono E911, il bypass multimediale, il controllo dell'ammissione alle chiamate e il routing basato sulla posizione.

**Soluzione**

Per risolvere il problema, disabilitare il supporto IPv6 nel computer client.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Se Enterprise Voice non è configurato per un utente, l'utente dovrà usare il formato E164 per effettuare la chiamata da una conferenza

**Problema**

Se Enterprise Voice non è configurato per un utente, l'utente dovrà usare il formato E164 per effettuare la chiamata in uscita da una conferenza. Se non si usa il formato E164, l'utente non sarà in grado di effettuare la chiamata fuori dalla conferenza.

**Soluzione**

Per risolvere il problema, gli utenti che non sono abilitati per VoIP aziendale devono eseguire la chiamata da una conferenza usando i numeri nel formato E164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Icone di presenza

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non viene rifiutato quando deve essere

**Problema**

Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non viene rifiutato quando necessario.

**Soluzione**

Per risolvere il problema, è possibile disattivare l'archivio contatti unificato per l'utente. A questo scopo, eseguire i cmdlet seguenti:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Ad esempio:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Gli utenti di Office Communications Server 2007 R2 ospitati in locale non sono in grado di visualizzare lo stato presenza degli utenti di Skype for business online nelle distribuzioni ibride-Hybrid

**Problema**

Il problema potrebbe verificarsi in una distribuzione ibrida quando si usa un amministratore di Lync Server 2013.

Lo stato presenza per gli utenti ospitati in Skype for business online viene visualizzato come presenza sconosciuta per gli utenti locali. Inoltre, gli utenti ospitati in Skype for business online non sono in grado di visualizzare lo stato presenza per gli utenti locali di Office Communications Server R2.

**Soluzione**

Per aggirare parzialmente il problema, cambiare il server principale (msRTCSIP-presencehomeserver) degli utenti di Skype for business online in un pool locale di Lync Server 2013 invece che nel Lync Server 2013 Director. È possibile modificare questa impostazione nel server front-end locale.

Questa soluzione alternativa visualizzerà correttamente lo stato presenza degli utenti ospitati in Office Communications Server 2007 R2 per gli utenti di Skype for business online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Response Group Application, Call Park Application e pick-up delle chiamate di gruppo

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Un chiamante potrebbe sentire un secondo di musica in attesa durante l'istituzione di una chiamata con il gruppo di recupero

<div class="">


> [!NOTE]  
> Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Quando viene recuperata una chiamata tramite raccolta chiamate di gruppo, il chiamante potrebbe sentire un secondo di musica in attesa durante l'istituzione della chiamata con la parte del recuperatore.

**Soluzione**

Non c'è soluzione alternativa per questo problema.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Un agente del gruppo di risposte può accedere e disconnettersi tramite una console di agente di Lync Server 2010 ai gruppi di agenti formali di Lync Server 2010 solo

**Problema**

Un agente del gruppo di risposte di Lync Server 2013 può accedere e disconnettersi tramite una console di agente di Lync Server 2010 solo ai gruppi di agenti formali di Lync Server 2010. Nella console agente di Lync Server 2010 gli utenti possono visualizzare solo il gruppo di risposte di Lync Server 2010 a cui appartengono. Non possono vedere i gruppi di risposte di Lync Server 2013 a cui appartengono.

**Soluzione**

Se l'agente di Response Group è un utente di Lync Server 2013 e fa parte di un gruppo di agenti formali di Lync Server 2013, l'utente deve accedere alla console di agente di Lync Server 2013 direttamente tramite un collegamento Web in un browser per accedere e disconnettersi dai gruppi di agenti di Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Un agente del gruppo di risposte di Lync Server 2010 non può inserire chiamate per conto di un gruppo di risposte di Lync Server 2013

**Problema**

Un utente di Lync Server 2010 che è un agente di un gruppo di risposte di Lync Server 2013 non è in grado di effettuare una chiamata per conto del gruppo di risposta. Il gruppo di risposte di Lync Server 2013 non sarà disponibile nel client Lync per effettuare una chiamata.

**Soluzione**

Per risolvere il problema, è necessario spostare l'utente di Lync Server 2010 in Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>La rimozione di un gruppo di risposte da Lync Server 2010 dopo la migrazione a Lync Server 2013 impedirà al gruppo di risposte di accettare le chiamate in arrivo

**Problema**

Se un gruppo di risposte di cui è stata eseguita la migrazione da Lync Server 2010 a Lync Server 2013 viene rimosso da Lync Server 2010 tramite il pannello di controllo di Lync Server o Lync Server Management Shell, il gruppo di risposte in Lync Server 2013 smetterà di ricevere le chiamate in arrivo.

**Soluzione**

Per risolvere il problema, non rimuovere i gruppi di risposta da Lync Server 2010 migrati da Lync Server 2010 a Lync Server 2013.

Se il gruppo di risposte è già stato rimosso, è necessario ridistribuirlo in Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Quando un nuovo flusso di lavoro gestito viene impostato su inattivo quando viene creato, la distribuzione del flusso di lavoro avrà esito negativo

**Problema**

Quando un nuovo flusso di lavoro gestito viene impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo. Questo problema si verifica quando il flusso di lavoro è impostato su inattivo quando viene creato, ma non influisce su un flusso di lavoro modificato per impostarlo su inattivo dopo la distribuzione.

**Soluzione**

Quando si crea e si distribuisce un flusso di lavoro, è possibile impostare il flusso di lavoro come attivo e quindi distribuirlo. Dopo che il flusso di lavoro è stato distribuito correttamente, il flusso di lavoro può essere modificato e impostato su inattivo.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>La rimozione di un gruppo di risposte dal pool di proprietari impedirà al gruppo di risposte del pool di backup di accettare le chiamate in arrivo durante il failover se il gruppo di risposte è stato importato nel pool di backup

**Problema**

Se un gruppo di risposte di proprietà del pool principale è stato importato nel pool di backup senza sovrascrivere il proprietario e il gruppo di risposte viene rimosso dal pool di proprietari, il gruppo di risposte nel pool di backup non accetterà le chiamate in arrivo durante il failover.

**Soluzione**

Sarà necessario ridistribuire il gruppo di risposte nel pool principale. Sarà quindi necessario esportare la configurazione del gruppo di risposte dal pool principale e importarla di nuovo nel pool di backup.

È anche possibile ricreare il gruppo di risposte nel pool di backup. In questo caso, il pool di backup sarà il pool di proprietari del gruppo di risposte.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Una chiamata parcheggiata non può essere recuperata dall'applicazione Call Park se la richiesta di recupero viene eseguita per conto di un gruppo di risposte

**Problema**

Quando le condizioni seguenti sono vere, una richiesta di recupero per una chiamata parcheggiata avrà esito negativo:

  - Un agente fa parte di un gruppo di risposte Anonimo

  - L'agente tenta di recuperare una chiamata parcheggiata dall'applicazione Call Park tramite il gruppo di risposte Anonimo

  - L'agente tenta di recuperare la chiamata componendo il numero dell'orbita tramite l'opzione chiama per conto o tramite la stessa opzione nel client dell'operatore di Lync

**Soluzione**

Non esistono soluzioni alternative per questo problema. La chiamata parcheggiata deve essere recuperata senza farlo per conto di un gruppo di risposte.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Pannello di controllo, Generatore di topologie e Strumento di pianificazione di Lync Server

<div>

## <a name="planning-tool-limitations"></a>Limitazioni dello strumento di pianificazione

<div class="">


> [!NOTE]  
> Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Lo strumento di pianificazione presenta le limitazioni seguenti per la pianificazione della distribuzione:

  - È supportato un massimo di 10 siti centrali

  - Ogni sito centrale può avere un massimo di 14 siti di succursale

  - Ogni sito centrale può avere un massimo di 240.000 utenti

Inoltre, quando si calcola la topologia consigliata, lo strumento di pianificazione non include i valori seguenti:

  - Numero di utenti ospitati online

  - Percentuale di utenti abilitati per la Federazione XMPP

  - Percentuale di utenti che usano Lync Web App

**Soluzione**

Per questi problemi non è disponibile alcuna soluzione alternativa. Per altre informazioni sullo strumento di pianificazione, vedere [progettazione della topologia di Lync Server 2013 tramite lo strumento pianificazione](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>Lo strumento di pianificazione potrebbe non usare gli indirizzi IP definiti in precedenza per la rete Edge durante l'aggiornamento delle opzioni

**Problema**

Dopo aver completato la progettazione usando lo strumento di pianificazione, se si apportano modifiche alle opzioni di rete Edge, gli indirizzi IP aggiuntivi potrebbero essere aggiunti alla struttura anziché aggiornare gli indirizzi IP esistenti. Questo problema può verificarsi quando si visualizzano i dettagli del diagramma reticolare, selezionare **fare clic qui per aggiornare le opzioni**e quindi nella finestra di dialogo Opzioni di configurazione selezionare rete Edge selezionare si **vogliono usare gli stessi FQDN e gli stessi indirizzi IP, ma le diverse porte per i servizi Edge nel server perimetrale**. L'applicazione di eventuali modifiche può causare l'aggiunta di nuovi indirizzi IP e Edge Server alla struttura.

**Soluzione**

Al momento non esiste alcuna soluzione alternativa per questo problema.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Nel pannello di controllo di Lync Server il comando "porta tutti gli utenti al pool" potrebbe non funzionare come previsto

**Problema**

Quando si usa il pannello di controllo di Lync Server per trasferire tutti gli utenti da un pool a un altro in un ambiente di Active Directory complesso, ad esempio uno con più controller di dominio e domini padre/figlio, potrebbe essere restituito un messaggio di errore che indica che "l'utente specificato non è un utente legacy, USA invece il cmdlet Move-CsUser". Questo è il risultato di tempi di replica più lunghi in ambienti Active Directory complessi.

**Soluzione**

Per risolvere il problema, eseguire una delle operazioni seguenti:

  - Usare i filtri nel pannello di controllo di Lync Server per cercare utenti legacy, selezionare questi utenti e quindi usare il **comando Sposta utenti selezionati in pool** invece di **Sposta tutti gli utenti in pool**.

  - Usare Lync Server Management Shell per trasferire gli utenti legacy in batch usando i cmdlet di Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo che il plug-in del browser Microsoft Silverlight è stato aggiornato alla versione 5

**Problema**

Se si usa il pannello di controllo di Lync Server in un ambiente VMware, il pannello di controllo di Lync Server potrebbe smettere di funzionare dopo l'aggiornamento di Silverlight alla versione 5.

**Soluzione**

Per risolvere il problema, eseguire una delle operazioni seguenti:

  - Disinstallare Silverlight 5 e quindi installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).

  - Aprire il pannello di controllo di Lync Server da un computer che non è un computer virtuale VMware.
    
    Per aprire il pannello di controllo di Lync Server da un computer remoto, installare gli strumenti di amministrazione di Lync Server nel computer e quindi avviare il pannello di controllo di Lync Server dal menu **Start** di Windows.
    
    È anche possibile aprire il pannello di controllo di Lync Server immettendo l'URL in un Web browser. L'URL sarà\<simile a FQDN\_\_\>del pool di frontend https:///CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Un amministratore non può eseguire il cmdlet Uninstall-csMirrorDB dopo aver rimosso il database di mirroring in Generatore di topologie

**Problema**

Quando un amministratore disabilita un database di mirroring in Generatore di topologie e quindi Elimina il database di mirroring in Generatore di topologia, viene visualizzato un messaggio nell'elenco da fare per l'amministratore per eseguire il cmdlet **Uninstall-csMirrorDatabase** per rimuovere il mirroring da SQL Server. Quando l'amministratore tenta di eseguire il cmdlet, non riesce.

**Soluzione**

Per rimuovere il mirroring SQL di un pool in Generatore di topologia, è necessario prima di tutto usare un cmdlet per rimuovere il mirror in SQL Server. Puoi quindi usare generatore di topologia per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, usare il cmdlet seguente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Il parametro *DropExistingDatabasesOnMirror* fa sì che i database interessati vengano eliminati dallo specchio. Quindi, per rimuovere il mirror dalla topologia, eseguire le operazioni seguenti:

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.

2.  Deselezionare **Abilita mirroring di SQL Store** e fare clic su **OK**.

3.  Pubblicare la topologia.

<div class="">


> [!IMPORTANT]  
> Ogni volta che si apporta una modifica a una relazione di mirroring del database back-end, è necessario riavviare tutti i server front-end nel pool.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Gli errori di convalida vengono restituiti in Generatore di topologia quando un amministratore tenta di rimuovere una distribuzione con un pool Front-end che include un archivio dei testimoni associato

**Problema**

Se un amministratore tenta di usare il comando **Rimuovi distribuzione** in Generatore di topologia per rimuovere una distribuzione che include un pool Front-end con un archivio dei testimoni associato, viene visualizzato un errore di convalida in Generatore di topologia e l'azione non procederà.

**Soluzione**

Per risolvere il problema, eseguire una delle operazioni seguenti:

  - Rimuovere l'archivio dei testimoni prima di provare a rimuovere la distribuzione.

  - Aggiungere un archivio dei testimoni per il pool Front-end e quindi rimuoverlo.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>Le informazioni di distribuzione del server di chat persistenti non sono coerenti tra lo strumento pianificazione e il generatore di topologie

**Problema**

Quando Lync Server 2013, lo strumento di pianificazione restituisce il diagramma della topologia del sito per una distribuzione del server di chat persistente con il ripristino di emergenza abilitato, il diagramma della topologia del sito include più siti (fisici), con i server di chat persistenti assegnati equamente a ogni sito. In Generatore di topologie tutti i server di chat persistenti sono rappresentati come appartenenti a un singolo sito (logico) e sono elencati nello stesso nodo del pool di server di chat persistente.

**Soluzione**

Al momento non è disponibile una soluzione alternativa per questo problema. L'utente dovrebbe analizzare l'output dello strumento di pianificazione per la distribuzione del server di chat persistente e modificare il piano in base alle specifiche esigenze.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localizzazione

<div>

## <a name="monitoring"></a>Monitoraggio

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>La procedura guidata Distribuisci report di monitoraggio consente di visualizzare caratteri non corretti in determinate circostanze quando si usa la versione asiatica di Lync Server

**Problema**

Quando si usa una versione dell'Asia orientale di Lync Server 2013, ad esempio cinese (semplificato), cinese (tradizionale), giapponese o coreano, in un sistema operativo in cui le impostazioni locali del sistema non sono impostate su una lingua dell'Asia orientale, la procedura guidata Distribuisci rapporti di monitoraggio verrà visualizzare i punti interrogativi o altri caratteri anziché i messaggi localizzati.

**Soluzione**

Per risolvere il problema, impostare le impostazioni locali per il sistema operativo e Lync Server 2013 sulla stessa lingua, che visualizzerà tutti i messaggi in modo corretto.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Pannello di controllo di Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>In alcuni casi, il primo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server scompare quando si fa clic sull'ultimo elemento nella barra di spostamento superiore

**Problema**

Esistono tre casi noti in cui fare clic sull'ultimo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server causerà la scomparsa del primo elemento nella barra di spostamento superiore:

  - Nel francese della versione, nella pagina "Féderation et accès externe", l'elemento "Stratégie accès externe" scomparirà quando si fa clic su "Partenaires fédérés XMPP".

  - Nella pagina "clients" della versione tedesca l'elemento "Clientversionskonfiguration" scompare quando viene fatto clic su "Pushbenachrichtigungskonfiguration".

  - Nella pagina "Конфигурация сети" della versione russa l'elemento "Глобально" scompare quando viene fatto clic su "Маршрут региона".

**Soluzione**

Per risolvere il problema, aggiornare la pagina del pannello di controllo di Lync Server nel browser. La pagina verrà caricata nel browser con tutti gli elementi nella barra di spostamento superiore visualizzata.

</div>

</div>

<div>

## <a name="address-book"></a>Rubrica

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>L'indicizzazione nella Rubrica non funziona come previsto in alcune lingue

<div class="">


> [!NOTE]  
> Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

Se le proprietà di un utente contengono un campo indicizzato e tale campo contiene solo caratteri che non è possibile indicizzare, l'utente non verrà visualizzato nelle ricerche eseguite nella rubrica.

Non è possibile indicizzare i caratteri e le impostazioni locali seguenti:

  - Caratteri cirillici maiuscoli, greci e armeni

  - Caratteri accentati in maiuscolo

  - Tailandese

  - Lao

  - Myanmar

  - Devanagari

  - Etiope

  - Tibetano

  - Bengali

  - Gujarati

  - Telugu

  - Tutti gli altri alfabeti indiani

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, Web Scheduler e Web Components

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Il fallback della lingua per alcune lingue in Lync Web Scheduler, Dial-in, Launcher join, gestione chat room persistente e OCTab potrebbe non funzionare come previsto

**Problema**

Quando si selezionano impostazioni locali neutre in un Web browser (in Internet Explorer, il nome della lingua, ad esempio, senza ulteriori specifiche \[,\]come "Norwegian no", anziché le impostazioni locali che specificano la lingua, lo script e le impostazioni locali, ad \[esempio "norvegese\], Bokmål (Norvegia) NB-no"), potrebbe determinare un comportamento di visualizzazione imprevisto per alcune lingue in Lync Web Scheduler, accesso esterno, avvio di join, gestione chat room e OCTab. Ad esempio, gli utenti potrebbero vedere la pagina inglese quando è selezionata una delle lingue seguenti:

  - Norvegese

  - Portoghese

  - Serbo

**Soluzione**

Se si vuole selezionare una lingua con impostazioni locali neutre, assicurarsi sempre di aggiungere anche la lingua con impostazioni locali specifiche (con script e/o codice paese) come lingua aggiuntiva nell'elenco delle preferenze di lingua del browser.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>È disponibile un supporto limitato per le impostazioni locali azeri e Usbeco quando si usa Lync Web Scheduler, accesso esterno, avvio di join, gestione di chat room persistente e OCTab in alcuni Web browser

<div class="">


> [!NOTE]  
> Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

**Problema**

Quando si usa Internet Explorer 8 o Internet Explorer 9 e si imposta la lingua del browser su Azero (alfabeto latino) o Uzbeco (alfabeto latino), le pagine di avvio di accesso esterno e di join verranno visualizzate in inglese o nella lingua preferita impostata nel browser.

Quando si usano browser Firefox o Chrome e si imposta la lingua del browser su Azero (alfabeto latino) o Uzbeco (alfabeto latino), Lync Web App, Lync Web Scheduler e RGS OCTab verranno visualizzati in inglese o nella lingua preferita impostata per il browser.

Le impostazioni locali dell'Uzbeco (alfabeto latino) non sono supportate nel browser Safari.

**Soluzione**

Non c'è soluzione alternativa per questi problemi.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>La freccia a discesa mancante per l'elenco "partecipa a riunione da" nella versione rumena di Lync Web App

**Problema**

Quando un utente che usa la versione rumena di Lync Web App esegue i passaggi seguenti, la freccia a discesa non viene visualizzata per partecipare a una **riunione** nell'elenco a discesa:

1.  Selezionare **memorizza nel computer** nella scheda **generale** .

2.  Selezionare la scheda **telefono** .

3.  Fare clic sull'elenco a discesa per **partecipare a una riunione**.
    
    Gli utenti non vedranno una freccia che indica che sono disponibili più opzioni rispetto a quella predefinita di **Lync Web App**, che includono: **non partecipare all'audio** (in Romeno, "nu se asociaža la Componenta audio") e **nuovo numero**"(in Romeno" Număr Nou ").

**Soluzione**

Anche se la freccia dell'elenco a discesa non viene visualizzata, gli utenti possono comunque selezionare le impostazioni aggiuntive nell'elenco facendo clic sul valore predefinito.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Quando si usa la versione turca di Lync Web Scheduler, non è possibile salvare una riunione quando si usa l'opzione "persone che scelgo" in "chi è un relatore"

**Problema**

Quando si crea o si modifica una riunione nella versione turca di Lync Web Scheduler, l'opzione "utenti scelti" in "chi è un relatore" non è supportata. Quando questa opzione è selezionata, la riunione non può essere salvata. Viene invece visualizzato un messaggio di errore che indica che non è possibile rendere relatori una o più persone.

**Soluzione**

Per risolvere il problema, gli utenti possono usare l'opzione predefinita "persone della mia azienda" o qualsiasi altra scelta, ad esempio "solo organizzatore" o "tutti, incluse le persone esterne alla mia azienda". L'organizzatore può abbassare di livello o promuovere i ruoli corretti in un secondo momento, dopo aver partecipato alla riunione.

In alternativa, gli utenti che conoscono un'altra lingua possono modificare la selezione della lingua nel browser in una delle altre lingue supportate da 43 e provare a usare l'opzione "persone che scelgo".

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Copyright

Questo documento supporta una versione preliminare di un prodotto software che può essere modificato in modo sostanziale prima del rilascio finale commerciale ed è l'informazione riservata e proprietaria di Microsoft Corporation. Viene divulgato in base a un accordo di non divulgazione tra il destinatario e Microsoft. Questo documento viene fornito solo a scopo informativo e Microsoft non rilascia garanzie, espresse o implicite, in questo documento. Le informazioni contenute in questo documento, incluso l'URL e altri riferimenti al sito Web Internet, sono soggette a modifiche senza preavviso. L'intero rischio dell'uso o dei risultati dell'uso di questo documento rimane con l'utente. Se non diversamente specificato, le società, le organizzazioni, i prodotti, i nomi di dominio, gli indirizzi di posta elettronica, i loghi, le persone, i luoghi e gli eventi descritti in questi esempi sono fittizi. Nessuna associazione con una società, un'organizzazione, un prodotto, un nome di dominio, un indirizzo di posta elettronica, un logo, una persona, un luogo o un evento reali è destinato o dovrebbe essere dedotto. Rispettare tutte le leggi sul copyright applicabili è responsabilità dell'utente. Senza limitare i diritti in diritto d'autore, nessuna parte di questo documento può essere riprodotta, archiviata o introdotta in un sistema di recupero o trasmessa in qualsiasi forma o con qualsiasi mezzo (elettronica, meccanica, fotocopie, registrazione o altro) o per qualsiasi scopo. senza l'espressa autorizzazione scritta di Microsoft Corporation.

Microsoft può avere brevetti, applicazioni di brevetto, marchi, copyright o altri diritti di proprietà intellettuale che coprono argomenti in questo documento. Fatta eccezione per quanto espressamente specificato in un contratto di licenza scritta da Microsoft, l'arredamento di questo documento non offre alcuna licenza per questi brevetti, marchi, copyright o altre proprietà intellettuali.

© 2012 Microsoft Corporation. Tutti i diritti riservati.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server sono marchi registrati o marchi di Microsoft Corporation negli Stati Uniti e/o in altri paesi/aree geografiche.

Tutti gli altri marchi sono proprietà dei rispettivi proprietari.

</div>

</div>

<span> </span>

</div>

</div>

</div>

