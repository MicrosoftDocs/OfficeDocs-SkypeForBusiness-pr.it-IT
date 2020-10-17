---
title: 'Lync Server 2013: eliminare una coda di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c768edeff7facc1030b414d0e0e54e3516abe52
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525623"
---
# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="f20c9-102">Eliminare una coda di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f20c9-102">Delete a Response Group queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f20c9-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f20c9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f20c9-104">Utilizzare una delle procedure seguenti per eliminare una coda.</span><span class="sxs-lookup"><span data-stu-id="f20c9-104">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="f20c9-105">Per utilizzare il pannello di controllo di Lync Server per eliminare una coda</span><span class="sxs-lookup"><span data-stu-id="f20c9-105">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="f20c9-106">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="f20c9-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f20c9-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f20c9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f20c9-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f20c9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f20c9-109">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Coda**.</span><span class="sxs-lookup"><span data-stu-id="f20c9-109">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="f20c9-110">Nel campo di ricerca digitare tutto o parte del nome della coda che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="f20c9-110">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="f20c9-111">Nell'elenco delle code fare clic sulla coda desiderata, fare clic su \*\*Modifica \*\* e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f20c9-111">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="f20c9-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f20c9-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="f20c9-113">Per utilizzare Windows PowerShell per eliminare una coda</span><span class="sxs-lookup"><span data-stu-id="f20c9-113">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="f20c9-114">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="f20c9-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f20c9-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f20c9-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f20c9-116">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f20c9-116">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="f20c9-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f20c9-117">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

