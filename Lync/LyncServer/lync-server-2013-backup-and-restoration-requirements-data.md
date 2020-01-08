---
title: 'Lync Server 2013: requisiti di backup e ripristino: dati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Requisiti di backup e ripristino in Lync Server 2013: dati

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-26_

Lync Server usa le impostazioni e le informazioni di configurazione archiviate nei database e i dati archiviati in database e archivi di file. In questo argomento vengono descritti i dati di cui è necessario eseguire il backup per poter ripristinare il servizio se l'organizzazione avverte un errore o un'interruzione, oltre a identificare anche i dati e i componenti usati da Lync Server che è necessario eseguire il backup separatamente.

<div>

## <a name="settings-and-configuration-requirements"></a>Requisiti per le impostazioni e la configurazione

Questo argomento include le procedure per il backup e il ripristino delle impostazioni e delle informazioni di configurazione necessarie per il ripristino del servizio Lync Server. Le informazioni di configurazione si trovano nell'Central Management Store o in un altro database back-end o in un server Standard Edition.

La tabella seguente identifica le impostazioni e le informazioni di configurazione necessarie per eseguire il backup e il ripristino.

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
<th>Dove archiviato</th>
<th>Descrizione/quando eseguire il backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informazioni sulla configurazione della topologia</p></td>
<td><p>Central Management store (database: XDS. MDF)</p></td>
<td><p>Impostazioni di topologia, criteri e configurazione.</p>
<p>Eseguire il backup con i controlli regolari e dopo avere usato il pannello di controllo di Lync Server o i cmdlet per modificare la configurazione o i criteri.</p></td>
</tr>
<tr class="even">
<td><p>Informazioni sulla posizione</p></td>
<td><p>Central Management store (database: LIS. MDF)</p></td>
<td><p>Informazioni sulla configurazione di Enterprise Voice Enhanced 9-1-1 (E9-1-1). Queste informazioni sono in genere statiche.</p>
<p>Eseguire il backup con i normali sostegni.</p></td>
</tr>
<tr class="odd">
<td><p>Informazioni sulla configurazione di Response Group</p></td>
<td><p>Server back-end o server Standard Edition (database: RgsConfig. MDF)</p></td>
<td><p>Gruppi di agenti di Response Group, code e flussi di lavoro.</p>
<p>Eseguire il backup con i normali sostegni e dopo aver aggiunto o modificato i gruppi di agenti, le code o i flussi di lavoro.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Requisiti per i dati

Ecco un elenco dei dati di Lync Server di cui è necessario eseguire il backup in modo da poter ripristinare il servizio Lync Server in caso di errore.

Tieni presente che alcuni tipi di dati non sono necessari per il ripristino. Questo argomento non contiene procedure per il backup di questi tipi di dati, che includono i seguenti:

  - Dati utente temporanei, ad esempio endpoint e abbonamenti, server di conferenza attiva e Stati di conferenza transitori (database: RtcDyn. MDF)

  - Dati della Rubrica (database: RtcAb. mdf e Rtcab1. MDF). Il database della Rubrica viene rigenerato automaticamente da servizi di dominio Active Directory.

  - Informazioni dinamiche per l'applicazione Call Park (database: CpsDyn. MDF)

  - Dati del gruppo di risposta temporaneo, ad esempio lo stato di accesso dell'agente e le informazioni di attesa delle chiamate (database: RgsDyn. MDF)

  - Database di conformità per la chat persistente (database: MgcComp. MDF). Se è abilitata la conformità della chat persistente, le informazioni nel database di conformità della chat persistente sono transitorie purché si disponga di un adapter configurato per leggere le informazioni dal database e convertirlo in un formato alternativo. Il database di conformità per la chat persistente viene quindi considerato temporaneo.
    
    Il server di chat persistente di Lync Server 2013 viene fornito con un adattatore XML. È anche possibile installare adapter personalizzati che accettano questi dati e lo spostano in altre origini, ad esempio gli archivi ospitati di Exchange.

