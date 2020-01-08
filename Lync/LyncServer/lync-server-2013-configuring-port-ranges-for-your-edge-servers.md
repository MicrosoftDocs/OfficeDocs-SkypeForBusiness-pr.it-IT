---
title: 'Lync Server 2013: configurazione degli intervalli di porte per gli Edge Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="1a613-102">Configurazione degli intervalli di porte per gli Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a613-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a613-103">_**Argomento Ultima modifica:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="1a613-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="1a613-104">Con Edge Server non è necessario configurare intervalli di porte distinti per l'audio, il video e la condivisione di applicazioni; allo stesso modo, gli intervalli di porte usati per i server perimetrali non devono corrispondere agli intervalli di porte usati con i server di conferenza, applicazione e mediazione.</span><span class="sxs-lookup"><span data-stu-id="1a613-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="1a613-105">Prima di procedere con il nostro esempio, è importante sottolineare che, mentre questa opzione esiste, ti consigliamo di non modificare gli intervalli di porte, perché questo potrebbe influire negativamente su alcuni scenari, se ci si sposta fuori dall'intervallo di porte di 50000.</span><span class="sxs-lookup"><span data-stu-id="1a613-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="1a613-106">Si supponga ad esempio di avere configurato i servizi di conferenza, applicazione e mediazione per l'uso di questi intervalli di porte:</span><span class="sxs-lookup"><span data-stu-id="1a613-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a613-107">Tipo di pacchetto</span><span class="sxs-lookup"><span data-stu-id="1a613-107">Packet Type</span></span></th>
<th><span data-ttu-id="1a613-108">Porta di avvio</span><span class="sxs-lookup"><span data-stu-id="1a613-108">Starting Port</span></span></th>
<th><span data-ttu-id="1a613-109">Numero di porte riservate</span><span class="sxs-lookup"><span data-stu-id="1a613-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a613-110">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="1a613-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="1a613-111">40803</span><span class="sxs-lookup"><span data-stu-id="1a613-111">40803</span></span></p></td>
<td><p><span data-ttu-id="1a613-112">8348</span><span class="sxs-lookup"><span data-stu-id="1a613-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a613-113">Audio</span><span class="sxs-lookup"><span data-stu-id="1a613-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="1a613-114">49152</span><span class="sxs-lookup"><span data-stu-id="1a613-114">49152</span></span></p></td>
<td><p><span data-ttu-id="1a613-115">8348</span><span class="sxs-lookup"><span data-stu-id="1a613-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a613-116">Video</span><span class="sxs-lookup"><span data-stu-id="1a613-116">Video</span></span></p></td>
<td><p><span data-ttu-id="1a613-117">57500</span><span class="sxs-lookup"><span data-stu-id="1a613-117">57500</span></span></p></td>
<td><p><span data-ttu-id="1a613-118">8034</span><span class="sxs-lookup"><span data-stu-id="1a613-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a613-119"><strong>Totali</strong></span><span class="sxs-lookup"><span data-stu-id="1a613-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="1a613-120">24730</span><span class="sxs-lookup"><span data-stu-id="1a613-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a613-121">Come si può vedere, gli intervalli di porte per la condivisione di audio, video e applicazioni iniziano alla porta 40803 e includono un totale di 24732 porte.</span><span class="sxs-lookup"><span data-stu-id="1a613-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="1a613-122">Se si preferisce, è possibile configurare un server perimetrale specifico per l'uso di questi valori di porta complessivi eseguendo un comando simile a quello di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1a613-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="1a613-123">In alternativa, usare il comando seguente per configurare contemporaneamente tutti i server perimetrali dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="1a613-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="1a613-124">Puoi verificare le impostazioni della porta corrente per gli Edge Server usando il comando Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1a613-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="1a613-125">Anche in questo caso, quando forniamo queste opzioni, ti consigliamo vivamente di abbandonare gli elementi per la configurazione della porta.</span><span class="sxs-lookup"><span data-stu-id="1a613-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

