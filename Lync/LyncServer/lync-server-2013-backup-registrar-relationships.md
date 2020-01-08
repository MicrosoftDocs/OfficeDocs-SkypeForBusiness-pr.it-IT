---
title: 'Lync Server 2013: Eseguire il backup delle relazioni di registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a642c8d8872b2c0d1372a209c9c05dac704ee20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="05956-102">Eseguire il backup delle relazioni di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05956-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05956-103">_**Argomento Ultima modifica:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="05956-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="05956-104">Oltre a fornire un'abilità di ripristino di emergenza, due pool associati fungono da registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="05956-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="05956-105">In Lync Server 2013 le relazioni di registrazione del backup tra i pool Front-End sono sempre 1:1 e reciproche.</span><span class="sxs-lookup"><span data-stu-id="05956-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="05956-106">Questo significa che se P1 è il backup per P2, P2 deve essere il backup per P1 e non può essere il backup per qualsiasi altro pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="05956-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="05956-107">Si tratta di una modifica da Lync Server 2010, in cui le relazioni di backup del pool Front-end possono essere diverse rispetto a una.</span><span class="sxs-lookup"><span data-stu-id="05956-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="05956-108">Anche se le relazioni di backup tra due pool Front-end devono essere di 1:1 e simmetriche, ogni pool Front-end può essere comunque anche il registrar per qualsiasi numero di appliance Survivable Branch, proprio come in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="05956-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="05956-109">Si noti che Lync Server 2013 non estende il supporto per il ripristino di emergenza agli utenti ospitati in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="05956-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="05956-110">Se un pool Front-end che funge da backup per un appliance Survivable Branch si abbassa, gli utenti che hanno effettuato l'accesso a Survivable Branch Appliance vengono rientrati in modalità di resilienza anche dopo che gli utenti ospitati nel pool Front-end non vengono eseguiti nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="05956-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

