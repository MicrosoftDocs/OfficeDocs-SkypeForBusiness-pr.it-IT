---
title: Lync Server 2013 relazioni di registrazione di backup
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac47dcda07d7c0ca368cc572ccfafe2c6c95b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="1796a-102">Relazioni di registrazione di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1796a-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1796a-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="1796a-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="1796a-104">Oltre ad offrire funzioni di ripristino di emergenza, due pool accoppiati funzionano come registrar di backup l'uno per l'altro.</span><span class="sxs-lookup"><span data-stu-id="1796a-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="1796a-105">In Lync Server 2013, le relazioni di registrazione di backup tra pool Front End sono sempre 1:1 e reciproche.</span><span class="sxs-lookup"><span data-stu-id="1796a-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="1796a-106">Pertanto, se il P1 è il backup del P2, il P2 sarà il backup del P1, e nessuno dei due potrà essere il backup di un altro pool Front End.</span><span class="sxs-lookup"><span data-stu-id="1796a-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="1796a-107">Si tratta di una modifica da Lync Server 2010, in cui le relazioni di backup del pool Front end potrebbero essere numerose.</span><span class="sxs-lookup"><span data-stu-id="1796a-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="1796a-108">Anche se le relazioni di backup tra due pool Front end devono essere 1:1 e simmetriche, ogni pool Front end può essere sempre anche il servizio di registrazione di backup per un numero qualsiasi di Survivable Branch Appliance, come in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1796a-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="1796a-109">Si noti che Lync Server 2013 non estende il supporto per il ripristino di emergenza agli utenti ospitati in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="1796a-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="1796a-110">Se un pool Front end che funge da backup per un Survivable Branch Appliance diminuisce, gli utenti che hanno effettuato l'accesso a Survivable Branch Appliance rientrano in modalità di resilienza anche dopo che gli utenti ospitati nel pool Front end non sono riusciti a eseguire il backup nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="1796a-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

