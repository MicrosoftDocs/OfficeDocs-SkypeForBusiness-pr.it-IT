---
title: 'Lync Server 2013: (facoltativo) verificare la distribuzione di Response Group'
description: 'Lync Server 2013: (facoltativo) verificare la distribuzione di Response Group.'
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
ms.openlocfilehash: 0cfe15026bc1fcfbe10b593987d2717fc0dc8104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565712"
---
# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="0a21a-103">Optional Verificare la distribuzione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a21a-103">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a21a-104">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="0a21a-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="0a21a-105">Dopo aver configurato Response Group, è necessario verificare la configurazione per assicurarsi che i Response Group funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="0a21a-105">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="0a21a-106">Verificare gli scenari seguenti utilizzando i tipi di utente riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="0a21a-106">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="0a21a-107">**Utenti**</span><span class="sxs-lookup"><span data-stu-id="0a21a-107">**Users**</span></span>

  - <span data-ttu-id="0a21a-108">Un utente ospitato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a21a-108">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="0a21a-109">Utente esterno che usa la rete PSTN (switched telephone network) pubblica</span><span class="sxs-lookup"><span data-stu-id="0a21a-109">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="0a21a-110">Un agente ospitato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a21a-110">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="0a21a-111">**Scenari**</span><span class="sxs-lookup"><span data-stu-id="0a21a-111">**Scenarios**</span></span>

  - <span data-ttu-id="0a21a-112">L'utente di Lync Server 2013 chiama il Response Group.</span><span class="sxs-lookup"><span data-stu-id="0a21a-112">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="0a21a-113">L'utente esterno chiama il gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="0a21a-113">The external user calls the response group.</span></span>

  - <span data-ttu-id="0a21a-114">Un utente chiama il gruppo di risposta mentre l'agente è impegnato in un'altra chiamata e finisce in coda.</span><span class="sxs-lookup"><span data-stu-id="0a21a-114">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

