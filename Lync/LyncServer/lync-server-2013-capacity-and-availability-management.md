---
title: 'Lync Server 2013: gestione della capacità e della disponibilità'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923dd7a4133da52a68e4d66ee6d5c7c47e7c0421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Gestione della capacità e della disponibilità in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-18_

Lo scopo della gestione della gestione delle capacità e della disponibilità è misurare e controllare le prestazioni del sistema. Ti consigliamo di implementare le procedure di gestione della capacità e gestione della disponibilità in modo da misurare e controllare le prestazioni del sistema. È necessario sapere se il sistema è disponibile e se è in grado di gestire le richieste correnti e quelle proiettate impostando le previsioni e monitorando il sistema per cercare le tendenze.

<div>

## <a name="capacity-management"></a>Gestione della capacità

La gestione della capacità prevede la pianificazione, il dimensionamento e il controllo della capacità del servizio per garantire che vengano superati i livelli minimi di prestazioni specificati nell'SLA. La gestione delle capacità ottimali garantisce la possibilità di fornire servizi IT a costi ragionevoli e rispettare i livelli di prestazioni definiti nei contratti SLA con il client. Questi criteri possono includere gli elementi seguenti:

  - **Tempo di risposta del sistema**   questo è il tempo misurato che il sistema impiega per eseguire azioni tipiche. Gli esempi includono il tempo necessario per il ruolo del server audio/video per elaborare il traffico audio/video, il tempo necessario per un client per creare e partecipare a una conferenza oppure il tempo necessario per l'aggiornamento della presenza in tutti i client Watcher.

  - **Capacità di archiviazione**   questa è la capacità di un sistema di archiviazione, sia che si tratti di un database del contenuto, di un dispositivo di backup o di un'unità locale. Gli esempi includono la quantità massima di spazio di archiviazione da fornire per ogni sito e l'ora in cui devono essere archiviati i backup prima che vengano sovrascritti.

La regolazione della capacità è spesso un caso di verificare che siano disponibili sufficienti risorse fisiche, ad esempio lo spazio su disco e la larghezza di banda della rete. La tabella seguente elenca le risoluzioni tipiche per i problemi relativi alla capacità.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Risoluzioni tipiche per i problemi relativi alla capacità

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Problema</th>
<th>Risoluzione possibile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti remoti con scarse prestazioni audio/video</p></td>
<td><p>Verificare se la larghezza di banda appropriata è disponibile nei collegamenti WAN e se QoS è abilitato e configurato in modo appropriato. Controlla i dati QoE.</p></td>
</tr>
<tr class="even">
<td><p>La risposta complessiva dell'ambiente Lync è lenta.</p></td>
<td><p>Eseguire test per verificare che i server front-end esistenti possano gestire il carico. Introdurre un nuovo server front-end, se necessario. Controllare i tempi di risposta del database SQL e correggere le cause dei ritardi, ad esempio migliorare I/O del disco.</p></td>
</tr>
</tbody>
</table>


La risoluzione dei problemi in modo più dettagliato è illustrata nella Guida alla rete di Lync Server.

La capacità è influenzata dalla configurazione di sistema e dipende da risorse fisiche come la larghezza di banda della rete. Ad esempio, se un ambiente Lync è configurato per eseguire un backup completo notturno, è necessario prestare attenzione per garantire che l'effetto sulle prestazioni interattive degli utenti finali sia ridotto a icona.

La gestione della capacità è il processo di mantenimento della capacità di un sistema entro livelli accettabili e risolve i problemi seguenti:

  - **Le modifiche**   apportate ai requisiti di capacità devono essere modificate per tenere conto delle modifiche nel sistema o nell'organizzazione. Ad esempio, se l'ambiente decide di implementare Enterprise Voice, il numero e la posizione di Mediation Server e gateway PSTN (Public Switched Telephone Network) sarà molto importante. Se si esegue il trunking SIP (Session Initiation Protocol) o SIP diretto, la progettazione complessiva verrà modificata in modo significativo per garantire le migliori prestazioni vocali aziendali.

  - **Prevedere requisiti**   futuri alcuni requisiti di capacità cambiano in termini prevedibili nel tempo. Monitorando le tendenze puoi pianificare gli aggiornamenti in anticipo. Ad esempio, la larghezza di banda disponibile tra i vari siti di Lync deve essere monitorata per creare una previsione. Questa previsione consentirà di prevedere quando è necessario aggiungere più larghezza di banda a questi collegamenti Man mano che il conteggio degli utenti in questi siti remoti aumenta con il tempo.

