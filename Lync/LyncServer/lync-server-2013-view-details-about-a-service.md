---
title: 'Lync Server 2013: visualizzare i dettagli relativi a un servizio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8268720754f0f34fa24a5a5c7beef9ac21b5d3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="6176d-102">Visualizzare i dettagli relativi a un servizio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6176d-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6176d-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6176d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6176d-104">È possibile utilizzare il pannello di controllo di Lync Server per visualizzare i dettagli relativi a ogni servizio in esecuzione in un computer specifico della topologia.</span><span class="sxs-lookup"><span data-stu-id="6176d-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="6176d-105">È possibile visualizzare lo stato di ogni servizio e i dettagli, ad esempio i database associati, le porte e i servizi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="6176d-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="6176d-106">Per visualizzare i dettagli di un servizio</span><span class="sxs-lookup"><span data-stu-id="6176d-106">To view details for a service</span></span>

1.  <span data-ttu-id="6176d-107">Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Lync Server 2013, accedere a un computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6176d-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="6176d-108">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere [pianificazione del controllo di accesso basato sui ruoli in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="6176d-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="6176d-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6176d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6176d-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6176d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6176d-111">Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="6176d-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="6176d-112">Nella pagina **stato** ordinare o cercare nell'elenco e quindi fare clic sul computer che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="6176d-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="6176d-113">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6176d-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="6176d-114">Nella finestra **Visualizza dettagli computer** , ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="6176d-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="6176d-115">Eseguire una delle operazioni seguenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="6176d-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="6176d-116">Per visualizzare lo stato più recente di quel servizio specifico, fare clic su **Ottieni stato del servizio**.</span><span class="sxs-lookup"><span data-stu-id="6176d-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="6176d-117">Per visualizzare i dettagli relativi a quel servizio specifico, fare clic su **Proprietà** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6176d-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="6176d-118">Per tornare all'elenco di tutti i computer della topologia, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6176d-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6176d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6176d-119">See Also</span></span>


[<span data-ttu-id="6176d-120">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6176d-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

