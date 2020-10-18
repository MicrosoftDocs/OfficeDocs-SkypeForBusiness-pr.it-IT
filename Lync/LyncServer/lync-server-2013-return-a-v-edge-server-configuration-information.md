---
title: 'Lync Server 2013: restituire le informazioni di configurazione di A/V Edge Server'
description: 'Lync Server 2013: restituire le informazioni di configurazione di A/V Edge Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575442"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="2a10d-103">Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a10d-103">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a10d-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a10d-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2a10d-p101">Il servizio A/V Edge consente agli utenti interni, ovvero gli utenti connessi alla rete dell'organizzazione, di condividere audio e video con gli utenti esterni, ovvero gli utenti non connessi alla rete dell'organizzazione. Il servizio A/V Edge viene gestito principalmente tramite le impostazioni di configurazione di A/V Edge, configurabili nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="2a10d-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="2a10d-107">Per ottenere informazioni sulle impostazioni di configurazione a/V Edge in uso nell'organizzazione, è necessario utilizzare Windows PowerShell e il cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2a10d-107">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="2a10d-108">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="2a10d-108">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="2a10d-109">Le informazioni restituite dal cmdlet Get-CsAVEdgeConfiguration saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a10d-109">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="2a10d-110">Per restituire informazioni su tutte le impostazioni di configurazione A/V Edge</span><span class="sxs-lookup"><span data-stu-id="2a10d-110">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="2a10d-111">Il comando seguente restituisce informazioni su tutte le impostazioni di configurazione A/V Edge attualmente in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2a10d-111">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="2a10d-112">Per restituire le informazioni relative alle impostazioni di configurazione A/V Edge con ambito sito</span><span class="sxs-lookup"><span data-stu-id="2a10d-112">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="2a10d-p103">Per restituire informazioni su una raccolta specifica di impostazioni di configurazione A/V Edge, specificare l'identità (Identity) di tale raccolta quando si esegue il cmdlet Get-CsAVEdgeConfiguration. Questo comando ad esempio restituisce informazioni solo sulle impostazioni applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="2a10d-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="2a10d-115">Per restituire le informazioni relative alle impostazioni di configurazione A/V Edge con ambito servizio</span><span class="sxs-lookup"><span data-stu-id="2a10d-115">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="2a10d-116">Questo comando restituisce informazioni solo sulle impostazioni applicate a un A/V Edge Server specifico:</span><span class="sxs-lookup"><span data-stu-id="2a10d-116">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a10d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a10d-117">See Also</span></span>


[<span data-ttu-id="2a10d-118">Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a10d-118">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="2a10d-119">Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a10d-119">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="2a10d-120">Audio/video (A/V) server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a10d-120">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

