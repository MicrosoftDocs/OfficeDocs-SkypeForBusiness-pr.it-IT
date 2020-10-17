---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a7ddba431e1c921df9b3880ee9af73f71584b5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515923"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="c089d-102">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="c089d-102">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c089d-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c089d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="c089d-104">Verificare il pool nello strumento di amministrazione di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c089d-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="c089d-105">Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c089d-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="c089d-106">Espandere il nodo **Foresta**, il nodo **Server Standard** o **Pool Enterprise** e quindi il nome del pool o del server.</span><span class="sxs-lookup"><span data-stu-id="c089d-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="c089d-107">Verificare che i servizi Office Communications Server 2007 R2 siano in esecuzione nel pool.</span><span class="sxs-lookup"><span data-stu-id="c089d-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="c089d-108">![Console di amministrazione di Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console di amministrazione di Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="c089d-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="c089d-109">Verificare il pool pilota nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c089d-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="c089d-110">Da un account utente membro del ruolo CsAdministrator accedere al front end server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c089d-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="c089d-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c089d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c089d-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c089d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c089d-113">Fare clic su **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="c089d-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="c089d-114">Verificare che i server distribuiti siano presenti nel pool pilota.</span><span class="sxs-lookup"><span data-stu-id="c089d-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="c089d-115">![Pagina della topologia del pannello di controllo di Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Pagina della topologia del pannello di controllo di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="c089d-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="c089d-116">Verificare che i servizi di Lync Server 2013 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="c089d-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="c089d-117">Nel server front end di Lync Server 2013 aprire l'applet **Servizi** dal gruppo **strumenti di amministrazione** .</span><span class="sxs-lookup"><span data-stu-id="c089d-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="c089d-118">Verificare che i servizi elencati corrispondano all'elenco mostrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="c089d-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="c089d-119">![Pagina Servizi in cui è stato avviato Lync Services](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Pagina Servizi in cui è stato avviato Lync Services")</span><span class="sxs-lookup"><span data-stu-id="c089d-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

