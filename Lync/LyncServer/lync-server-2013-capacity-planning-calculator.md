---
title: Lync Server 2013 Capacity Planning Calculator
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5ece90e8db4240eaef00f39a827e6779663dcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="24dee-102">Utilizzo del calcolatore di pianificazione della capacità per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24dee-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24dee-103">_**Ultimo argomento modificato:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="24dee-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="24dee-104">Microsoft® Lync™ Server 2013 Capacity Planning Calculator è disponibile per il download <http://www.microsoft.com/download/details.aspx?id=36828>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="24dee-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="24dee-105">È stato creato per facilitare la determinazione dei requisiti del server in base al numero di utenti e alle modalità di comunicazione abilitate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24dee-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="24dee-106">Immettere il profilo dell'organizzazione e la calcolatrice fornisce consigli utili per la pianificazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="24dee-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="24dee-107">I suggerimenti creati dalla calcolatrice sono solo a scopo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="24dee-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="24dee-108">È necessaria una simulazione di carico effettiva per garantire che Lync Server 2013 sia adeguatamente provisioning.</span><span class="sxs-lookup"><span data-stu-id="24dee-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="24dee-109">Per eseguire il test di stress con un carico simulato, utilizzare lo strumento di analisi [dello stress e delle prestazioni di Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="24dee-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="24dee-110">Dopo aver determinato il profilo utente e le modalità che si desidera abilitare per gli utenti, è opportuno utilizzare la calcolatrice per pianificare il numero di server, la memoria e la larghezza di banda necessaria.</span><span class="sxs-lookup"><span data-stu-id="24dee-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="24dee-111">Questa versione della calcolatrice non fornisce indicazioni per I requisiti di I/O su disco.</span><span class="sxs-lookup"><span data-stu-id="24dee-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="24dee-112">Questo calcolatore è complementare a [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) e [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="24dee-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="24dee-113">Utilizzare la calcolatrice dopo aver esaminato la guida e aver creato una topologia consigliata tramite lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="24dee-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="24dee-114">Se si dispone di informazioni accurate e dettagliate sul profilo utente specifico, è possibile trarre vantaggio dalla calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="24dee-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="24dee-115">Ad esempio, la percentuale di utenti abilitati per la voce, le chiamate medie per utente all'ora, la durata delle chiamate e la percentuale di utenti simultanei nelle conferenze possono fare una differenza enorme nei requisiti del server.</span><span class="sxs-lookup"><span data-stu-id="24dee-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="24dee-116">L'accuratezza dei suggerimenti creati dalla calcolatrice dipende dall'accuratezza delle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="24dee-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="24dee-117">Utilizzo del calcolatore capacità</span><span class="sxs-lookup"><span data-stu-id="24dee-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="24dee-118">La calcolatrice è un foglio di calcolo di Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="24dee-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="24dee-119">Le celle di colore arancione sono per l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="24dee-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="24dee-120">I valori predefiniti vengono immessi (80.000 utenti in un pool con dodici Front End Server), ma è possibile modificare questi valori in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24dee-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="24dee-121">Il modello di utilizzo contiene le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="24dee-121">The usage model contains the following sections.</span></span> <span data-ttu-id="24dee-122">Per calcolare i requisiti di capacità, immettere i dati come descritto di:</span><span class="sxs-lookup"><span data-stu-id="24dee-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="24dee-123">**Messaggistica istantanea e presenza**</span><span class="sxs-lookup"><span data-stu-id="24dee-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="24dee-124">In numero di utenti digitare il numero di utenti a cui verrà effettuato l'accesso simultaneo.</span><span class="sxs-lookup"><span data-stu-id="24dee-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="24dee-125">Questo numero è in genere 80% del numero totale di utenti di cui è stato effettuato il provisioning.</span><span class="sxs-lookup"><span data-stu-id="24dee-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="24dee-126">Nella maggior parte dei casi, il 100% degli utenti simultanei verrà abilitato per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="24dee-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="24dee-127">Il valore predefinito è 80.000.</span><span class="sxs-lookup"><span data-stu-id="24dee-127">The default is 80,000.</span></span>

  - <span data-ttu-id="24dee-128">Numero medio di contatti nell'elenco contatti indica il numero di contatti utilizzati per convalidare i requisiti di sistema.</span><span class="sxs-lookup"><span data-stu-id="24dee-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="24dee-129">Questo numero non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="24dee-129">This number is not changeable.</span></span>

