---
title: Impedisci sessioni per i servizi
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed0ba62a3635d58d685668adc9cf3687609e4f49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="f5c0a-102">Impedisci sessioni per i servizi</span><span class="sxs-lookup"><span data-stu-id="f5c0a-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c0a-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f5c0a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f5c0a-104">È possibile utilizzare il pannello di controllo di Microsoft Lync Server 2010 per impedire nuove sessioni per tutti i servizi di Lync Server 2010 in esecuzione in un computer specifico o per impedire nuove sessioni per un servizio specifico di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="f5c0a-105">Per impedire nuove sessioni di tutti i servizi di Lync Server in un computer</span><span class="sxs-lookup"><span data-stu-id="f5c0a-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="f5c0a-106">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f5c0a-107">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f5c0a-108">Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="f5c0a-109">Nella pagina **Stato** ordinare l'elenco oppure cercare nell'elenco il computer in cui sono in esecuzione i servizi per cui si desidera impedire nuove sessioni, quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="f5c0a-110">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-110">Click **Action**.</span></span>

6.  <span data-ttu-id="f5c0a-111">Fare clic su **Impedisci nuove sessioni per tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="f5c0a-112">Per impedire nuove sessioni per uno specifico servizio</span><span class="sxs-lookup"><span data-stu-id="f5c0a-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="f5c0a-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f5c0a-114">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f5c0a-115">Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="f5c0a-116">Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="f5c0a-117">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="f5c0a-118">Ordinare l'elenco dei servizi, se necessario, quindi fare clic sul servizio per cui si desidera impedire nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="f5c0a-119">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-119">Click **Action**.</span></span>

8.  <span data-ttu-id="f5c0a-120">Fare clic su **Impedisci nuove sessioni per il servizio**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="f5c0a-121">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f5c0a-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

