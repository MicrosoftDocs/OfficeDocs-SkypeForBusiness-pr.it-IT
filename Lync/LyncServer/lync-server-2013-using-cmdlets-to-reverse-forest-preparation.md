---
title: 'Lync Server 2013: Utilizzo dei cmdlet per annullare la preparazione della foresta'
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
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="a8b95-102">Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8b95-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8b95-103">_**Argomento Ultima modifica:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="a8b95-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="a8b95-104">Usa il cmdlet **Disable-CsAdForest** per invertire il passaggio di preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="a8b95-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a8b95-105">Se si esegue il cmdlet <STRONG>Disable-CsAdForest</STRONG> in un ambiente in cui è stata distribuita anche una versione precedente di Lync Server, verranno eliminate anche le impostazioni globali per la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="a8b95-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="a8b95-106">Per usare i cmdlet per invertire la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="a8b95-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="a8b95-107">Accedere a un computer collegato a un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="a8b95-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="a8b95-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a8b95-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a8b95-109">Eseguire</span><span class="sxs-lookup"><span data-stu-id="a8b95-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="a8b95-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a8b95-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="a8b95-111">Il parametro Force specifica se forzare l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a8b95-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="a8b95-112">Se questo parametro non è presente, il comando non verrà eseguito se anche un dominio nella foresta è ancora pronto per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8b95-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="a8b95-113">Se il parametro Force viene specificato, l'azione continuerà indipendentemente dallo stato di altri domini nella foresta.</span><span class="sxs-lookup"><span data-stu-id="a8b95-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="a8b95-114">Se non specifichi il parametro GroupDomain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="a8b95-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8b95-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8b95-115">See Also</span></span>


[<span data-ttu-id="a8b95-116">Esecuzione della preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8b95-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="a8b95-117">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8b95-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

