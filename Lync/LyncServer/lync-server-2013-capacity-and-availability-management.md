---
title: 'Lync Server 2013: gestione della capacità e della disponibilità'
description: 'Lync Server 2013: gestione della capacità e della disponibilità.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565152"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Gestione della capacità e della disponibilità in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-18_

Lo scopo della gestione della capacità e della gestione della disponibilità è misurare e controllare le prestazioni del sistema. È consigliabile implementare le procedure di gestione della capacità e gestione della disponibilità in modo da poter misurare e controllare le prestazioni del sistema. È necessario sapere se il sistema è disponibile e se è in grado di gestire le richieste correnti e quelle proiettate impostando le linee di base e monitorando il sistema per individuare le tendenze.

<div>

## <a name="capacity-management"></a>Gestione della capacità

La gestione della capacità implica la pianificazione, il dimensionamento e il controllo della capacità del servizio per garantire che vengano superati i livelli minimi di prestazioni specificati nell'SLA. La buona gestione della capacità consente di fornire servizi IT a un costo ragionevole e di rispettare i livelli di prestazioni definiti nei contratti SLA con il client. Questi criteri possono includere gli elementi seguenti:

  - Tempo di risposta del **sistema**     Questo è il tempo misurato che il sistema impiega per eseguire azioni tipiche. Esempi: il tempo necessario affinché il ruolo del server audio/video elabori il traffico audio/video, il tempo necessario per un client per creare e partecipare a una conferenza oppure il tempo necessario per l'aggiornamento della presenza in tutti i client Watcher.

  - **Capacità**     di archiviazione Questa è la capacità di un sistema di archiviazione, sia che si tratti di un database del contenuto, di un dispositivo di backup o di un'unità locale. Tra gli esempi sono inclusi la quantità massima di spazio di archiviazione da fornire per sito e l'ora in cui devono essere archiviati i backup prima che vengano sovrascritti.

La regolazione della capacità è spesso un caso in cui sono disponibili sufficienti risorse fisiche, come lo spazio su disco e la larghezza di banda della rete. Nella tabella seguente sono elencate le risoluzioni tipiche per i problemi relativi alla capacità.

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
<td><p>Utenti remoti con prestazioni audio/video insufficienti</p></td>
<td><p>Controllare se la larghezza di banda appropriata è disponibile sui collegamenti WAN e se QoS è abilitata e configurata in modo appropriato. Controllare i dati QoE.</p></td>
</tr>
<tr class="even">
<td><p>La risposta complessiva dell'ambiente Lync è lenta.</p></td>
<td><p>Eseguire test per verificare che i server front-end esistenti siano in grado di gestire il carico. Se necessario, introdurre un nuovo server front-end. Controllare i tempi di risposta del database SQL e correggere le cause dei ritardi, ad esempio migliorare I/O del disco.</p></td>
</tr>
</tbody>
</table>


La risoluzione dei problemi in modo più dettagliato è illustrata nella Guida alla rete di Lync Server.

La capacità è intaccata dalla configurazione del sistema e dipende da risorse fisiche come la larghezza di banda della rete. Ad esempio, se un ambiente Lync è configurato per eseguire un backup completo notturno, è necessario prestare particolare attenzione per garantire che l'effetto sulle prestazioni interattive eseguite dagli utenti finali sia ridotto a icona.

La gestione della capacità è il processo per mantenere la capacità di un sistema entro livelli accettabili e per risolvere i problemi seguenti:

  - **Reagire alle modifiche dei requisiti**     I requisiti di capacità devono essere adeguati per tenere conto delle modifiche apportate al sistema o all'organizzazione. Ad esempio, se l'ambiente in uso decide di implementare VoIP aziendale, il numero e la posizione dei server Mediation e del gateway PSTN (Public Switched Telephone Network) saranno molto importanti. Se si esegue il trunking SIP (Session Initiation Protocol) o SIP diretto, la progettazione complessiva verrà modificata in modo significativo per offrire le migliori prestazioni di VoIP aziendale.

  - **Predizione dei requisiti futuri**     Alcuni requisiti di capacità variano in termini prevedibili nel tempo. Monitorando le tendenze è possibile pianificare gli aggiornamenti in anticipo. Ad esempio, la larghezza di banda disponibile tra vari siti di Lync deve essere monitorata per creare una linea di base. Questa linea di base consente di prevedere quando è necessario aggiungere più larghezza di banda a questi collegamenti, in quanto il numero di utenti in questi siti remoti aumenta con il tempo.

