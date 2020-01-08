---
title: 'Lync Server 2013: impedire sessioni per i servizi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8d22b74168c784d6a5e19c3ffc32b9e275040b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="91373-102">Impedire sessioni per i servizi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91373-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91373-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="91373-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="91373-104">È possibile usare il pannello di controllo di Lync Server per evitare nuove sessioni per tutti i servizi di Lync Server 2013 in uso in un computer specifico o per evitare nuove sessioni per un servizio specifico di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91373-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="91373-105">Per evitare nuove sessioni per tutti i servizi Lync Server in un computer</span><span class="sxs-lookup"><span data-stu-id="91373-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="91373-106">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91373-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="91373-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91373-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="91373-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="91373-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="91373-109">Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="91373-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="91373-110">Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi per cui si vogliono impedire le nuove sessioni e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="91373-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="91373-111">Fare clic su **azione**.</span><span class="sxs-lookup"><span data-stu-id="91373-111">Click **Action**.</span></span>

6.  <span data-ttu-id="91373-112">Fare clic su **Impedisci nuove sessioni per tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="91373-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="91373-113">Per impedire nuove sessioni per un servizio specifico</span><span class="sxs-lookup"><span data-stu-id="91373-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="91373-114">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91373-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="91373-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91373-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="91373-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="91373-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="91373-117">Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="91373-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="91373-118">Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="91373-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="91373-119">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="91373-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="91373-120">Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio per cui si vogliono impedire le nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="91373-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="91373-121">Fare clic su **azione**.</span><span class="sxs-lookup"><span data-stu-id="91373-121">Click **Action**.</span></span>

8.  <span data-ttu-id="91373-122">Fare clic su **Impedisci nuove sessioni per il servizio**.</span><span class="sxs-lookup"><span data-stu-id="91373-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="91373-123">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="91373-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91373-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91373-124">See Also</span></span>


[<span data-ttu-id="91373-125">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91373-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

