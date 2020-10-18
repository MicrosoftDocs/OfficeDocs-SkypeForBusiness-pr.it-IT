---
title: Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server
description: Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cdf7dca19446f4eac584564eed776f7fde47bfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578342"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="38f57-103">Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38f57-103">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38f57-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38f57-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38f57-p101">Il servizio A/V Edge consente agli utenti interni, ovvero gli utenti connessi alla rete dell'organizzazione, di condividere audio e video con gli utenti esterni, ovvero gli utenti non connessi alla rete dell'organizzazione. Il servizio A/V Edge viene gestito principalmente tramite le impostazioni di configurazione di A/V Edge, configurabili nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="38f57-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="38f57-107">Quando si installa Lync Server, viene creata una raccolta globale delle impostazioni di configurazione di A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="38f57-107">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="38f57-108">Oltre a ciò, è possibile utilizzare Windows PowerShell e il cmdlet New-CsAVEdgeConfiguration per creare nuove impostazioni nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="38f57-108">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="38f57-109">Quando si creano nuove impostazioni, tenere presente quanto segue.</span><span class="sxs-lookup"><span data-stu-id="38f57-109">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="38f57-110">Le impostazioni configurate nell'ambito del servizio, ovvero in un singolo server, avranno la precedenza su tutte le altre.</span><span class="sxs-lookup"><span data-stu-id="38f57-110">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="38f57-p103">Le impostazioni configurate nell'ambito del sito hanno la priorità su quelle configurate nell'ambito globale. Le impostazioni nell'ambito del servizio avranno tuttavia la precedenza sulle impostazioni nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="38f57-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="38f57-113">Le impostazioni dell'ambito globale vengono utilizzate solo se non sono state configurate impostazioni del servizio nel singolo server e se non sono presenti impostazioni del sito per il sito in cui si trova il server in oggetto.</span><span class="sxs-lookup"><span data-stu-id="38f57-113">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="38f57-114">Tutte le impostazioni possono essere quindi modificate utilizzando il cmdlet Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="38f57-114">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="38f57-115">Per ulteriori informazioni, vedere gli argomenti della Guida per i cmdlet [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) e [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="38f57-115">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="38f57-116">Per creare nuove impostazioni di configurazione a/V Edge nell'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="38f57-116">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="38f57-117">Il comando seguente crea una nuova raccolta di impostazioni di configurazione di A/V Edge per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="38f57-117">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="38f57-118">Per creare impostazioni di configurazione a/V Edge personalizzate nell'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="38f57-118">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="38f57-p105">Poiché non sono stati inclusi parametri aggiuntivi, queste nuove impostazioni utilizzeranno i valori predefiniti per il servizio A/V Edge. In alternativa, è possibile inserire altri parametri e valori di parametro per creare una raccolta personalizzata. Questo comando imposta ad esempio la proprietà MaxTokenLifetime su 4 ore (04 ore : 00 minuti : 00 secondi):</span><span class="sxs-lookup"><span data-stu-id="38f57-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="38f57-122">Per creare impostazioni di configurazione a/V Edge personalizzate nell'ambito del servizio</span><span class="sxs-lookup"><span data-stu-id="38f57-122">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="38f57-123">Questo comando crea una raccolta simile applicata al server A/V Edge atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="38f57-123">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="38f57-124">Per modificare le impostazioni di configurazione di A/V Edge esistenti</span><span class="sxs-lookup"><span data-stu-id="38f57-124">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="38f57-125">In questo esempio il cmdlet Set-CsAVEdgeConfiguration viene utilizzato per modificare in 12 ore la durata massima dei token per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="38f57-125">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38f57-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38f57-126">See Also</span></span>


[<span data-ttu-id="38f57-127">Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38f57-127">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="38f57-128">Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38f57-128">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="38f57-129">Audio/video (A/V) server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38f57-129">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="38f57-130">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38f57-130">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="38f57-131">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38f57-131">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

