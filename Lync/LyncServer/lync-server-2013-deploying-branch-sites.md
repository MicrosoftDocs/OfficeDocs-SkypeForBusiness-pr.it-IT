---
title: 'Lync Server 2013: Distribuzione di siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="d0ecc-102">Distribuzione di siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0ecc-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0ecc-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d0ecc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d0ecc-104">Gli utenti del sito della filiale ottengono la maggior parte delle funzionalità di Lync Server 2013 dal server nel sito centrale a cui è associato il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="d0ecc-105">Ogni sito di succursale è associato esattamente a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="d0ecc-106">Per eseguire chiamate da e verso la rete PSTN (Public Switched Telephone Network), un sito di succursale potrebbe contenere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ecc-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="d0ecc-107">Un gateway PSTN e possibilmente un server di meditazione</span><span class="sxs-lookup"><span data-stu-id="d0ecc-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="d0ecc-108">Trunk SIP</span><span class="sxs-lookup"><span data-stu-id="d0ecc-108">A SIP trunk</span></span>

  - <span data-ttu-id="d0ecc-109">Infrastruttura vocale esistente con un PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="d0ecc-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="d0ecc-110">Un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="d0ecc-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="d0ecc-111">Un Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="d0ecc-111">A Survivable Branch Server</span></span>

<span data-ttu-id="d0ecc-112">I siti di succursale con un Survivable Branch Appliance o un Survivable Branch Server sono più resistenti in tempi di errori di rete a livello di area geografica o di siti centrali diversi da quelli della filiale senza una di queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="d0ecc-113">Ad esempio, in un sito con un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere chiamate PSTN se la rete che connette il sito della filiale al sito centrale non è più presente.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="d0ecc-114">Un altro modo per ottenere la resilienza del sito della filiale consiste nell'usare un gateway PSTN o un trunk SIP con una distribuzione su vasta scala di Lync Server presso il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="d0ecc-115">Per informazioni dettagliate sulla distribuzione del sito della filiale appropriata per l'organizzazione, inclusi i prerequisiti e altre considerazioni sulla pianificazione, vedere [pianificazione della connettività PSTN in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [pianificazione della resilienza vocale del sito filiale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0ecc-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d0ecc-116">In This Section</span></span>

  - [<span data-ttu-id="d0ecc-117">Implementazione della connettività PSTN in un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0ecc-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="d0ecc-118">Distribuzione di Survivable Branch Appliance o Survivable Branch Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0ecc-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

