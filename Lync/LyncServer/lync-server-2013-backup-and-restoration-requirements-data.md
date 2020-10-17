---
title: 'Lync Server 2013: requisiti di backup e ripristino: dati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8431e16e976f0ad189205f0c42c04d50e6936e90
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527043"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Requisiti di backup e ripristino in Lync Server 2013: data

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-26_

Lync Server utilizza le impostazioni e le informazioni di configurazione archiviate nei database e i dati archiviati nei database e nei file archiviati. In questo argomento vengono descritti i dati di cui è necessario eseguire il backup per poter ripristinare il servizio se l'organizzazione avverte un errore o un'interruzione e identifica anche i dati e i componenti utilizzati da Lync Server di cui è necessario eseguire il backup separatamente.

<div>

## <a name="settings-and-configuration-requirements"></a>Requisiti di impostazioni e dati di configurazione

In questo argomento sono incluse le procedure per il backup e il ripristino delle impostazioni e delle informazioni di configurazione necessarie per il ripristino del servizio Lync Server. Le informazioni di configurazione si trovano nell'archivio di gestione centrale o in un altro database back-end o nel server Standard Edition.

Nella tabella seguente vengono identificate le impostazioni e le informazioni di configurazione necessarie per eseguire il backup e il ripristino.

### <a name="settings-and-configuration-data"></a>Impostazioni e dati di configurazione

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di dati</th>
<th>Dove sono archiviati</th>
<th>Descrizione/Quando eseguire il backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informazioni di configurazione della topologia</p></td>
<td><p>Archivio di gestione centrale (database: XDS. MDF)</p></td>
<td><p>Impostazioni relative a topologia, criteri e configurazione.</p>
<p>Eseguire il backup con i controlli regolari e dopo aver utilizzato il pannello di controllo di Lync Server o i cmdlet per modificare la configurazione o i criteri.</p></td>
</tr>
<tr class="even">
<td><p>Informazioni sulle posizioni</p></td>
<td><p>Archivio di gestione centrale (database: LIS. MDF)</p></td>
<td><p>Informazioni sulla configurazione del servizio Enhanced 9-1-1 (E9-1-1) di VoIP aziendale. Queste informazioni sono in genere statiche.</p>
<p>Eseguire il backup in occasione dei backup regolari.</p></td>
</tr>
<tr class="odd">
<td><p>Informazioni di configurazione di Response Group</p></td>
<td><p>Server back-end server o Standard Edition (database: RgsConfig. MDF)</p></td>
<td><p>Gruppi di agenti, code e flussi di lavoro di Response Group.</p>
<p>Eseguire il backup in occasione dei backup regolari e dopo aver aggiunto o modificato gruppi di agenti, code o flussi di lavoro.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Requisiti dei dati

Di seguito è indicato un elenco dei dati di Lync Server di cui è necessario eseguire il backup in modo che sia possibile ripristinare il servizio Lync Server in caso di errore.

Tenere presente che alcuni tipi di dati non sono necessari per il ripristino. Questo argomento non contiene le procedure per eseguire il backup di questi tipi di dati, inclusi i seguenti:

  - Dati utente temporanei, ad esempio endpoint e sottoscrizioni, server per conferenze attivi e stati di conferenza transitori (database: RtcDyn.mdf)

  - Dati della Rubrica (database: RtcAb. mdf e Rtcab1. MDF). Il database della Rubrica viene rigenerato automaticamente da servizi di dominio Active Directory.

  - Informazioni dinamiche per l'applicazione Parcheggio di chiamata (database: CpsDyn. MDF)

  - Dati dei Response Group transitori, ad esempio lo stato di accesso dell'agente e le informazioni di attesa delle chiamate (database: RgsDyn. MDF)

  - Il database di conformità per la chat persistente (database: MgcComp. MDF). Se si dispone della conformità di Persistent Chat abilitata, le informazioni nel database di conformità di Persistent Chat sono transitorie finché si dispone di un adattatore configurato per leggere informazioni dal database e convertirlo in un formato alternativo. Di conseguenza, il database di conformità per la chat persistente è considerato temporaneo.
    
    Lync Server 2013 Persistent Chat Server viene fornito con un adattatore XML. È inoltre possibile installare adattatori personalizzati che consentono di utilizzare i dati e spostarli in altre origini, ad esempio gli archivi ospitati di Exchange.