La tabella seguente identifica i dati necessari per eseguire il backup e il ripristino.

### <a name="data-stored-in-databases"></a>Dati archiviati nei database

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di dati</th>
<th>Dove archiviato</th>
<th>Descrizione/quando eseguire il backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dati utente permanenti</p></td>
<td><p>Server back-end o server Standard Edition (database: RTCXDS. MDF)</p></td>
<td><p>Diritti utente, elenchi contatti utente, dati server o pool, conferenze pianificate e così via. Questi dati utente non includono il contenuto caricato in una conferenza.</p>
<p>Eseguire il backup con i normali sostegni. Queste informazioni sono dinamiche, ma la perdita di aggiornamenti non è catastrofica per Lync Server se è necessario ripristinare l'ultimo backup normale. Se gli elenchi di contatti sono fondamentali per l'organizzazione, è possibile eseguire il backup dei dati più frequentemente.</p></td>
</tr>
<tr class="even">
<td><p>Archiviazione dei dati</p></td>
<td><p>Database di archiviazione (database: LcsLog. MDF)</p>
<p>Questi dati possono essere archiviati in Exchange 2013, se è stata abilitata l'opzione di integrazione di Microsoft Exchange. In caso contrario, questi dati vengono conservati in un database di archiviazione di Lync Server, che può essere collocato in un altro database di Lync Server o autonomo in un server di database separato.</p></td>
<td><p>Messaggistica istantanea (IM) e contenuto della riunione.</p>
<p>Questi dati non sono fondamentali per Lync Server, ma può essere fondamentale per l'organizzazione per scopi normativi. Determinare di conseguenza la pianificazione di backup.</p></td>
</tr>
<tr class="odd">
<td><p>Monitoraggio dei dati</p></td>
<td><p>Monitoraggio di database (LcsCDR. mdf e QoeMetrics. MDF)</p>
<p>Questi database possono essere collocati in un altro database di Lync Server o autonomo in un server di database separato.</p></td>
<td><p>Record dettagli chiamata (LcsCDR. MDF) e metriche di qualità delle esperienze (QoE) (QoeMetrics. MDF).</p>
<p>I record dettagli chiamata sono dinamici e possono essere critici per l'azienda. Determinare la pianificazione del backup considerando se sono necessari questi record per motivi di regolamentazione.</p>
<p>Le informazioni sulla qualità delle esperienze sono dinamiche. La perdita di dati QoE non è fondamentale per l'operazione di Lync Server, ma può essere fondamentale per l'azienda. Determinare la pianificazione del backup in base alla criticità di queste informazioni per l'organizzazione.</p></td>
</tr>
<tr class="even">
<td><p>Dati della chat persistente</p></td>
<td><p>Database di chat persistente (MGD. MDF).</p>
<p>Questo database può essere collocato in un altro database di Lync Server o autonomo in un server di database separato.</p></td>
<td><p>I dati della chat persistente sono contenuti di chat effettivi pubblicati nelle chat room. Questi dati sono spesso critici per gli affari.</p>
<p>È possibile scegliere di usare il backup di SQL Server oppure esportare il database usando il cmdlet <strong>Export-CsPersistentChatData</strong> fornito in Lync Server. Per il ripristino dei dati, è possibile importare e ripristinare il database fino al punto dell'ultimo backup completo, quindi non è possibile ripristinare il database fino al punto di errore.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Requisiti per l'archiviazione dei file

In una distribuzione di Enterprise Edition, il file Store di Lync Server si trova in genere in un file server. In una distribuzione Standard Edition, il file Store di Lync Server si trova per impostazione predefinita nel server Standard Edition. In genere, esiste un archivio file di Lync Server condiviso per un sito. L'archivio di file della chat persistente usa la stessa condivisione di file dell'archivio di file di Lync Server.

