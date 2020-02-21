---
title: 'Lync Server 2013: eliminare un gruppo di agenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71d4d2a2ca22ec0852fb09bdfe011c5d934ab3d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="6ae57-102">Eliminare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ae57-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae57-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6ae57-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6ae57-104">Utilizzare una delle procedure seguenti per eliminare un gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="6ae57-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="6ae57-105">Per utilizzare il pannello di controllo di Lync Server per eliminare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="6ae57-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="6ae57-106">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="6ae57-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6ae57-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ae57-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ae57-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6ae57-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ae57-109">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="6ae57-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="6ae57-110">Nella pagina **Response Group** digitare tutto o parte del nome del gruppo di agenti da eliminare nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6ae57-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="6ae57-111">Nell'elenco risultante fare clic sul gruppo da eliminare, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6ae57-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="6ae57-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ae57-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="6ae57-113">Per utilizzare Windows PowerShell per eliminare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="6ae57-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="6ae57-114">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="6ae57-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6ae57-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6ae57-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6ae57-116">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6ae57-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="6ae57-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6ae57-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ae57-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ae57-118">See Also</span></span>


[<span data-ttu-id="6ae57-119">Creare o modificare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ae57-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="6ae57-120">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="6ae57-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="6ae57-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="6ae57-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