Nella tabella seguente vengono identificati i dati di cui è necessario eseguire il backup e il ripristino.

### <a name="data-stored-in-databases"></a>Dati archiviati in database

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di dati</th>
<th>Dove sono archiviati</th>
<th>Descrizione/Quando eseguire il backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dati utente permanenti</p></td>
<td><p>Server back-end server o Standard Edition (database: RTCXDS. MDF)</p></td>
<td><p>Diritti utente, elenchi Contatti, dati di server o pool, conferenze pianificate e così via. Questi dati utente non includono il contenuto caricato in una conferenza.</p>
<p>Eseguire il backup in occasione dei backup regolari. Queste informazioni sono dinamiche, ma la perdita di aggiornamenti non è catastrofica per Lync Server, se è necessario ripristinare l'ultimo backup regolare. Se gli elenchi Contatti sono critici per l'organizzazione, è possibile eseguire il backup di questi dati più di frequente.</p></td>
</tr>
<tr class="even">
<td><p>Dati di archiviazione</p></td>
<td><p>Database di archiviazione (database: LcsLog.mdf)</p>
<p>Questi dati possono essere archiviati in Exchange 2013, se è stata abilitata l'opzione di integrazione di Microsoft Exchange. In caso contrario, i dati vengono conservati in un database di archiviazione di Lync Server, che può essere collocato con un altro database di Lync Server o autonomo in un server di database separato.</p></td>
<td><p>Contenuto di messaggistica istantanea e riunioni.</p>
<p>Questi dati non sono fondamentali per Lync Server, ma possono essere fondamentali per l'organizzazione a fini normativi. Stabilire la pianificazione dei backup di conseguenza.</p></td>
</tr>
<tr class="odd">
<td><p>Dati di monitoraggio</p></td>
<td><p>Database di monitoraggio (LcsCDR.mdf e QoeMetrics.mdf)</p>
<p>Tali database possono essere collocati in un altro database di Lync Server o autonomo in un server di database separato.</p></td>
<td><p>Record dettagli chiamata (LcsCDR. MDF) e metriche sulla qualità delle esperienze (QoE) (QoeMetrics. MDF).</p>
<p>La registrazione dettagli chiamata contiene dati dinamici che possono essere critici per l'azienda. Stabilire la pianificazione dei backup valutando se questi record sono necessari o meno per motivi di regolamentazione.</p>
<p>Le informazioni su QoE sono dinamiche. La perdita di dati QoE non è critica per il funzionamento di Lync Server, ma può essere fondamentale per la propria azienda. Stabilire la pianificazione dei backup in base al grado di criticità delle informazioni per l'organizzazione.</p></td>
</tr>
<tr class="even">
<td><p>Dati di chat persistente</p></td>
<td><p>Database di chat persistente (MGD. MDF).</p>
<p>Questo database può essere collocato con un altro database di Lync Server o autonomo in un server di database separato.</p></td>
<td><p>I dati di chat persistente sono contenuti di chat effettivamente pubblicati nelle chat room. Questi dati sono spesso importanti per le aziende.</p>
<p>È possibile scegliere di utilizzare il backup di SQL Server o di esportare il database utilizzando il cmdlet <strong>Export-CsPersistentChatData</strong> fornito in Lync Server. Per il ripristino dei dati, è possibile importare e ripristinare il database fino al punto in cui si trova l'ultimo backup completo, il che significa che non è possibile ripristinare il database fino al punto di errore.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Requisiti dei dati dell'archivio file

In una distribuzione di Enterprise Edition, l'archivio file di Lync Server è in genere posizionato in un file server. In una distribuzione di Standard Edition, l'archivio file di Lync Server si trova per impostazione predefinita nel server Standard Edition. In genere, è presente un archivio file di Lync Server condiviso per un sito. L'archivio file di chat persistente utilizza la stessa condivisione file dell'archivio file di Lync Server.

