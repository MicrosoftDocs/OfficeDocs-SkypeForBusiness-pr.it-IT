---
title: 'Lync Server 2013: utilizzo dei cmdlet per annullare la preparazione della foresta'
description: 'Lync Server 2013: utilizzo dei cmdlet per annullare la preparazione della foresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580392"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="55e0d-103">Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55e0d-103">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55e0d-104">_**Ultimo argomento modificato:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="55e0d-104">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="55e0d-105">Utilizzare il cmdlet **Disable-CsAdForest** per annullare il passaggio di preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="55e0d-105">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="55e0d-106">Se si esegue il cmdlet <STRONG>Disable-CsAdForest</STRONG> in un ambiente in cui è stata distribuita anche una versione precedente di Lync Server, verranno eliminate anche le impostazioni globali per la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="55e0d-106">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="55e0d-107">Per utilizzare cmdlet per annullare la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="55e0d-107">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="55e0d-108">Accedere a un computer che fa parte di un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="55e0d-108">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="55e0d-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="55e0d-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="55e0d-110">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="55e0d-110">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="55e0d-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="55e0d-111">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="55e0d-112">Il parametro Force specifica se forzare l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="55e0d-112">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="55e0d-113">Se questo parametro non è presente, il comando non verrà eseguito se anche un dominio della foresta è ancora pronto per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55e0d-113">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="55e0d-114">Se viene specificato il parametro Force, l'azione continuerà indipendentemente dallo stato degli altri domini nella foresta.</span><span class="sxs-lookup"><span data-stu-id="55e0d-114">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="55e0d-115">Se non si specifica il parametro GroupDomain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="55e0d-115">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55e0d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55e0d-116">See Also</span></span>


[<span data-ttu-id="55e0d-117">Esecuzione della preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55e0d-117">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="55e0d-118">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55e0d-118">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