</div>

<div>

## <a name="availability-management"></a>Gestione della disponibilità

La gestione della disponibilità è il processo per verificare che il servizio IT in modo coerente e costiero fornisca efficacemente il livello di servizio affidabile e coerente richiesto dal cliente. La gestione della disponibilità si occupa di ridurre al minimo la perdita di servizio e verificare che venga eseguita un'azione appropriata in caso di perdita del servizio. In un ambiente Lync potrebbe essere preoccupata se il servizio VoIP aziendale è disponibile, se gli utenti possono partecipare a conferenze pianificate e così via. Un contratto di SLA definisce una frequenza e una lunghezza accettabile di interruzioni e consente determinati periodi in cui il sistema non è disponibile per la manutenzione pianificata.

Se è necessario specificare i report per la gestione della disponibilità dei sistemi o se sono presenti penalità finanziarie o di altro tipo associate a destinazioni di disponibilità mancanti, è necessario registrare i dati di disponibilità. Anche se non si dispone di tali requisiti formali, è consigliabile almeno sapere quanto spesso il sistema non è riuscito in un determinato periodo di tempo. Ad esempio, la disponibilità di sistema negli ultimi 12 mesi e quanto tempo ci è voluto per recuperare ogni errore. Queste informazioni ti aiuteranno a misurare e migliorare l'efficacia del team per rispondere a un errore di sistema. Può anche fornirti informazioni utili in caso di controversia.

Le misure correlate alla disponibilità sono le seguenti:

  - **Disponibilità**   questo viene in genere espresso con l'ora in cui è possibile accedere a un sistema o un servizio rispetto al momento in cui è in calo. Viene in genere espresso come percentuale. È possibile che vengano visualizzati riferimenti a "tre nove" o "cinque nove". Questi riferimenti si riferiscono a 99,9% o 99,999 percentuale di disponibilità.

  - **Affidabilità**   si tratta di una misura del tempo tra gli errori di un sistema ed è talvolta espressa come media (o media) tra gli errori (MTBF).

  - **Ora per**   ripristinare questo è il tempo necessario per recuperare un servizio dopo che si è verificato un errore ed è spesso espressa come media (significato medio) tempo di ripristino (MTTR).

La disponibilità, l'affidabilità e il tempo di ripristino sono correlati come segue:

**Availability = (MTBF-MTTR)/MTBF**   ad esempio, se un server non riesce due volte per un periodo di sei mesi e non è disponibile per una media di 20 minuti, l'MTBF è di tre mesi o di 90 giorni e il MTTR è di 20 minuti. Pertanto, disponibilità = (90 giorni-20 minuti)/90 giorni = 99,985%.

La gestione della disponibilità è il processo per garantire che la disponibilità venga ingrandita e mantenuta entro i parametri definiti in SLA. Gestione disponibilità include i processi seguenti:

  - **Monitoraggio**     dell'analisi di quando e per quanto tempo i servizi non sono disponibili.

  - **La segnalazione**   delle cifre sulla disponibilità deve essere fornita regolarmente a team di gestione, utenti e operazioni. Questi report devono evidenziare le tendenze e identificare le aree che stanno procedendo bene e le aree che richiedono attenzione. Il report deve riepilogare la conformità con le destinazioni impostate negli SLA.

  - **Miglioramento**   se la disponibilità non soddisfa le destinazioni definite negli SLA o se la tendenza è rivolta a una disponibilità ridotta, il processo di gestione della disponibilità deve pianificare i passaggi correttivi. Questo dovrebbe includere l'uso di altri team responsabili per evidenziare i motivi per le interruzioni e per pianificare azioni correttive per evitare una ricorrenza delle interruzioni.

Le misure di capacità e disponibilità sono attività ripetitive, ideali per gli strumenti e gli script automatici, come Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), descritto più avanti in questo documento.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Monitoraggio di Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