Le posizioni dell'archivio file sono identificate come \\ \\ nome della condivisione del server \\ . Per trovare le posizioni specifiche degli archivi di file, aprire Generatore di topologie e cercare nel nodo **archivi file** .

Nella tabella seguente sono identificati gli archivi file di cui è necessario eseguire il backup e il ripristino.

### <a name="file-stores"></a>Archivi file

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di dati</th>
<th>Dove sono archiviati</th>
<th>Descrizione/Quando eseguire il backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Archivio file di Lync Server</p></td>
<td><p>In genere in un file server, in un cluster di file o in un server Standard Edition</p></td>
<td><p>Soddisfare le riunioni, soddisfare i metadati del contenuto, registrare i registri di conformità, i file di dati dell'applicazione, aggiornare i file per gli aggiornamenti dei dispositivi, i file audio per Response Group, il parcheggio di chiamata e le applicazioni di annuncio e i file inseriti nelle chat persistenti.</p>
<p>Eseguire il backup in occasione dei backup regolari.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Altri requisiti di backup

Per garantire la possibilità di ripristinare i servizi di Lync Server in caso di errore, è necessario eseguire il backup di alcuni componenti necessari che non fanno parte di Lync Server stesso. Non è possibile eseguire il backup o il ripristino dei componenti seguenti nell'ambito del processo di backup e ripristino di Lync Server descritto in questo documento:

  - Servizi di dominio **Active Directory**     È necessario eseguire il backup di AD DS utilizzando gli strumenti di Active Directory contemporaneamente all'esecuzione del backup di Lync Server. È importante mantenere servizi di dominio Active Directory sincronizzati con Lync Server, al fine di evitare problemi che possono verificarsi quando Lync Server prevede che gli oggetti contatto che non corrispondono a quelli in servizi di dominio Active Directory. Servizi di dominio Active Directory archivia le impostazioni seguenti che vengono utilizzate da Lync Server:
    
      - URI SIP dell'utente e altre impostazioni utente.
    
      - Oggetti contatto per applicazioni quali Response Group e operatore conferenza.
    
      - Puntatore all'archivio di gestione centrale.
    
      - Account di autenticazione Kerberos (un oggetto computer facoltativo) e gruppi di sicurezza di Lync Server.
    
    Per informazioni dettagliate su come eseguire il backup e il ripristino di servizi di dominio Active Directory in Windows Server 2008, vedere "Guida dettagliata su backup e ripristino di servizi di dominio Active Directory" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .

  - **Autorità di certificazione e certificati**     Utilizzare i criteri dell'organizzazione per il backup dell'autorità di certificazione (CA) e dei certificati. Se si utilizzano le chiavi private esportabili, è possibile eseguire il backup del certificato e della chiave privata e quindi esportarle se si utilizzano le procedure descritte in questo documento per ripristinare Lync Server. Se si utilizza un'autorità di certificazione interna, è possibile eseguire di nuovo la registrazione se è necessario ripristinare Lync Server. È importante conservare la chiave privata in un posto sicuro dove sarà disponibile in caso di problemi con un computer.

  - **System Center Operations Manager**     Se si utilizza Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager) per monitorare la distribuzione di Lync Server, è possibile, facoltativamente, eseguire il backup dei dati creati durante il monitoraggio di Lync Server. Utilizzare il processo di backup standard di SQL Server per eseguire il backup dei file di System Center Operations Manager. Questi file non vengono ripristinati durante il recupero.

  - **Configurazione del gateway PSTN (Public Switched Telephone Network)**     Se si utilizzano VoIP aziendale o Survivable Branch Appliance, è necessario eseguire il backup della configurazione del gateway PSTN. Per informazioni dettagliate sul backup e il ripristino delle configurazioni di gateway PSTN, contattare il fornitore.

  - **Versioni coesistenti di Lync Server o Office Communications Server**     Se la distribuzione di Lync Server 2013 è coesistente con Lync Server 2010 o una versione precedente di Office Communications Server, non è possibile utilizzare le procedure descritte in questo documento per eseguire il backup o il ripristino della versione precedente. È invece necessario utilizzare le procedure documentate specificamente per la versione precedente. Per informazioni dettagliate su come eseguire il backup e il ripristino di Lync Server 2010, vedere [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) . Per informazioni dettagliate su come eseguire il backup e il ripristino di Microsoft Office Communications Server 2007 R2, vedere [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .

  - **Informazioni sull'infrastruttura**     È necessario eseguire il backup delle informazioni relative all'infrastruttura, ad esempio la configurazione del firewall, la configurazione del bilanciamento del carico, la configurazione di Internet Information Services (IIS), i record DNS (Domain Name System) e gli indirizzi IP e la configurazione DHCP (Dynamic Host Configuration Protocol). Per informazioni dettagliate sul backup di questi componenti, contattare i rispettivi fornitori.

  - Messaggistica unificata **di Microsoft Exchange e Exchange**     Eseguire il backup e il ripristino della messaggistica unificata di Microsoft Exchange e Exchange come descritto nella documentazione di Microsoft Exchange. Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange Server 2013, vedere [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) . Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange Server 2010, vedere [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .
    
    Si noti che Lync Server 2013 introduce la possibilità di disporre di elenchi di contatti utente, foto utente ad alta definizione e dati di archiviazione archiviati in Exchange 2013. Vedere l'elenco seguente per vedere come eseguire il backup di questi tipi di dati:
    
      - Le **foto ad alta definizione** vengono copiate come parte del backup di Exchange Server.
    
      - L' **archivio contatti unificato** è stato introdotto in Lync Server 2013. Archivio contatti unificato consente agli utenti di mantenere tutte le informazioni di contatto in Exchange 2013.
        
        È necessario verificare che i backup siano aggiornati per gli utenti in termini di archiviazione dei contatti utente nell'archivio contatti unificato o nel server back-end Lync. Negli scenari seguenti vengono illustrati i casi in cui la migrazione dei contatti utente all'archivio contatti unificato può causare problemi per il processo di backup e ripristino.
        
        **Scenario 1:** I contatti utente vengono migrati nell'archivio contatti unificato e viene eseguito un ripristino da un backup di Lync Server effettuato prima della migrazione dei contatti utente. In questo scenario, l'utente avrà uno stato di contatti obsoleti fino a un giorno fino a quando l'attività di migrazione di Lync Server inizierà la migrazione dei contatti utente a Exchange. Si noti che, poiché i contatti dell'utente sono stati precedentemente migrati nell'archivio contatti unificato, verranno utilizzate le informazioni sui contatti di Exchange. In questo scenario non sono necessari interventi di amministratore.
        
        **Scenario 2:** I contatti utente sono stati precedentemente archiviati nell'archivio contatti unificato, ma quindi sono stati ripristinati. Viene eseguito un ripristino da un backup di Lync Server utilizzato quando i contatti dell'utente sono stati archiviati nell'archivio contatti unificato. In questo scenario, un messaggio di errore `Error: Incorrect Exchange Version` nei registri del server client o Lyss può indicare che si tratta di un problema. L'utente sarà in grado di accedere all'elenco dei contatti in Lync 2013 direttamente da Exchange, ma lo stato del client non corrisponderà allo stato di Lync Server. Per risolvere questo errore, è necessario che un amministratore esegua i cmdlet **Invoke-CsUCSRollback** per gli utenti coinvolti.
    
      - È possibile archiviare **i dati di archiviazione** in Exchange 2013. Questi dati non sono fondamentali per Lync Server, ma possono essere fondamentali per l'organizzazione a fini normativi. Se i dati di archiviazione sono archiviati in Exchange ed è importante per l'organizzazione, seguire le procedure di backup e ripristino di Exchange. Si noti che i dati di archiviazione archiviati in Exchange non possono essere spostati di nuovo in Lync Server. Inoltre, non esiste alcun modo per spostare i dati già archiviati nel database di archiviazione Lync in Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