<span data-ttu-id="24dee-130">**VoIP aziendale**</span><span class="sxs-lookup"><span data-stu-id="24dee-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="24dee-131">In utenti abilitati per VoIP aziendale, digitare la percentuale di utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="24dee-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="24dee-132">Il valore predefinito è 60%.</span><span class="sxs-lookup"><span data-stu-id="24dee-132">The default is 60%.</span></span>

  - <span data-ttu-id="24dee-133">In media il numero di chiamate per utente all'ora (picco), digitare il numero di chiamate all'ora in cui si prevede che l'utente medio partecipi in periodi di carico di picco.</span><span class="sxs-lookup"><span data-stu-id="24dee-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="24dee-134">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="24dee-134">The default is 4.</span></span>

  - <span data-ttu-id="24dee-135">In percentuale delle chiamate che utilizzano il bypass multimediale, digitare la percentuale di chiamate effettuate dagli utenti che ignoreranno il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="24dee-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="24dee-136">Il valore predefinito è 65%.</span><span class="sxs-lookup"><span data-stu-id="24dee-136">The default is 65%.</span></span>

  - <span data-ttu-id="24dee-137">In percentuale degli utenti vocali coinvolti nelle chiamate di messaggistica UNIFICAta PSTN, digitare la percentuale delle chiamate dell'organizzazione che sono chiamate telefoniche UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="24dee-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="24dee-138">Il valore predefinito è 60%</span><span class="sxs-lookup"><span data-stu-id="24dee-138">The default is 60%</span></span>

  - <span data-ttu-id="24dee-139">In percentuale di utenti vocali coinvolti nelle chiamate UC-UC viene visualizzata la percentuale di utenti abilitati per VoIP aziendale che verranno abilitati solo per le chiamate UC-UC.</span><span class="sxs-lookup"><span data-stu-id="24dee-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="24dee-140">Questo numero viene calcolato in base all'input per la percentuale di utenti vocali abilitati per le chiamate UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="24dee-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="24dee-141">**Conferenza**</span><span class="sxs-lookup"><span data-stu-id="24dee-141">**Conferencing**</span></span>

  - <span data-ttu-id="24dee-142">In percentuale degli utenti nelle conferenze simultanee, digitare la percentuale di utenti che parteciperanno contemporaneamente a conferenze.</span><span class="sxs-lookup"><span data-stu-id="24dee-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="24dee-143">Il valore predefinito è 5%.</span><span class="sxs-lookup"><span data-stu-id="24dee-143">The default is 5%.</span></span>

  - <span data-ttu-id="24dee-144">In percentuale delle conferenze con solo gruppo di messaggistica istantanea (nessuna voce), digitare la percentuale di conferenze le cui conferenze coinvolgono solo la messaggistica istantanea; ovvero, che non includono un componente audio.</span><span class="sxs-lookup"><span data-stu-id="24dee-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="24dee-145">Il valore predefinito è 10%</span><span class="sxs-lookup"><span data-stu-id="24dee-145">The default is 10%</span></span>

  - <span data-ttu-id="24dee-146">In percentuale di utenti che utilizzano le conferenze telefoniche con accesso esterno, digitare la percentuale di partecipanti simultanei alle conferenze che utilizzeranno le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="24dee-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="24dee-147">Il valore predefinito è 15%.</span><span class="sxs-lookup"><span data-stu-id="24dee-147">The default is 15%.</span></span>

  - <span data-ttu-id="24dee-148">In percentuale delle conferenze che utilizzano la voce, digitare la percentuale di conferenze che includerà un componente audio.</span><span class="sxs-lookup"><span data-stu-id="24dee-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="24dee-149">Se il 20% delle conferenze vocali includerà anche un video normale, selezionare la casella di controllo Includi video (nessuna visualizzazione multipla).</span><span class="sxs-lookup"><span data-stu-id="24dee-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="24dee-150">Se il 20% delle conferenze includerà anche video con più visualizzazioni, selezionare la casella di controllo Includi Multi View.</span><span class="sxs-lookup"><span data-stu-id="24dee-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="24dee-151">Se il 50% delle conferenze vocali includerà anche la condivisione di applicazioni, selezionare la casella di controllo Includi la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="24dee-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="24dee-152">Se il 20% delle conferenze vocali include i caricamenti di dati, ad esempio le presentazioni di Microsoft PowerPoint®, selezionare la casella di controllo Includi Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="24dee-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="24dee-153">**Mobilità**</span><span class="sxs-lookup"><span data-stu-id="24dee-153">**Mobility**</span></span>

  - <span data-ttu-id="24dee-154">In percentuale degli utenti abilitati per la mobilità, digitare la percentuale di utenti che saranno abilitati per la connessione a Lync Server tramite dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="24dee-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="24dee-155">Il valore predefinito è 40%.</span><span class="sxs-lookup"><span data-stu-id="24dee-155">The default is 40%.</span></span>

