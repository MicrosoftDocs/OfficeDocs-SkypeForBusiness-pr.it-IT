---
title: 'Lync Server 2013: (facoltativo) verificare la distribuzione di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b28fa4a83e89e446c5f4739d95fedea88769bc3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530743"
---
# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="e8ffc-102">Optional Verificare la distribuzione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ffc-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8ffc-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e8ffc-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e8ffc-104">Dopo aver configurato Response Group, è necessario verificare la configurazione per assicurarsi che i Response Group funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="e8ffc-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="e8ffc-105">Verificare gli scenari seguenti utilizzando i tipi di utente riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="e8ffc-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="e8ffc-106">**Utenti**</span><span class="sxs-lookup"><span data-stu-id="e8ffc-106">**Users**</span></span>

  - <span data-ttu-id="e8ffc-107">Un utente ospitato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ffc-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="e8ffc-108">Utente esterno che usa la rete PSTN (switched telephone network) pubblica</span><span class="sxs-lookup"><span data-stu-id="e8ffc-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="e8ffc-109">Un agente ospitato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ffc-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="e8ffc-110">**Scenari**</span><span class="sxs-lookup"><span data-stu-id="e8ffc-110">**Scenarios**</span></span>

  - <span data-ttu-id="e8ffc-111">L'utente di Lync Server 2013 chiama il Response Group.</span><span class="sxs-lookup"><span data-stu-id="e8ffc-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="e8ffc-112">L'utente esterno chiama il gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="e8ffc-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="e8ffc-113">Un utente chiama il gruppo di risposta mentre l'agente è impegnato in un'altra chiamata e finisce in coda.</span><span class="sxs-lookup"><span data-stu-id="e8ffc-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

