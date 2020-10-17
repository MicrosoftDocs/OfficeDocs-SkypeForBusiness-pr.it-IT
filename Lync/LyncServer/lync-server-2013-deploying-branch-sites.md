---
title: 'Lync Server 2013: distribuzione di siti di succursale'
description: 'Lync Server 2013: distribuzione di siti di succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552642"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="94bb9-103">Distribuzione di siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-103">Deploying branch sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94bb9-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="94bb9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="94bb9-105">Gli utenti del sito di succursale ottengono la maggior parte delle funzionalità di Lync Server 2013 dal server nel sito centrale a cui è associato il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="94bb9-105">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="94bb9-106">Ogni sito di succursale è associato esattamente a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="94bb9-106">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="94bb9-107">Per garantire le chiamate alla e dalla rete PSTN (Public Switched Telephone Network), un sito di succursale può includere uno o più elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="94bb9-107">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="94bb9-108">Un gateway PSTN ed eventualmente un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="94bb9-108">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="94bb9-109">Un trunk SIP</span><span class="sxs-lookup"><span data-stu-id="94bb9-109">A SIP trunk</span></span>

  - <span data-ttu-id="94bb9-110">Un'infrastruttura vocale esistente con un centralino (PBX)</span><span class="sxs-lookup"><span data-stu-id="94bb9-110">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="94bb9-111">Un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="94bb9-111">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="94bb9-112">Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="94bb9-112">A Survivable Branch Server</span></span>

<span data-ttu-id="94bb9-113">I siti di succursale con un Survivable Branch Appliance o un Survivable Branch Server sono più resistenti in periodi di problemi di rete o di siti centrali di aree estese rispetto a quelli di succursale senza una di queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="94bb9-113">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="94bb9-114">Ad esempio, in un sito in cui è presente un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere chiamate PSTN se la rete che connette il sito di succursale al sito centrale è inattivo.</span><span class="sxs-lookup"><span data-stu-id="94bb9-114">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="94bb9-115">Un altro modo per ottenere la resilienza dei siti di succursale consiste nell'utilizzare un gateway PSTN o un trunk SIP con una distribuzione di Lync Server su vasta scala nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="94bb9-115">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="94bb9-116">Per informazioni dettagliate sulla distribuzione dei siti di succursale per l'organizzazione, inclusi i prerequisiti e altre considerazioni relative alla pianificazione, vedere [Planning for PSTN Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [Planning for Branch-site Voice Resilienzy in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="94bb9-116">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94bb9-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="94bb9-117">In This Section</span></span>

  - [<span data-ttu-id="94bb9-118">Fornitura di connettività PSTN in un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-118">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="94bb9-119">Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-119">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

