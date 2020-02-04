---
title: Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server
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
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6c710-102">Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c710-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c710-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6c710-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6c710-104">Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa).</span><span class="sxs-lookup"><span data-stu-id="6c710-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="6c710-105">Il servizio A/V Edge viene gestito principalmente con le impostazioni di configurazione di Edge A/V, che possono essere configurate nell'ambito del sito o nell'ambito del servizio, ovvero possono essere configurate per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="6c710-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="6c710-106">Quando si installa Lync Server, viene creata una raccolta globale di impostazioni di configurazione di Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="6c710-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="6c710-107">Questa raccolta globale non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="6c710-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="6c710-108">Puoi tuttavia usare Windows PowerShell e il cmdlet Remove-CsAVEdgeConfiguration per "reimpostare" la raccolta globale; Questo significa semplicemente che tutti i valori di proprietà nella raccolta globale verranno reimpostati sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6c710-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="6c710-109">Se ad esempio è stata impostata la proprietà MaxTokenLifetime per 16 ore, tale proprietà verrà reimpostata sul valore predefinito di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="6c710-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="6c710-110">Tuttavia, le raccolte di impostazioni personalizzate create nell'ambito del sito o nell'ambito del servizio possono essere eliminate usando il cmdlet Remove-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6c710-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="6c710-111">Se si eliminano le impostazioni dei siti, i server a/V Edge in tale sito verranno gestiti dalle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="6c710-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="6c710-112">Se si eliminano le impostazioni per l'ambito del servizio, tale server verrà gestito dalle impostazioni del sito, se esistenti o dalle impostazioni globali, se non sono disponibili impostazioni del sito.</span><span class="sxs-lookup"><span data-stu-id="6c710-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="6c710-113">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="6c710-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="6c710-114">Per reimpostare la raccolta globale</span><span class="sxs-lookup"><span data-stu-id="6c710-114">To reset the global collection</span></span>

  - <span data-ttu-id="6c710-115">Il comando seguente reimposta la raccolta globale delle impostazioni di configurazione di un/V Edge:</span><span class="sxs-lookup"><span data-stu-id="6c710-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="6c710-116">Per rimuovere una raccolta dall'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="6c710-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="6c710-117">Questo comando rimuove le impostazioni di configurazione del bordo A/V applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="6c710-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="6c710-118">Per rimuovere una raccolta dall'ambito del servizio</span><span class="sxs-lookup"><span data-stu-id="6c710-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="6c710-119">Questo comando rimuove le impostazioni applicate all'atl-edge-001.litwareinc.com A/V Edge Server:</span><span class="sxs-lookup"><span data-stu-id="6c710-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c710-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c710-120">See Also</span></span>


[<span data-ttu-id="6c710-121">Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c710-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="6c710-122">Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c710-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="6c710-123">Audio/video (A/V) Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c710-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="6c710-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c710-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

