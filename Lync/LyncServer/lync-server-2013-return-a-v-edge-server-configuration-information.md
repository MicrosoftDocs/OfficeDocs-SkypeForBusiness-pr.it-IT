---
title: 'Lync Server 2013: restituire le informazioni di configurazione A/V Edge Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15096099184525890328dbe1c89d891487b46d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="3daef-102">Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3daef-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3daef-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3daef-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3daef-104">Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa).</span><span class="sxs-lookup"><span data-stu-id="3daef-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="3daef-105">Il servizio A/V Edge viene gestito principalmente con le impostazioni di configurazione di Edge A/V, che possono essere configurate nell'ambito del sito o nell'ambito del servizio, ovvero possono essere configurate per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="3daef-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="3daef-106">Per restituire informazioni sulle impostazioni di configurazione a/V Edge in uso nell'organizzazione, è necessario usare Windows PowerShell e il cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3daef-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3daef-107">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3daef-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="3daef-108">Le informazioni restituite dal cmdlet Get-CsAVEdgeConfiguration avranno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3daef-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="3daef-109">Per restituire informazioni per tutte le impostazioni di configurazione di Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3daef-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="3daef-110">Il comando seguente restituisce informazioni su tutte le impostazioni di configurazione A/V Edge attualmente in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="3daef-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="3daef-111">Per restituire informazioni per le impostazioni di configurazione A/V Edge con ambito sito</span><span class="sxs-lookup"><span data-stu-id="3daef-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="3daef-112">Per restituire informazioni su una raccolta specifica di impostazioni di configurazione di un/V Edge, specificare l'identità della raccolta durante l'uso del cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3daef-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3daef-113">Ad esempio, questo comando restituisce le informazioni solo per le impostazioni applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="3daef-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="3daef-114">Per restituire informazioni per le impostazioni di configurazione A/V Edge con ambito servizio</span><span class="sxs-lookup"><span data-stu-id="3daef-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="3daef-115">Questo comando restituisce solo le informazioni per le impostazioni applicate a un/V Edge Server specifico:</span><span class="sxs-lookup"><span data-stu-id="3daef-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3daef-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3daef-116">See Also</span></span>


[<span data-ttu-id="3daef-117">Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3daef-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="3daef-118">Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3daef-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="3daef-119">Audio/video (A/V) Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3daef-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