I percorsi di archiviazione file sono \\ \\identificati come nome condivisione server\\. Per trovare le posizioni specifiche degli archivi di file, aprire Generatore di topologie e cercare nel nodo **archivi file** .

La tabella seguente identifica gli archivi di file necessari per eseguire il backup e il ripristino.

### <a name="file-stores"></a>Archivi di file

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di dati</th>
<th>Dove archiviato</th>
<th>Descrizione/quando eseguire il backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Archivio file di Lync Server</p></td>
<td><p>In genere in un file server, un cluster di file o un server Standard Edition</p></td>
<td><p>Contenuto della riunione, riunione dei metadati del contenuto, registri della conformità delle riunioni, file di dati dell'applicazione, file di aggiornamento per gli aggiornamenti dei dispositivi, file audio per il gruppo di risposte, parcheggio delle chiamate e applicazioni di annunci e file inseriti nelle chat room permanenti.</p>
<p>Eseguire il backup con i normali sostegni.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Requisiti di backup aggiuntivi

Per garantire la possibilità di ripristinare i servizi Lync Server in caso di errore, è necessario eseguire il backup di alcuni componenti necessari che non fanno parte di Lync Server stesso. I componenti seguenti non vengono sottoposte a backup o ripristinati come parte del processo di backup e ripristino di Lync Server descritto in questo documento:

  - **Servizi di dominio Active Directory**   che è necessario eseguire il backup di Active Directory con gli strumenti attivi per il backup di Lync Server. È importante garantire la sincronizzazione di Active Directory con Lync Server, per evitare problemi che si verificano quando Lync Server si aspetta che gli oggetti contatto non corrispondano a quelli in servizi di dominio Active Directory. In servizi di dominio Active Directory vengono archiviate le impostazioni seguenti usate da Lync Server:
    
      - URI SIP utente e altre impostazioni utente.
    
      - Contattare gli oggetti per le applicazioni, ad esempio Response Group e Attendant.
    
      - Un puntatore all'archivio di gestione centrale.
    
      - Account di autenticazione Kerberos (un oggetto computer facoltativo) e gruppi di sicurezza di Lync Server.
    
    Per informazioni dettagliate su come eseguire il backup e il ripristino di servizi di dominio Active Directory in Windows Server 2008, vedere "Guida introduttiva a [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)backup e ripristino di servizi di dominio Active Directory".

  - **Autorità di certificazione e certificati**   usare i criteri dell'organizzazione per eseguire il backup dell'autorità di certificazione (CA) e dei certificati. Se si usano chiavi private esportabili, è possibile eseguire il backup del certificato e della chiave privata e quindi esportarle se si usano le procedure descritte in questo documento per ripristinare Lync Server. Se si usa una CA interna, è possibile eseguire di nuovo la registrazione se è necessario ripristinare Lync Server. È importante mantenere la chiave privata in un percorso sicuro in cui sarà disponibile se un computer non riesce.

  - **System Center Operations Manager**   se si usa Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager) per monitorare la distribuzione di Lync Server, è possibile eseguire facoltativamente il backup dei dati creati durante il monitoraggio di Lync Server. Usare il processo di backup standard di SQL Server per eseguire il backup dei file di System Center Operations Manager. Questi file non vengono ripristinati durante il ripristino.

  - **Configurazione del gateway PSTN (Public Switched Telephone Network)**   se si usano Enterprise Voice o Survivable Branch Appliances, è necessario eseguire il backup della configurazione del gateway PSTN. Vedere il fornitore per informazioni dettagliate su come eseguire il backup e il ripristino delle configurazioni dei gateway PSTN.

  - **Versioni coesistenti di Lync Server o Office Communications Server**   se la distribuzione di Lync Server 2013 è coesistente con Lync Server 2010 o una versione precedente di Office Communications Server, non è possibile usare le procedure descritte in questo documento per eseguire il backup o il ripristino della versione precedente. Devi invece usare le procedure di backup e ripristino documentate in modo specifico per la versione precedente. Per informazioni dettagliate su come eseguire il backup e il ripristino di Lync [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) Server 2010, vedere. Per informazioni dettagliate su come eseguire il backup e il ripristino di Microsoft Office Communications Server [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)2007 R2, vedere.

  - **Informazioni sull'infrastruttura**   necessarie per eseguire il backup di informazioni sull'infrastruttura, ad esempio la configurazione del firewall, la configurazione del bilanciamento del carico, la configurazione di Internet Information Services (IIS), i record DNS (Domain Name System) e gli indirizzi IP e la configurazione DHCP (Dynamic Host Configuration Protocol). Per informazioni dettagliate su come eseguire il backup di questi componenti, consultare i rispettivi fornitori.

  - **Microsoft Exchange ed Exchange Unified Messaging (UM)**   backup e ripristino della messaggistica unificata di Microsoft Exchange e Exchange come descritto nella documentazione di Microsoft Exchange. Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)Server 2013, vedere. Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)Server 2010, vedere.
    
    Si noti che Lync Server 2013 introduce la possibilità di avere elenchi di contatti utente, foto degli utenti ad alta definizione e archiviazione dei dati archiviati in Exchange 2013. Vedere l'elenco seguente per informazioni su come eseguire il backup di questi tipi di dati:
    
      - Le **foto ad alta definizione** vengono supportate come parte del backup di Exchange Server.
    
      - L' **archivio contatti unificato** è stato introdotto in Lync Server 2013. L'archivio contatti unificato consente agli utenti di conservare tutte le informazioni di contatto in Exchange 2013.
        
        È necessario assicurarsi che i backup siano aggiornati per gli utenti in termini di archiviazione dei contatti utente nell'archivio contatti unificato o nel server back-end Lync. Gli scenari seguenti illustrano dove la migrazione dei contatti utente all'archivio contatti unificato può causare problemi per il processo di backup e ripristino.
        
        **Scenario 1:** I contatti utente vengono migrati nell'archivio contatti unificato e viene eseguito un ripristino da un backup di Lync Server effettuato prima della migrazione dei contatti utente. In questo scenario, l'utente avrà uno stato di contatti obsoleti per un massimo di un giorno fino a quando l'attività di migrazione di Lync Server inizierà a eseguire la migrazione dei contatti utente a Exchange. Tieni presente che, poiché i contatti utente sono stati precedentemente migrati nell'archivio contatti unificato, verranno usate le informazioni di contatto di Exchange. In questo scenario non è necessario alcun intervento dell'amministratore.
        
        **Scenario 2:** I contatti degli utenti sono stati archiviati in precedenza nell'archivio contatti unificato, ma sono stati ripristinati. Un ripristino viene eseguito da un backup di Lync Server acquisito quando i contatti utente sono stati archiviati nell'archivio contatti unificato. In questo scenario, un messaggio di `Error: Incorrect Exchange Version` errore nei registri del server client o Lyss può indicare che si tratta di un problema. L'utente potrà accedere all'elenco contatti in Lync 2013 direttamente da Exchange, ma lo stato del client non corrisponde allo stato del server Lync. Per risolvere questo problema, un amministratore dovrà eseguire i cmdlet **Invoke-CsUCSRollback** per gli utenti interessati.
    
      - **I dati di archiviazione** possono essere archiviati in Exchange 2013. Questi dati non sono fondamentali per Lync Server, ma può essere fondamentale per l'organizzazione per scopi normativi. Se l'archiviazione dei dati è archiviata in Exchange ed è fondamentale per l'organizzazione, seguire le procedure di backup e ripristino di Exchange. Tieni presente che l'archiviazione dei dati archiviati in Exchange non può essere spostata di nuovo in Lync Server. Inoltre, non è possibile trasferire i dati già archiviati nel database di archiviazione di Lync in Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

