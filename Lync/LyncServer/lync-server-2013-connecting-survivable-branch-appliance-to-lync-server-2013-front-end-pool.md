---
title: Connessione di Survivable Branch Appliance al pool Front End di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d23b501738010a8e5e5ed1c5c2e9a8608b0709e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="a7df2-102">Connessione di Survivable Branch Appliance al pool Front End di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7df2-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7df2-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a7df2-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a7df2-104">Ogni Survivable Branch Appliance (SBA) è associato a un pool Front End, che funge da registrar di backup per la SBA.</span><span class="sxs-lookup"><span data-stu-id="a7df2-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="a7df2-105">Quando il pool Front end viene aggiornato a Lync Server 2013, è necessario che l'SBA sia dissociata dal pool Front end mentre il pool Front end viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="a7df2-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="a7df2-106">Dopo l'aggiornamento del pool Front End, l'SBA può essere riassociato al pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a7df2-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="a7df2-107">Si tratta di eliminare l'ASB dalla topologia in Generatore di topologie e quindi aggiungere di nuovo l'SBA a Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a7df2-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="a7df2-108">Gli utenti ospitati nell'ASB devono essere spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="a7df2-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="a7df2-109">Dopo aver aggiunto la SBA alla topologia, gli utenti possono essere spostati di nuovo nell'ASB.</span><span class="sxs-lookup"><span data-stu-id="a7df2-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="a7df2-110">La procedura è sintetizzata sotto.</span><span class="sxs-lookup"><span data-stu-id="a7df2-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="a7df2-111">Spostare gli utenti di succursale presenti in SBA in un altro pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a7df2-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="a7df2-112">Rimuovere SBA dalla topologia per dissociare il pool Front end esistente come registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="a7df2-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="a7df2-113">Aggiornare il pool Front end a Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7df2-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="a7df2-114">Aggiungere nuovamente l'SBA alla topologia.</span><span class="sxs-lookup"><span data-stu-id="a7df2-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="a7df2-115">Associare il nuovo pool Front end all'ASB come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="a7df2-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="a7df2-116">Trasferire nuovamente gli utenti dei siti di succursale nell'SBA.</span><span class="sxs-lookup"><span data-stu-id="a7df2-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a7df2-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a7df2-117">In This Section</span></span>

  - [<span data-ttu-id="a7df2-118">Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2013 alla topologia</span><span class="sxs-lookup"><span data-stu-id="a7df2-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="a7df2-119">Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2010 alla topologia</span><span class="sxs-lookup"><span data-stu-id="a7df2-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

