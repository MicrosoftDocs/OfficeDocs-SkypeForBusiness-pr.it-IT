---
title: 'Lync Server 2013: avviare o arrestare i servizi di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ab531875145315b6a505bd0b324e9fdb4d77d5d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532983"
---
# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="34249-102">Avviare o arrestare i servizi di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34249-102">Start or stop Lync Server 2013 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34249-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="34249-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="34249-104">È possibile utilizzare il pannello di controllo di Lync Server per avviare o arrestare tutti i servizi di Lync Server 2013 in esecuzione in un computer specifico oppure per avviare o arrestare un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="34249-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="34249-105">Per avviare o arrestare tutti i servizi di Lync Server in un computer</span><span class="sxs-lookup"><span data-stu-id="34249-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="34249-106">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34249-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="34249-107">È possibile determinare se è stato assegnato il ruolo RBAC di CsServerAdministrator o CsAdministrator eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="34249-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="34249-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34249-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34249-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="34249-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34249-110">Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="34249-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="34249-111">Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui sono in esecuzione i servizi che si desidera avviare o arrestare e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="34249-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="34249-112">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="34249-112">Click **Action**.</span></span>

6.  <span data-ttu-id="34249-113">Fare clic su **Avvia tutti i servizi** o **Arresta tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="34249-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="34249-114">Per avviare o arrestare un servizio specifico</span><span class="sxs-lookup"><span data-stu-id="34249-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="34249-115">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="34249-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34249-116">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34249-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34249-117">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="34249-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34249-118">Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="34249-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="34249-119">Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="34249-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="34249-120">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="34249-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="34249-121">Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio da avviare o arrestare.</span><span class="sxs-lookup"><span data-stu-id="34249-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="34249-122">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="34249-122">Click **Action**.</span></span>

8.  <span data-ttu-id="34249-123">Fare clic su **Avvia servizio** o **Arresta servizio**.</span><span class="sxs-lookup"><span data-stu-id="34249-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="34249-124">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="34249-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34249-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34249-125">See Also</span></span>


[<span data-ttu-id="34249-126">Impedisci sessioni per i servizi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34249-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="34249-127">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34249-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

