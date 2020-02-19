---
title: 'Lync Server 2013: gestione della capacità e della disponibilità'
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
ms.openlocfilehash: ceff744ca9af465d70c8641d5a7538ee1ae3f4eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="8a5a8-102">Gestione della capacità e della disponibilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a5a8-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a5a8-103">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8a5a8-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8a5a8-104">Lo scopo della gestione della capacità e della gestione della disponibilità è misurare e controllare le prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="8a5a8-105">È consigliabile implementare le procedure di gestione della capacità e gestione della disponibilità in modo da poter misurare e controllare le prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="8a5a8-106">È necessario sapere se il sistema è disponibile e se è in grado di gestire le richieste correnti e quelle proiettate impostando le linee di base e monitorando il sistema per individuare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="8a5a8-107">Gestione della capacità</span><span class="sxs-lookup"><span data-stu-id="8a5a8-107">Capacity management</span></span>

<span data-ttu-id="8a5a8-108">La gestione della capacità implica la pianificazione, il dimensionamento e il controllo della capacità del servizio per garantire che vengano superati i livelli minimi di prestazioni specificati nell'SLA.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="8a5a8-109">La buona gestione della capacità consente di fornire servizi IT a un costo ragionevole e di rispettare i livelli di prestazioni definiti nei contratti SLA con il client.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="8a5a8-110">Questi criteri possono includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a5a8-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="8a5a8-111">**Tempo di risposta del sistema**   questo è il tempo misurato che il sistema impiega per eseguire azioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="8a5a8-112">Esempi: il tempo necessario affinché il ruolo del server audio/video elabori il traffico audio/video, il tempo necessario per un client per creare e partecipare a una conferenza oppure il tempo necessario per l'aggiornamento della presenza in tutti i client Watcher.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="8a5a8-113">**Capacità di archiviazione**   questa è la capacità di un sistema di archiviazione, sia che si tratti di un database del contenuto, di un dispositivo di backup o di un'unità locale.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="8a5a8-114">Tra gli esempi sono inclusi la quantità massima di spazio di archiviazione da fornire per sito e l'ora in cui devono essere archiviati i backup prima che vengano sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="8a5a8-115">La regolazione della capacità è spesso un caso in cui sono disponibili sufficienti risorse fisiche, come lo spazio su disco e la larghezza di banda della rete.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="8a5a8-116">Nella tabella seguente sono elencate le risoluzioni tipiche per i problemi relativi alla capacità.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="8a5a8-117">Risoluzioni tipiche per i problemi relativi alla capacità</span><span class="sxs-lookup"><span data-stu-id="8a5a8-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a5a8-118">Problema</span><span class="sxs-lookup"><span data-stu-id="8a5a8-118">Issue</span></span></th>
<th><span data-ttu-id="8a5a8-119">Risoluzione possibile</span><span class="sxs-lookup"><span data-stu-id="8a5a8-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a5a8-120">Utenti remoti con prestazioni audio/video insufficienti</span><span class="sxs-lookup"><span data-stu-id="8a5a8-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="8a5a8-121">Controllare se la larghezza di banda appropriata è disponibile sui collegamenti WAN e se QoS è abilitata e configurata in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="8a5a8-122">Controllare i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a5a8-123">La risposta complessiva dell'ambiente Lync è lenta.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="8a5a8-124">Eseguire test per verificare che i server front-end esistenti siano in grado di gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="8a5a8-125">Se necessario, introdurre un nuovo server front-end. Controllare i tempi di risposta del database SQL e correggere le cause dei ritardi, ad esempio migliorare I/O del disco.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a5a8-126">La risoluzione dei problemi in modo più dettagliato è illustrata nella Guida alla rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="8a5a8-127">La capacità è intaccata dalla configurazione del sistema e dipende da risorse fisiche come la larghezza di banda della rete.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="8a5a8-128">Ad esempio, se un ambiente Lync è configurato per eseguire un backup completo notturno, è necessario prestare particolare attenzione per garantire che l'effetto sulle prestazioni interattive eseguite dagli utenti finali sia ridotto a icona.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="8a5a8-129">La gestione della capacità è il processo per mantenere la capacità di un sistema entro livelli accettabili e per risolvere i problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a5a8-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="8a5a8-130">**Per rispondere alle modifiche**   apportate ai requisiti di capacità, è necessario modificare le modifiche apportate al sistema o all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="8a5a8-131">Ad esempio, se l'ambiente in uso decide di implementare VoIP aziendale, il numero e la posizione dei server Mediation e del gateway PSTN (Public Switched Telephone Network) saranno molto importanti.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="8a5a8-132">Se si esegue il trunking SIP (Session Initiation Protocol) o SIP diretto, la progettazione complessiva verrà modificata in modo significativo per offrire le migliori prestazioni di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="8a5a8-133">**Predizione dei requisiti**   futuri alcuni requisiti di capacità variano in termini prevedibili nel tempo.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="8a5a8-134">Monitorando le tendenze è possibile pianificare gli aggiornamenti in anticipo.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="8a5a8-135">Ad esempio, la larghezza di banda disponibile tra vari siti di Lync deve essere monitorata per creare una linea di base.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="8a5a8-136">Questa linea di base consente di prevedere quando è necessario aggiungere più larghezza di banda a questi collegamenti, in quanto il numero di utenti in questi siti remoti aumenta con il tempo.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="8a5a8-137">Gestione della disponibilità</span><span class="sxs-lookup"><span data-stu-id="8a5a8-137">Availability management</span></span>

