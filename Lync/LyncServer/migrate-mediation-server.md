---
title: Eseguire la migrazione di Mediation Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="d4ac7-102">Eseguire la migrazione di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d4ac7-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4ac7-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d4ac7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d4ac7-104">Il Mediation Server viene unito alla topologia pilota di Lync Server 2013 quando si esegue la creazione guidata unione.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="d4ac7-105">La configurazione di Lync Server 2013 Mediation Server viene tuttavia eseguita dopo la migrazione di tutti gli utenti perché un pool di Office Communications Server 2007 R2 non può comunicare con un server di mediazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d4ac7-106">Durante la migrazione affiancata, il pool di Lync Server 2013 comunica con Office Communications Server 2007 R2 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="d4ac7-107">Quando si configura Lync Server 2013 Mediation Server, è anche necessario aggiornare o sostituire i gateway di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="d4ac7-108">I gateway di Office Communications Server 2007 R2 non supportano Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d4ac7-109">È necessario distribuire gateway certificati per Lync Server 2013 e associarli a Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d4ac7-110">Questo passaggio è necessario prima di poter decommissionare completamente la distribuzione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="d4ac7-111">Gli argomenti di questa sezione descrivono le attività di configurazione che è necessario eseguire dopo aver completato la migrazione di Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d4ac7-112">La transizione del server di mediazione collocato a un Mediation Server autonomo è un'attività facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="d4ac7-113">Configurare Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d4ac7-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="d4ac7-114">Modificare le route vocali per usare il nuovo server di mediazione Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4ac7-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="d4ac7-115">Transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d4ac7-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

