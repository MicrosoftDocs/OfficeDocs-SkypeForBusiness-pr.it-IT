---
title: 'Lync Server 2013: visualizzare i dettagli di un servizio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fd84ad7290f3b82130f04d8b81955f6ffb4921
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="0d6cf-102">Visualizzare i dettagli di un servizio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d6cf-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d6cf-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0d6cf-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0d6cf-104">È possibile usare il pannello di controllo di Lync Server per visualizzare i dettagli su ogni servizio in uso in un computer specifico della topologia.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="0d6cf-105">È possibile visualizzare lo stato di ogni servizio e i dettagli, ad esempio i database associati, le porte e i servizi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="0d6cf-106">Per visualizzare i dettagli di un servizio</span><span class="sxs-lookup"><span data-stu-id="0d6cf-106">To view details for a service</span></span>

1.  <span data-ttu-id="0d6cf-107">Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Lync Server 2013, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="0d6cf-108">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere [pianificazione per il controllo dell'accesso basato sui ruoli in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="0d6cf-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="0d6cf-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0d6cf-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0d6cf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0d6cf-111">Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="0d6cf-112">Nella pagina **stato** ordinare o eseguire una ricerca nell'elenco e quindi fare clic sul computer che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="0d6cf-113">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="0d6cf-114">Nella finestra **Visualizza dettaglio computer** ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="0d6cf-115">Eseguire una delle operazioni seguenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="0d6cf-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="0d6cf-116">Per visualizzare lo stato più recente di tale servizio specifico, fare clic su **Ottieni stato servizio**.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="0d6cf-117">Per visualizzare i dettagli del servizio specifico, fare clic su **Proprietà** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="0d6cf-118">Per tornare all'elenco di tutti i computer della topologia, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0d6cf-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d6cf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d6cf-119">See Also</span></span>


[<span data-ttu-id="0d6cf-120">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d6cf-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

