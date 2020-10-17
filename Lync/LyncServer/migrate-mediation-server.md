---
title: Eseguire la migrazione di Mediation Server
description: Eseguire la migrazione di Mediation Server.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570332"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="7e9ba-103">Eseguire la migrazione di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7e9ba-103">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e9ba-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7e9ba-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7e9ba-105">Il Mediation Server viene unito alla topologia pilota di Lync Server 2013 quando si esegue la procedura guidata di Unione.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-105">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="7e9ba-106">È tuttavia possibile configurare Lync Server 2013 Mediation Server, dopo la migrazione di tutti gli utenti, perché un pool di Office Communications Server 2007 R2 non è in grado di comunicare con un server di mediazione Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-106">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7e9ba-107">Durante la migrazione affiancata, il pool di Lync Server 2013 comunica con il Mediation Server di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-107">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="7e9ba-108">Quando si configura Lync Server 2013 Mediation Server, è inoltre necessario aggiornare o sostituire i gateway di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-108">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="7e9ba-109">I gateway di Office Communications Server 2007 R2 non supportano Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-109">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7e9ba-110">È necessario distribuire i gateway certificati per Lync Server 2013 e associarli a Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-110">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7e9ba-111">Questo passaggio è necessario prima di poter rimuovere completamente la distribuzione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-111">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="7e9ba-112">Negli argomenti di questa sezione vengono descritte le attività di configurazione che è necessario eseguire dopo aver completato la migrazione di Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-112">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7e9ba-113">L'esecuzione della transizione dal Mediation Server collocato a un Mediation Server autonomo è un'attività facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7e9ba-113">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="7e9ba-114">Configurare Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7e9ba-114">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="7e9ba-115">Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7e9ba-115">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="7e9ba-116">Eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e9ba-116">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

