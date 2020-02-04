---
title: 'Lync Server 2013: Abilitazione degli utenti per il E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86d5032defc7322e96662dcfe6357bd30c598e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="def6a-102">Abilitazione degli utenti per E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="def6a-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="def6a-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="def6a-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="def6a-104">Durante la registrazione del client, Lync Server usa un criterio di posizione per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="def6a-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="def6a-105">Questo criterio contiene le impostazioni che definiscono la modalità di implementazione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="def6a-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="def6a-106">Ad esempio, il criterio di posizione contiene informazioni come la stringa di chiamata di emergenza e se un utente deve immettere manualmente una posizione se il servizio informazioni sulla posizione non ne fornisce automaticamente uno.</span><span class="sxs-lookup"><span data-stu-id="def6a-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="def6a-107">Per una definizione completa di un criterio di posizione, vedere [definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="def6a-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="def6a-108">Lync Server può assegnare un criterio di posizione ai client in base alla subnet o agli utenti in base a un criterio globale, per sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="def6a-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="def6a-109">Per decidere come abilitare gli utenti, è necessario prima rispondere alle domande seguenti.</span><span class="sxs-lookup"><span data-stu-id="def6a-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="def6a-110">**Si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione?**</span><span class="sxs-lookup"><span data-stu-id="def6a-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="def6a-111">È possibile assegnare una posizione a tutti gli utenti dell'organizzazione usando un criterio di posizione globale.</span><span class="sxs-lookup"><span data-stu-id="def6a-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="def6a-112">Tuttavia, assegnando un criterio di posizione a un sito di rete di Lync Server e aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing di E9-1-1 per ogni singolo sito.</span><span class="sxs-lookup"><span data-stu-id="def6a-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="def6a-113">**Si prevede di abilitare singoli utenti tramite un criterio utente?**</span><span class="sxs-lookup"><span data-stu-id="def6a-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="def6a-114">Per personalizzare il supporto di E9-1-1, è possibile assegnare i criteri di posizione direttamente a utenti specifici o oggetti contatto telefonico di area comune.</span><span class="sxs-lookup"><span data-stu-id="def6a-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="def6a-115">**Quando i client vagano all'esterno della rete o si connettono da una subnet non definita, i client devono essere ancora abilitati per E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="def6a-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="def6a-116">Se agli utenti viene assegnato un criterio di posizione globale, sito o per utente, è possibile che sia necessario immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni sulla posizione non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="def6a-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="def6a-117">Per informazioni dettagliate, vedere [definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="def6a-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

