---
title: 'Lync Server 2013: configurazione degli intervalli di porte per le conferenze, le applicazioni e i server di mediazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="0a258-102">Configurazione di intervalli di porte in Lync Server 2013 per i servizi di conferenza, applicazione e mediazione</span><span class="sxs-lookup"><span data-stu-id="0a258-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a258-103">_**Argomento Ultima modifica:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="0a258-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="0a258-104">Per implementare la qualità del servizio, è necessario configurare intervalli di porte identici per la condivisione di audio, video e applicazioni in servizi di conferenza, applicazione e mediazione; Inoltre, questi intervalli di porte non devono sovrapporsi in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="0a258-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="0a258-105">Per usare un semplice esempio, supponiamo di usare le porte da 10000 a 10999 per il video nei server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a258-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="0a258-106">Ciò significa che devi anche prenotare le porte da 10000 a 10999 per il video nell'applicazione e nei server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="0a258-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="0a258-107">In caso contrario, QoS non funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="0a258-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="0a258-108">Allo stesso modo, supponiamo di prenotare le porte da 10000 a 10999 per il video, ma di prenotare le porte da 10500 a 11999 per l'audio.</span><span class="sxs-lookup"><span data-stu-id="0a258-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="0a258-109">Ciò può creare problemi per la qualità del servizio, perché gli intervalli di porte si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="0a258-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="0a258-110">Con QoS ogni modalità deve avere un set di porte univoco: se si usano le porte da 10000 a 10999 per il video, è necessario usare un intervallo diverso, ad esempio da 11000 a 11999 per l'audio.</span><span class="sxs-lookup"><span data-stu-id="0a258-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="0a258-111">Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Microsoft Lync Server 2013; Tuttavia, gli intervalli di porte assegnati alla sovrapposizione di condivisione delle applicazioni con gli intervalli di porte audio e video.</span><span class="sxs-lookup"><span data-stu-id="0a258-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="0a258-112">Il che, a sua volta, indica che nessuno di questi intervalli è univoco. Puoi verificare gli intervalli di porte esistenti per i servizi di conferenza, applicazione e mediazione eseguendo i seguenti tre comandi dall'interno di Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="0a258-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="0a258-113">Come si può vedere nei comandi precedenti, ogni tipo di porta-audio, video e condivisione applicazioni-viene assegnato due valori di proprietà distinti: l'inizio della porta e il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="0a258-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="0a258-114">L'inizio della porta indica la prima porta usata per tale modalità; ad esempio, se la porta audio Start è uguale a 50000, significa che la prima porta usata per il traffico audio è la porta 50000.</span><span class="sxs-lookup"><span data-stu-id="0a258-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="0a258-115">Se il numero di porta audio è 2 (che non è un valore valido, ma viene usato qui per scopi illustrativi), ciò significa che solo 2 porte vengono allocate per l'audio.</span><span class="sxs-lookup"><span data-stu-id="0a258-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="0a258-116">Se la prima porta è la porta 50000 e sono presenti un totale di due porte, significa che la seconda porta deve essere la porta 50001 (gli intervalli di porta devono essere contigui).</span><span class="sxs-lookup"><span data-stu-id="0a258-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="0a258-117">Di conseguenza, l'intervallo di porte per l'audio sarebbe porte da 50000 a 50001, inclusi.</span><span class="sxs-lookup"><span data-stu-id="0a258-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="0a258-118">Nota anche che Application Server e Mediation Server supportano solo QoS per l'audio; non è necessario modificare le porte di condivisione di video o applicazioni nei server delle applicazioni o nei server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="0a258-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="0a258-119">Se si eseguono i tre comandi precedenti, si noterà che i valori di porta predefiniti per Lync Server 2013 sono configurati in questo modo:</span><span class="sxs-lookup"><span data-stu-id="0a258-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a258-120">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0a258-120">Property</span></span></th>
<th><span data-ttu-id="0a258-121">Server delle conferenze</span><span class="sxs-lookup"><span data-stu-id="0a258-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="0a258-122">Server applicazioni</span><span class="sxs-lookup"><span data-stu-id="0a258-122">Application Server</span></span></th>
<th><span data-ttu-id="0a258-123">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="0a258-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a258-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="0a258-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="0a258-125">49152</span><span class="sxs-lookup"><span data-stu-id="0a258-125">49152</span></span></p></td>
<td><p><span data-ttu-id="0a258-126">49152</span><span class="sxs-lookup"><span data-stu-id="0a258-126">49152</span></span></p></td>
<td><p><span data-ttu-id="0a258-127">49152</span><span class="sxs-lookup"><span data-stu-id="0a258-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a258-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="0a258-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="0a258-129">8348</span><span class="sxs-lookup"><span data-stu-id="0a258-129">8348</span></span></p></td>
<td><p><span data-ttu-id="0a258-130">8348</span><span class="sxs-lookup"><span data-stu-id="0a258-130">8348</span></span></p></td>
<td><p><span data-ttu-id="0a258-131">8348</span><span class="sxs-lookup"><span data-stu-id="0a258-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a258-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="0a258-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="0a258-133">57501</span><span class="sxs-lookup"><span data-stu-id="0a258-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a258-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="0a258-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="0a258-135">8034</span><span class="sxs-lookup"><span data-stu-id="0a258-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a258-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="0a258-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="0a258-137">49152</span><span class="sxs-lookup"><span data-stu-id="0a258-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a258-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="0a258-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="0a258-139">16383</span><span class="sxs-lookup"><span data-stu-id="0a258-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0a258-140">Come indicato in precedenza, quando si configurano le porte di Lync Server per QoS, è necessario assicurarsi che: 1) le impostazioni della porta audio siano identiche tra i servizi di conferenza, applicazione e mediazione. e 2) gli intervalli di porte non si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="0a258-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="0a258-141">Se si guarda attentamente la tabella precedente, si vedrà che gli intervalli di porta sono identici tra i tre tipi di server.</span><span class="sxs-lookup"><span data-stu-id="0a258-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="0a258-142">Ad esempio, la porta audio iniziale è impostata su porta 49152 su ogni tipo di server e il numero totale di porte riservate per l'audio in ogni server è identico: 8348.</span><span class="sxs-lookup"><span data-stu-id="0a258-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="0a258-143">Tuttavia, gli intervalli di porte si sovrappongono: le porte audio iniziano dalla porta 49152, ma anche le porte sono riservate per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0a258-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="0a258-144">Per usare in modo ottimale la qualità del servizio, la condivisione delle applicazioni deve essere riconfigurata in modo da usare un intervallo di porte univoco.</span><span class="sxs-lookup"><span data-stu-id="0a258-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="0a258-145">Ad esempio, puoi configurare la condivisione delle applicazioni per iniziare dalla porta 40803 e usare le porte di 8348.</span><span class="sxs-lookup"><span data-stu-id="0a258-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="0a258-146">(Perché le porte di 8348?</span><span class="sxs-lookup"><span data-stu-id="0a258-146">(Why 8348 ports?</span></span> <span data-ttu-id="0a258-147">Se Aggiungi questi valori insieme, 40803 + 8348, significa che la condivisione delle applicazioni userà le porte 40803 tramite la porta 49150.</span><span class="sxs-lookup"><span data-stu-id="0a258-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="0a258-148">Poiché le porte audio non iniziano fino alla porta 49152, non si avranno più intervalli di porte sovrapposti.</span><span class="sxs-lookup"><span data-stu-id="0a258-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="0a258-149">Dopo aver selezionato il nuovo intervallo di porte per la condivisione delle applicazioni, è possibile apportare le modifiche usando il cmdlet Set-CsConferencingServer.</span><span class="sxs-lookup"><span data-stu-id="0a258-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="0a258-150">Questa modifica non deve essere eseguita nei server delle applicazioni o nei server di mediazione, perché questi server non gestiscono il traffico di condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0a258-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="0a258-151">È necessario modificare i valori di porta solo in questi server se si decide di riassegnare le porte usate per il traffico audio.</span><span class="sxs-lookup"><span data-stu-id="0a258-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="0a258-152">Per modificare i valori di porta per la condivisione delle applicazioni in un singolo server di conferenza, eseguire un comando simile a questo da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="0a258-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="0a258-153">Se si vogliono apportare queste modifiche in tutti i server dei servizi di conferenza, è possibile eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="0a258-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="0a258-154">Dopo aver modificato le impostazioni della porta, è necessario interrompere e quindi riavviare ogni servizio interessato dalle modifiche.</span><span class="sxs-lookup"><span data-stu-id="0a258-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="0a258-155">Non è obbligatorio che i server di conferenza, i server delle applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte; l'unico requisito vero è l'impostazione degli intervalli di porte univoci in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="0a258-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="0a258-156">Tuttavia, l'amministrazione sarà in genere più semplice se usi lo stesso set di porte in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="0a258-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

