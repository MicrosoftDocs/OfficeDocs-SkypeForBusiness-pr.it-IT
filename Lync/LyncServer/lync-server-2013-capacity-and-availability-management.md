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

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="50254-102">Gestione della capacità e della disponibilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50254-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50254-103">_**Argomento Ultima modifica:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="50254-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="50254-104">Lo scopo della gestione della gestione delle capacità e della disponibilità è misurare e controllare le prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="50254-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="50254-105">Ti consigliamo di implementare le procedure di gestione della capacità e gestione della disponibilità in modo da misurare e controllare le prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="50254-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="50254-106">È necessario sapere se il sistema è disponibile e se è in grado di gestire le richieste correnti e quelle proiettate impostando le previsioni e monitorando il sistema per cercare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="50254-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="50254-107">Gestione della capacità</span><span class="sxs-lookup"><span data-stu-id="50254-107">Capacity management</span></span>

<span data-ttu-id="50254-108">La gestione della capacità prevede la pianificazione, il dimensionamento e il controllo della capacità del servizio per garantire che vengano superati i livelli minimi di prestazioni specificati nell'SLA.</span><span class="sxs-lookup"><span data-stu-id="50254-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="50254-109">La gestione delle capacità ottimali garantisce la possibilità di fornire servizi IT a costi ragionevoli e rispettare i livelli di prestazioni definiti nei contratti SLA con il client.</span><span class="sxs-lookup"><span data-stu-id="50254-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="50254-110">Questi criteri possono includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="50254-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="50254-111">**Tempo di risposta del sistema**   questo è il tempo misurato che il sistema impiega per eseguire azioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="50254-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="50254-112">Gli esempi includono il tempo necessario per il ruolo del server audio/video per elaborare il traffico audio/video, il tempo necessario per un client per creare e partecipare a una conferenza oppure il tempo necessario per l'aggiornamento della presenza in tutti i client Watcher.</span><span class="sxs-lookup"><span data-stu-id="50254-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="50254-113">**Capacità di archiviazione**   questa è la capacità di un sistema di archiviazione, sia che si tratti di un database del contenuto, di un dispositivo di backup o di un'unità locale.</span><span class="sxs-lookup"><span data-stu-id="50254-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="50254-114">Gli esempi includono la quantità massima di spazio di archiviazione da fornire per ogni sito e l'ora in cui devono essere archiviati i backup prima che vengano sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="50254-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="50254-115">La regolazione della capacità è spesso un caso di verificare che siano disponibili sufficienti risorse fisiche, ad esempio lo spazio su disco e la larghezza di banda della rete.</span><span class="sxs-lookup"><span data-stu-id="50254-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="50254-116">La tabella seguente elenca le risoluzioni tipiche per i problemi relativi alla capacità.</span><span class="sxs-lookup"><span data-stu-id="50254-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="50254-117">Risoluzioni tipiche per i problemi relativi alla capacità</span><span class="sxs-lookup"><span data-stu-id="50254-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50254-118">Problema</span><span class="sxs-lookup"><span data-stu-id="50254-118">Issue</span></span></th>
<th><span data-ttu-id="50254-119">Risoluzione possibile</span><span class="sxs-lookup"><span data-stu-id="50254-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50254-120">Utenti remoti con scarse prestazioni audio/video</span><span class="sxs-lookup"><span data-stu-id="50254-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="50254-121">Verificare se la larghezza di banda appropriata è disponibile nei collegamenti WAN e se QoS è abilitato e configurato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="50254-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="50254-122">Controlla i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="50254-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50254-123">La risposta complessiva dell'ambiente Lync è lenta.</span><span class="sxs-lookup"><span data-stu-id="50254-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="50254-124">Eseguire test per verificare che i server front-end esistenti possano gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="50254-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="50254-125">Introdurre un nuovo server front-end, se necessario. Controllare i tempi di risposta del database SQL e correggere le cause dei ritardi, ad esempio migliorare I/O del disco.</span><span class="sxs-lookup"><span data-stu-id="50254-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="50254-126">La risoluzione dei problemi in modo più dettagliato è illustrata nella Guida alla rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50254-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="50254-127">La capacità è influenzata dalla configurazione di sistema e dipende da risorse fisiche come la larghezza di banda della rete.</span><span class="sxs-lookup"><span data-stu-id="50254-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="50254-128">Ad esempio, se un ambiente Lync è configurato per eseguire un backup completo notturno, è necessario prestare attenzione per garantire che l'effetto sulle prestazioni interattive degli utenti finali sia ridotto a icona.</span><span class="sxs-lookup"><span data-stu-id="50254-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="50254-129">La gestione della capacità è il processo di mantenimento della capacità di un sistema entro livelli accettabili e risolve i problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="50254-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="50254-130">**Le modifiche**   apportate ai requisiti di capacità devono essere modificate per tenere conto delle modifiche nel sistema o nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50254-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="50254-131">Ad esempio, se l'ambiente decide di implementare Enterprise Voice, il numero e la posizione di Mediation Server e gateway PSTN (Public Switched Telephone Network) sarà molto importante.</span><span class="sxs-lookup"><span data-stu-id="50254-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="50254-132">Se si esegue il trunking SIP (Session Initiation Protocol) o SIP diretto, la progettazione complessiva verrà modificata in modo significativo per garantire le migliori prestazioni vocali aziendali.</span><span class="sxs-lookup"><span data-stu-id="50254-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="50254-133">**Prevedere requisiti**   futuri alcuni requisiti di capacità cambiano in termini prevedibili nel tempo.</span><span class="sxs-lookup"><span data-stu-id="50254-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="50254-134">Monitorando le tendenze puoi pianificare gli aggiornamenti in anticipo.</span><span class="sxs-lookup"><span data-stu-id="50254-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="50254-135">Ad esempio, la larghezza di banda disponibile tra i vari siti di Lync deve essere monitorata per creare una previsione.</span><span class="sxs-lookup"><span data-stu-id="50254-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="50254-136">Questa previsione consentirà di prevedere quando è necessario aggiungere più larghezza di banda a questi collegamenti Man mano che il conteggio degli utenti in questi siti remoti aumenta con il tempo.</span><span class="sxs-lookup"><span data-stu-id="50254-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="50254-137">Gestione della disponibilità</span><span class="sxs-lookup"><span data-stu-id="50254-137">Availability management</span></span>