</div>

<div>

## <a name="availability-management"></a>Gestione della disponibilità

La gestione della disponibilità è il processo per garantire che un servizio IT sia coerente e che costi efficacemente il livello di servizio coerente e affidabile richiesto dal cliente. Gestione della disponibilità consente di ridurre al minimo la perdita di servizio e di verificare che vengano eseguite azioni appropriate in caso di perdita del servizio. In un ambiente Lync, è possibile preoccuparsi se il servizio VoIP aziendale è disponibile, se gli utenti possono partecipare a conferenze pianificate e così via. Un contratto di servizio di SLA definisce una frequenza e una lunghezza accettabili di interruzioni e consente alcuni periodi in cui il sistema non è disponibile per la manutenzione pianificata.

Se è necessario fornire relazioni alla gestione sulla disponibilità dei sistemi, o se si dispone di sanzioni finanziarie o di altro tipo associate a obiettivi di disponibilità mancanti, è necessario registrare i dati di disponibilità. Anche se non si dispone di tali requisiti formali, è consigliabile conoscere almeno la frequenza con cui un sistema ha avuto esito negativo in un determinato periodo di tempo. Ad esempio, la disponibilità del sistema negli ultimi 12 mesi e il tempo necessario per il ripristino da ogni errore. Queste informazioni consentono di misurare e migliorare l'efficacia del team nel rispondere a un errore del sistema. È inoltre possibile fornire informazioni utili se si verifica una controversia.

Le misure relative alla disponibilità sono le seguenti:

  - **Disponibilità**     Questo è in genere espresso come l'ora in cui è possibile accedere a un sistema o a un servizio rispetto all'ora in cui è inverso. In genere viene espressa come percentuale. È possibile visualizzare i riferimenti a "Three Nines" o "Five Nines". Si riferiscono a 99,9% o 99,999% di disponibilità.

  - **Affidabilità**     Si tratta di una misura del tempo tra gli errori di un sistema e a volte è espressa come media (o media) tempo tra gli errori (MTBF).

  - **Tempo di ripristino**     Questo è il tempo necessario per il ripristino di un servizio dopo che si è verificato un errore ed è spesso espresso come media (significato medio) tempo di ripristino (MTTR).

La disponibilità, l'affidabilità e il tempo necessario per il ripristino sono correlati come indicato di seguito:

**Disponibilità = (MTBF – MTTR)/MTBF**     Ad esempio, se un server ha esito negativo due volte nel corso di un periodo di sei mesi e non è disponibile per una media di 20 minuti, l'MTBF è di tre mesi o 90 giorni e la MTTR è di 20 minuti. Pertanto, disponibilità = (90 giorni – 20 minuti)/90 giorni = 99,985%.

La gestione della disponibilità è il processo per garantire che la disponibilità venga ingrandita e mantenuta entro i parametri definiti nei contratti SLA. La gestione della disponibilità include i processi seguenti:

  - **Monitoraggio**     Esaminare quando e per quanto tempo i servizi non sono disponibili.

  - **Creazione di report**     Le cifre sulla disponibilità devono essere regolarmente fornite ai team di gestione, utenti e operazioni. Questi rapporti devono evidenziare le tendenze e identificare le aree che stanno facendo bene e le aree che richiedono attenzione. Il report deve riepilogare la conformità con le destinazioni impostate nei contratti SLA.

  - **Miglioramento**     Se la disponibilità non soddisfa le destinazioni definite nei contratti SLA o in cui l'andamento è verso una disponibilità ridotta, il processo di gestione della disponibilità deve pianificare i passaggi correttivi. In questo modo, è necessario collaborare con altri team responsabili per evidenziare i motivi di interruzioni e pianificare azioni correttive per impedire la ricorrenza delle interruzioni.

Misure di disponibilità e capacità sono attività ripetitive che sono ideali per gli strumenti e gli script automatici, come Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), descritta più avanti in questo documento.

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

