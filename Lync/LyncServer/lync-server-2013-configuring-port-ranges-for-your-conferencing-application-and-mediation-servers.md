---
title: "Lync Server 2013: configurazione degli intervalli di porte per le conferenze, l'applicazione e i Mediation Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb91667406fe2c4ed292f9b0b6b85e69c2e4e256
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="81016-102">Configurazione degli intervalli di porte in Lync Server 2013 per i servizi di conferenza, applicazione e Mediation Server</span><span class="sxs-lookup"><span data-stu-id="81016-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81016-103">_**Ultimo argomento modificato:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="81016-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="81016-p101">Per implementare Qualità del servizio, è necessario configurare intervalli di porte identici per la condivisione di audio, video e applicazioni sui server per conferenze, sui server applicazioni e sui Mediation Server. Questi intervalli non devono sovrapporsi in alcun modo. Ecco un semplice esempio. Supponiamo di usare le porte 10000-10999 dei server per conferenze per il video. Questo significa che le stesse porte devono essere riservate alle funzioni video anche sui server applicazioni e sui Mediation Server. in caso contrario, QoS non funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="81016-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="81016-p102">Analogamente, supponiamo di riservare le porte 10000-10999 per il video e le porte 10500-11999 per l'audio. Questa configurazione crea problemi al funzionamento di Qualità del servizio, perché gli intervalli delle porte si sovrappongono. Con QoS ogni modalità deve disporre di un set di porte esclusivo. Se si usano le porte 10000-10999 per il video, è necessario usare un altro intervallo, ad esempio 11000-11999, per l'audio.</span><span class="sxs-lookup"><span data-stu-id="81016-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="81016-111">Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Microsoft Lync Server 2013; Tuttavia, gli intervalli di porte assegnati alla sovrapposizione di condivisione delle applicazioni con gli intervalli di porte audio e video.</span><span class="sxs-lookup"><span data-stu-id="81016-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="81016-112">Che, a sua incirca, significa che nessuno di questi intervalli è univoco. È possibile verificare gli intervalli di porte esistenti per i servizi di conferenza, applicazione e Mediation Server eseguendo i tre comandi seguenti dall'interno di Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="81016-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="81016-p104">Come si vede nei comandi precedenti, a ciascun tipo di porta (audio, video e condivisione di applicazioni) sono assegnati due valori di proprietà separati: PortStart e PortCount. PortStart indica la prima porta usata per la modalità in questione. Ad esempio, se AudioPortStart corrisponde a 50000, significa che la prima porta usata per il traffico audio è la porta 50000. Se AudioPortCount corrisponde a 2 (che non è un valore valido, ma che useremo qui puramente a titolo di esempio), significa che per l'audio sono allocate solo due porte. Se la prima porta è la porta 50000 e ci sono due porte in tutto, la seconda porta deve essere la porta 50001 (negli intervalli di porte le porte devono essere contigue). Di conseguenza, l'intervallo di porte per l'audio deve essere costituito dalle porte da 50000 a 50001 comprese.</span><span class="sxs-lookup"><span data-stu-id="81016-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="81016-118">Si noti anche che i server applicazioni e i Mediation Server supportano QoS solo per l'audio. Per questi server non è quindi necessario modificare le porte di condivisione video o applicazioni.</span><span class="sxs-lookup"><span data-stu-id="81016-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="81016-119">Se si eseguono i tre comandi precedenti, si noterà che i valori di porta predefiniti per Lync Server 2013 sono configurati in questo modo:</span><span class="sxs-lookup"><span data-stu-id="81016-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81016-120">Proprietà</span><span class="sxs-lookup"><span data-stu-id="81016-120">Property</span></span></th>
<th><span data-ttu-id="81016-121">Server per conferenze</span><span class="sxs-lookup"><span data-stu-id="81016-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="81016-122">Server applicazioni</span><span class="sxs-lookup"><span data-stu-id="81016-122">Application Server</span></span></th>
<th><span data-ttu-id="81016-123">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="81016-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81016-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="81016-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="81016-125">49152</span><span class="sxs-lookup"><span data-stu-id="81016-125">49152</span></span></p></td>
<td><p><span data-ttu-id="81016-126">49152</span><span class="sxs-lookup"><span data-stu-id="81016-126">49152</span></span></p></td>
<td><p><span data-ttu-id="81016-127">49152</span><span class="sxs-lookup"><span data-stu-id="81016-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81016-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="81016-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="81016-129">8348</span><span class="sxs-lookup"><span data-stu-id="81016-129">8348</span></span></p></td>
<td><p><span data-ttu-id="81016-130">8348</span><span class="sxs-lookup"><span data-stu-id="81016-130">8348</span></span></p></td>
<td><p><span data-ttu-id="81016-131">8348</span><span class="sxs-lookup"><span data-stu-id="81016-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81016-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="81016-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="81016-133">57501</span><span class="sxs-lookup"><span data-stu-id="81016-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81016-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="81016-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="81016-135">8034</span><span class="sxs-lookup"><span data-stu-id="81016-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81016-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="81016-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="81016-137">49152</span><span class="sxs-lookup"><span data-stu-id="81016-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81016-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="81016-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="81016-139">16383</span><span class="sxs-lookup"><span data-stu-id="81016-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="81016-140">Come indicato in precedenza, quando si configurano le porte di Lync Server per QoS, è necessario assicurarsi che: 1) le impostazioni della porta audio siano identiche tra i propri servizi di conferenza, applicazioni e Mediation Server. e 2) gli intervalli di porte non si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="81016-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="81016-141">Se si osserva la tabella precedente, si nota che gli intervalli di porte sono identici per i tre tipi di server.</span><span class="sxs-lookup"><span data-stu-id="81016-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="81016-142">Ad esempio, la porta audio iniziale corrisponde alla porta 49152 per ciascun tipo di server.</span><span class="sxs-lookup"><span data-stu-id="81016-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="81016-143">Anche il numero totale di porte riservate all'audio in ciascun server è identico: 8348.</span><span class="sxs-lookup"><span data-stu-id="81016-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="81016-144">Tuttavia gli intervalli di porte si sovrappongono: le porte audio iniziano in corrispondenza della porta 49152, ma lo stesso avviene per le porte riservate alla condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="81016-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="81016-145">Per ottimizzare l'uso di Quality of Service, è necessario riconfigurare la condivisione delle applicazioni in modo che usi un intervallo esclusivo, ad esempio impostando l'inizio alla porta 40803 e l'uso di 8348 porte.</span><span class="sxs-lookup"><span data-stu-id="81016-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="81016-146">Perché 8348 porte?</span><span class="sxs-lookup"><span data-stu-id="81016-146">(Why 8348 ports?</span></span> <span data-ttu-id="81016-147">Se si aggiungono questi valori insieme--40803 + 8348--questo significa che la condivisione di applicazioni utilizzerà le porte 40803 tramite la porta 49150.</span><span class="sxs-lookup"><span data-stu-id="81016-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="81016-148">Poiché le porte audio iniziano con la porta 49152, gli intervalli di porte non si sovrappongono più.</span><span class="sxs-lookup"><span data-stu-id="81016-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="81016-p106">Dopo aver selezionato il nuovo intervallo di porte per la condivisione applicazioni, è possibile eseguire la modifica mediante il cmdlet Set-CsConferencingServer. Questa modifica non è necessaria per i server applicazioni e i Mediation Server, perché questi server non gestiscono il traffico relativo alla condivisione applicazioni. Per questi server i valori delle porte devono essere modificati solo se si decide di riassegnare le porte usate per il traffico audio.</span><span class="sxs-lookup"><span data-stu-id="81016-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="81016-152">Per modificare i valori delle porte per la condivisione delle applicazioni in un singolo server Conferencing, eseguire un comando simile a questo dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="81016-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="81016-153">Se invece si vogliono eseguire queste modifiche in tutti i server per conferenze, è possibile eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="81016-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="81016-154">Dopo la modifica delle impostazioni relative alle porte, è necessario arrestare e riavviare tutti i servizi interessati dalle modifiche.</span><span class="sxs-lookup"><span data-stu-id="81016-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="81016-p107">Non è obbligatorio che i server per conferenze, i server applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte. L'unico requisito è che ogni server abbia un intervallo di porte esclusivo. Tuttavia, in genere l'amministrazione è più semplice se si usa lo stesso intervallo di porte per tutti i server.</span><span class="sxs-lookup"><span data-stu-id="81016-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