<span data-ttu-id="24dee-156">Dopo aver immesso tutte le informazioni necessarie, la calcolatrice della capacità stima i propri requisiti.</span><span class="sxs-lookup"><span data-stu-id="24dee-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="24dee-157">Le celle gialle mostrano i valori calcolati per i requisiti di CPU, memoria e larghezza di banda in base ai test eseguiti in Lync Server 2013 Performance Labs.</span><span class="sxs-lookup"><span data-stu-id="24dee-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="24dee-158">I numeri sono forniti come linee guida, non ogni singola variante viene testata e convalidata.</span><span class="sxs-lookup"><span data-stu-id="24dee-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="24dee-159">Vengono calcolati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="24dee-159">The following values are calculated:</span></span>

  - <span data-ttu-id="24dee-160">CPU front-end: percentuale di utilizzo della CPU se l'intero carico veniva gestito da un front end server delle stesse specifiche del server utilizzato in Microsoft testing.</span><span class="sxs-lookup"><span data-stu-id="24dee-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="24dee-161">Rete in Mbps: requisiti di larghezza di banda in megabit al secondo (Mbps) per il carico di lavoro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="24dee-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="24dee-162">Memoria in GB: memoria necessaria in gigabyte (GB) per il carico di lavoro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="24dee-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="24dee-163">Le celle verdi mostrano suggerimenti per il modello di utilizzo immesso.</span><span class="sxs-lookup"><span data-stu-id="24dee-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="24dee-164">Total front end server: il numero di server fisici necessari si basa su server dedicati che eseguono Lync Server 2013 con processore duale, hex-core, con 2.260 megacicli.</span><span class="sxs-lookup"><span data-stu-id="24dee-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="24dee-165">Si noti che è consigliabile abilitare l'Hyper-Threading ed è stato dimostrato che è possibile migliorare le prestazioni per i server che supportano audio/video.</span><span class="sxs-lookup"><span data-stu-id="24dee-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="24dee-166">Server perimetrali: il numero di server perimetrali necessari, in base al 30% di tutti gli utenti simultanei che comunicano con i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="24dee-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="24dee-167">Questa percentuale non può essere modificata nella calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="24dee-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="24dee-168">Archiviazione/registrazione dettagli chiamata/archivio qualità dei servizi di esperienza: il numero di archivi necessari per le funzionalità di archiviazione o di monitoraggio, se sono abilitati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24dee-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="24dee-169">Server database back-end necessario (pool necessari): il numero di server di database back-end necessari per il supporto del carico di lavoro selezionato.</span><span class="sxs-lookup"><span data-stu-id="24dee-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="24dee-170">Inoltre, nella riga accanto a Total front end server, vengono fornite ulteriori informazioni sul carico sui server e sulla rete per tutti i carichi di lavoro pianificati combinati.</span><span class="sxs-lookup"><span data-stu-id="24dee-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="24dee-171">Carico medio della CPU: l'utilizzo medio della CPU per Front End Server.</span><span class="sxs-lookup"><span data-stu-id="24dee-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="24dee-172">Rete in Mbps: l'allocazione di larghezza di banda necessaria per supportare il modello di utilizzo immesso.</span><span class="sxs-lookup"><span data-stu-id="24dee-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="24dee-173">Memoria in GB: memoria, in gigabyte, obbligatoria per ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="24dee-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="24dee-174">Adattamento delle cifre ai processori disponibili</span><span class="sxs-lookup"><span data-stu-id="24dee-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="24dee-175">Tutte le figure di utilizzo della CPU nel foglio di calcolo presuppongono che ogni server disponga di un processore duale, un hex-core con 2,26 GHz, almeno 32 GB di memoria e 8 o più unità disco rigido a 10.000-RPM con almeno 72 GB di spazio libero su disco.</span><span class="sxs-lookup"><span data-stu-id="24dee-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="24dee-176">Se nei server sono disponibili processori diversi, è possibile modificare le figure in modo che corrispondano all'hardware.</span><span class="sxs-lookup"><span data-stu-id="24dee-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

