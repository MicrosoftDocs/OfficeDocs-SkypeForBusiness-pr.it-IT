---
title: Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901562812e7847a6c205f042922dca6383ad6254
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ed7c4-102">Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7c4-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed7c4-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ed7c4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ed7c4-p101">Il servizio A/V Edge consente agli utenti interni, ovvero gli utenti connessi alla rete dell'organizzazione, di condividere audio e video con gli utenti esterni, ovvero gli utenti non connessi alla rete dell'organizzazione. Il servizio A/V Edge viene gestito principalmente tramite le impostazioni di configurazione di A/V Edge, configurabili nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="ed7c4-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="ed7c4-106">Quando si installa Lync Server, viene creata una raccolta globale delle impostazioni di configurazione di A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="ed7c4-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="ed7c4-107">Questa raccolta globale non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="ed7c4-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="ed7c4-108">Tuttavia, è possibile utilizzare Windows PowerShell e il cmdlet Remove-CsAVEdgeConfiguration per "reimpostare" la raccolta globale. Ciò significa semplicemente che tutti i valori della proprietà nella raccolta globale verranno reimpostati sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ed7c4-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="ed7c4-109">Se la proprietà MaxTokenLifetime è impostata su 16 ore, ad esempio, con l'esecuzione del cmdlet verrebbe ripristinato il valore predefinito di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="ed7c4-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="ed7c4-p103">È comunque possibile utilizzare il cmdlet Remove-CsAVEdgeConfiguration per eliminare le raccolte di impostazioni personalizzate create con ambito sito o con ambito servizio. Se si eliminano le impostazioni a livello di sito, i server A/V Edge in tale sito verranno gestiti dalle impostazioni globali. Se si eliminano le impostazioni con ambito servizio, il server verrà gestito dalle impostazioni a livello sito, se esistenti, o dalle impostazioni globali se non sono disponibili impostazioni a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="ed7c4-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="ed7c4-113">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="ed7c4-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="ed7c4-114">Per reimpostare la raccolta globale</span><span class="sxs-lookup"><span data-stu-id="ed7c4-114">To reset the global collection</span></span>

  - <span data-ttu-id="ed7c4-115">Il comando seguente consente di reimpostare la raccolta globale delle impostazioni di configurazione di A/V Edge:</span><span class="sxs-lookup"><span data-stu-id="ed7c4-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="ed7c4-116">Per rimuovere una raccolta dall'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="ed7c4-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="ed7c4-117">Questo comando consente di rimuovere le impostazioni di configurazione di A/V Edge applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="ed7c4-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="ed7c4-118">Per rimuovere una raccolta dall'ambito del servizio</span><span class="sxs-lookup"><span data-stu-id="ed7c4-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="ed7c4-119">Questo comando consente di rimuovere le impostazioni applicate al server A/V Edge atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ed7c4-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed7c4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed7c4-120">See Also</span></span>


[<span data-ttu-id="ed7c4-121">Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7c4-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="ed7c4-122">Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7c4-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="ed7c4-123">Audio/video (A/V) server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7c4-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="ed7c4-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed7c4-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