<span data-ttu-id="8a5a8-138">La gestione della disponibilità è il processo per garantire che un servizio IT sia coerente e che costi efficacemente il livello di servizio coerente e affidabile richiesto dal cliente.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="8a5a8-139">Gestione della disponibilità consente di ridurre al minimo la perdita di servizio e di verificare che vengano eseguite azioni appropriate in caso di perdita del servizio.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="8a5a8-140">In un ambiente Lync, è possibile preoccuparsi se il servizio VoIP aziendale è disponibile, se gli utenti possono partecipare a conferenze pianificate e così via.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="8a5a8-141">Un contratto di servizio di SLA definisce una frequenza e una lunghezza accettabili di interruzioni e consente alcuni periodi in cui il sistema non è disponibile per la manutenzione pianificata.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="8a5a8-142">Se è necessario fornire relazioni alla gestione sulla disponibilità dei sistemi, o se si dispone di sanzioni finanziarie o di altro tipo associate a obiettivi di disponibilità mancanti, è necessario registrare i dati di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="8a5a8-143">Anche se non si dispone di tali requisiti formali, è consigliabile conoscere almeno la frequenza con cui un sistema ha avuto esito negativo in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="8a5a8-144">Ad esempio, la disponibilità del sistema negli ultimi 12 mesi e il tempo necessario per il ripristino da ogni errore.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="8a5a8-145">Queste informazioni consentono di misurare e migliorare l'efficacia del team nel rispondere a un errore del sistema.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="8a5a8-146">È inoltre possibile fornire informazioni utili se si verifica una controversia.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="8a5a8-147">Le misure relative alla disponibilità sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a5a8-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="8a5a8-148">**Availability**   questo è in genere espresso come l'ora in cui è possibile accedere a un sistema o a un servizio rispetto all'ora in cui è inverso.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="8a5a8-149">In genere viene espressa come percentuale.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="8a5a8-150">È possibile visualizzare i riferimenti a "Three Nines" o "Five Nines".</span><span class="sxs-lookup"><span data-stu-id="8a5a8-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="8a5a8-151">Si riferiscono a 99,9% o 99,999% di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="8a5a8-152">**Attendibilità**   questa è una misura del tempo tra gli errori di un sistema e talvolta viene espressa come media o tempo tra gli errori (MTBF).</span><span class="sxs-lookup"><span data-stu-id="8a5a8-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="8a5a8-153">**Tempo di ripristino**   questo è il tempo necessario per recuperare un servizio dopo che si è verificato un errore ed è spesso espresso come media (significato medio) tempo di ripristino (MTTR).</span><span class="sxs-lookup"><span data-stu-id="8a5a8-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="8a5a8-154">La disponibilità, l'affidabilità e il tempo necessario per il ripristino sono correlati come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8a5a8-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="8a5a8-155">**Availability = (MTBF – MTTR)/MTBF**   ad esempio, se un server ha esito negativo due volte nel corso di un periodo di sei mesi e non è disponibile per una media di 20 minuti, l'MTBF è di tre mesi o 90 giorni e la MTTR è di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="8a5a8-156">Pertanto, disponibilità = (90 giorni – 20 minuti)/90 giorni = 99,985%.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="8a5a8-157">La gestione della disponibilità è il processo per garantire che la disponibilità venga ingrandita e mantenuta entro i parametri definiti nei contratti SLA.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="8a5a8-158">La gestione della disponibilità include i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a5a8-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="8a5a8-159">**Monitoraggio**     dell'esame quando e per quanto tempo i servizi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="8a5a8-160">\*\*\*\*   I dati relativi alla disponibilità dei rapporti devono essere regolarmente forniti ai team di gestione, utenti e operazioni.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="8a5a8-161">Questi rapporti devono evidenziare le tendenze e identificare le aree che stanno facendo bene e le aree che richiedono attenzione.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="8a5a8-162">Il report deve riepilogare la conformità con le destinazioni impostate nei contratti SLA.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="8a5a8-163">**Miglioramento**   se la disponibilità non soddisfa le destinazioni definite nei contratti SLA o in cui la tendenza è verso una disponibilità ridotta, il processo di gestione della disponibilità deve pianificare i passaggi correttivi.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="8a5a8-164">In questo modo, è necessario collaborare con altri team responsabili per evidenziare i motivi di interruzioni e pianificare azioni correttive per impedire la ricorrenza delle interruzioni.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="8a5a8-165">Misure di disponibilità e capacità sono attività ripetitive che sono ideali per gli strumenti e gli script automatici, come Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), descritta più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="8a5a8-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a5a8-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a5a8-166">See Also</span></span>


[<span data-ttu-id="8a5a8-167">Monitoraggio di Lync Server 2013 con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="8a5a8-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

