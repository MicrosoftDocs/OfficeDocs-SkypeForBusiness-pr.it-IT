---
title: 'Lync Server 2013: configurazione degli intervalli di porte per i server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce17300c6504989d132cb27301128bfbc568870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="82d72-102">Configurazione degli intervalli di porte per i server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82d72-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82d72-103">_**Ultimo argomento modificato:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="82d72-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="82d72-104">Con i server perimetrali non è necessario configurare intervalli di porte separati per la condivisione di audio, video e applicazioni. Analogamente, gli intervalli di porte utilizzati per i server perimetrali non devono corrispondere agli intervalli di porte utilizzati con le conferenze, l'applicazione e i Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="82d72-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="82d72-105">Prima di procedere con l'esempio, è importante sottolineare che, sebbene esista questa opzione, si consiglia di non modificare gli intervalli di porte, in quanto ciò potrebbe influire negativamente su alcuni scenari se si esce dall'intervallo di porte 50000.</span><span class="sxs-lookup"><span data-stu-id="82d72-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="82d72-106">Si supponga, ad esempio, che siano stati configurati i servizi di conferenza, applicazione e Mediation Server per l'utilizzo di questi intervalli di porte:</span><span class="sxs-lookup"><span data-stu-id="82d72-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82d72-107">Tipo di pacchetto</span><span class="sxs-lookup"><span data-stu-id="82d72-107">Packet Type</span></span></th>
<th><span data-ttu-id="82d72-108">Numero di porta iniziale</span><span class="sxs-lookup"><span data-stu-id="82d72-108">Starting Port</span></span></th>
<th><span data-ttu-id="82d72-109">Numero di porte riservate</span><span class="sxs-lookup"><span data-stu-id="82d72-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82d72-110">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="82d72-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="82d72-111">40803</span><span class="sxs-lookup"><span data-stu-id="82d72-111">40803</span></span></p></td>
<td><p><span data-ttu-id="82d72-112">8348</span><span class="sxs-lookup"><span data-stu-id="82d72-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82d72-113">Audio</span><span class="sxs-lookup"><span data-stu-id="82d72-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="82d72-114">49152</span><span class="sxs-lookup"><span data-stu-id="82d72-114">49152</span></span></p></td>
<td><p><span data-ttu-id="82d72-115">8348</span><span class="sxs-lookup"><span data-stu-id="82d72-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82d72-116">Video</span><span class="sxs-lookup"><span data-stu-id="82d72-116">Video</span></span></p></td>
<td><p><span data-ttu-id="82d72-117">57500</span><span class="sxs-lookup"><span data-stu-id="82d72-117">57500</span></span></p></td>
<td><p><span data-ttu-id="82d72-118">8034</span><span class="sxs-lookup"><span data-stu-id="82d72-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82d72-119"><strong>Totali</strong></span><span class="sxs-lookup"><span data-stu-id="82d72-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="82d72-120">24730</span><span class="sxs-lookup"><span data-stu-id="82d72-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82d72-121">Come si può notare, gli intervalli di porte per la condivisione di audio, video e applicazioni partono dalla porta 40803 e comprendono un totale di 24732 porte.</span><span class="sxs-lookup"><span data-stu-id="82d72-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="82d72-122">Se lo si desidera, è possibile configurare un server perimetrale specifico affinché utilizzi questi valori generali, eseguendo un comando simile al seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="82d72-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="82d72-123">Alternativamente, è possibile utilizzare il comando seguente per configurare simultaneamente tutti i server perimetrali all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="82d72-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="82d72-124">È possibile verificare le impostazioni correnti delle porte per i server perimetrali utilizzando il comando Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="82d72-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="82d72-125">Anche in questo caso, se si forniscono queste opzioni, si consiglia vivamente di lasciare le cose così come sono per la configurazione della porta.</span><span class="sxs-lookup"><span data-stu-id="82d72-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