<span data-ttu-id="50254-138">La gestione della disponibilità è il processo per verificare che il servizio IT in modo coerente e costiero fornisca efficacemente il livello di servizio affidabile e coerente richiesto dal cliente.</span><span class="sxs-lookup"><span data-stu-id="50254-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="50254-139">La gestione della disponibilità si occupa di ridurre al minimo la perdita di servizio e verificare che venga eseguita un'azione appropriata in caso di perdita del servizio.</span><span class="sxs-lookup"><span data-stu-id="50254-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="50254-140">In un ambiente Lync potrebbe essere preoccupata se il servizio VoIP aziendale è disponibile, se gli utenti possono partecipare a conferenze pianificate e così via.</span><span class="sxs-lookup"><span data-stu-id="50254-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="50254-141">Un contratto di SLA definisce una frequenza e una lunghezza accettabile di interruzioni e consente determinati periodi in cui il sistema non è disponibile per la manutenzione pianificata.</span><span class="sxs-lookup"><span data-stu-id="50254-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="50254-142">Se è necessario specificare i report per la gestione della disponibilità dei sistemi o se sono presenti penalità finanziarie o di altro tipo associate a destinazioni di disponibilità mancanti, è necessario registrare i dati di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="50254-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="50254-143">Anche se non si dispone di tali requisiti formali, è consigliabile almeno sapere quanto spesso il sistema non è riuscito in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="50254-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="50254-144">Ad esempio, la disponibilità di sistema negli ultimi 12 mesi e quanto tempo ci è voluto per recuperare ogni errore.</span><span class="sxs-lookup"><span data-stu-id="50254-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="50254-145">Queste informazioni ti aiuteranno a misurare e migliorare l'efficacia del team per rispondere a un errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="50254-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="50254-146">Può anche fornirti informazioni utili in caso di controversia.</span><span class="sxs-lookup"><span data-stu-id="50254-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="50254-147">Le misure correlate alla disponibilità sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="50254-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="50254-148">**Disponibilità**   questo viene in genere espresso con l'ora in cui è possibile accedere a un sistema o un servizio rispetto al momento in cui è in calo.</span><span class="sxs-lookup"><span data-stu-id="50254-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="50254-149">Viene in genere espresso come percentuale.</span><span class="sxs-lookup"><span data-stu-id="50254-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="50254-150">È possibile che vengano visualizzati riferimenti a "tre nove" o "cinque nove".</span><span class="sxs-lookup"><span data-stu-id="50254-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="50254-151">Questi riferimenti si riferiscono a 99,9% o 99,999 percentuale di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="50254-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="50254-152">**Affidabilità**   si tratta di una misura del tempo tra gli errori di un sistema ed è talvolta espressa come media (o media) tra gli errori (MTBF).</span><span class="sxs-lookup"><span data-stu-id="50254-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="50254-153">**Ora per**   ripristinare questo è il tempo necessario per recuperare un servizio dopo che si è verificato un errore ed è spesso espressa come media (significato medio) tempo di ripristino (MTTR).</span><span class="sxs-lookup"><span data-stu-id="50254-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="50254-154">La disponibilità, l'affidabilità e il tempo di ripristino sono correlati come segue:</span><span class="sxs-lookup"><span data-stu-id="50254-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="50254-155">**Availability = (MTBF-MTTR)/MTBF**   ad esempio, se un server non riesce due volte per un periodo di sei mesi e non è disponibile per una media di 20 minuti, l'MTBF è di tre mesi o di 90 giorni e il MTTR è di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="50254-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="50254-156">Pertanto, disponibilità = (90 giorni-20 minuti)/90 giorni = 99,985%.</span><span class="sxs-lookup"><span data-stu-id="50254-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="50254-157">La gestione della disponibilità è il processo per garantire che la disponibilità venga ingrandita e mantenuta entro i parametri definiti in SLA.</span><span class="sxs-lookup"><span data-stu-id="50254-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="50254-158">Gestione disponibilità include i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="50254-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="50254-159">**Monitoraggio**     dell'analisi di quando e per quanto tempo i servizi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="50254-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="50254-160">**La segnalazione**   delle cifre sulla disponibilità deve essere fornita regolarmente a team di gestione, utenti e operazioni.</span><span class="sxs-lookup"><span data-stu-id="50254-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="50254-161">Questi report devono evidenziare le tendenze e identificare le aree che stanno procedendo bene e le aree che richiedono attenzione.</span><span class="sxs-lookup"><span data-stu-id="50254-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="50254-162">Il report deve riepilogare la conformità con le destinazioni impostate negli SLA.</span><span class="sxs-lookup"><span data-stu-id="50254-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="50254-163">**Miglioramento**   se la disponibilità non soddisfa le destinazioni definite negli SLA o se la tendenza è rivolta a una disponibilità ridotta, il processo di gestione della disponibilità deve pianificare i passaggi correttivi.</span><span class="sxs-lookup"><span data-stu-id="50254-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="50254-164">Questo dovrebbe includere l'uso di altri team responsabili per evidenziare i motivi per le interruzioni e per pianificare azioni correttive per evitare una ricorrenza delle interruzioni.</span><span class="sxs-lookup"><span data-stu-id="50254-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="50254-165">Le misure di capacità e disponibilità sono attività ripetitive, ideali per gli strumenti e gli script automatici, come Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), descritto più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="50254-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50254-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50254-166">See Also</span></span>


[<span data-ttu-id="50254-167">Monitoraggio di Lync Server 2013 con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="50254-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

