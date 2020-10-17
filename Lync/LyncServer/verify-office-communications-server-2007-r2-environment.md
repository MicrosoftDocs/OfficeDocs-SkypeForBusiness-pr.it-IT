---
title: Verificare l'ambiente Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4107877c237abef92233dbca88cf7060fdca25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515943"
---
# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="3284e-102">Verificare l'ambiente Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3284e-102">Verify Office Communications Server 2007 R2 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3284e-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="3284e-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="3284e-104">Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Office Communications Server 2007 R2, è necessario verificare che i servizi Office Communications Server 2007 R2 siano configurati e avviati.</span><span class="sxs-lookup"><span data-stu-id="3284e-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="3284e-105">**Verificare che il pool venga avviato utilizzando lo strumento di amministrazione di Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="3284e-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="3284e-106">Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3284e-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="3284e-107">Espandere il nodo **Foresta**, il nodo **Server Standard** o **Pool Enterprise** e quindi il nome del pool o del server.</span><span class="sxs-lookup"><span data-stu-id="3284e-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="3284e-108">Verificare che i servizi siano in esecuzione nel server Standard Edition o nel pool Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3284e-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="3284e-109">![Console di amministrazione di Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console di amministrazione di Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="3284e-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="3284e-110">**Controllare gli utenti configurati per Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="3284e-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="3284e-111">Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3284e-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="3284e-112">Espandere il nodo **Foresta**, il nodo **Server Standard** o **Pool Enterprise** e quindi il nome del pool o del server.</span><span class="sxs-lookup"><span data-stu-id="3284e-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="3284e-113">Fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="3284e-113">Click **Users**.</span></span>

4.  <span data-ttu-id="3284e-114">Verificare l'elenco degli utenti di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3284e-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="3284e-115">![Elencare gli utenti di fo nello strumento di amministrazione di OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Elencare gli utenti di fo nello strumento di amministrazione di OCS")</span><span class="sxs-lookup"><span data-stu-id="3284e-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="3284e-116">**Verificare la configurazione del partner federato XMPP legacy**</span><span class="sxs-lookup"><span data-stu-id="3284e-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="3284e-117">Dal server XMPP legacy, accedere all'applet servizi di amministrazione degli strumenti \\ .</span><span class="sxs-lookup"><span data-stu-id="3284e-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3284e-118">Verificare che il servizio Office Communications Server XMPP Gateway sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="3284e-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="3284e-119">![Servizio gateway XMPP di Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servizio gateway XMPP di Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="3284e-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

