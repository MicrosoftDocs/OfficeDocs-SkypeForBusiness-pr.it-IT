---
title: 'Lync Server 2013: Modalità di bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f92d45099f39ec96724f8d0f6025f58e2dbccb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41761952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="e6756-102">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6756-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6756-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="e6756-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="e6756-104">È necessario configurare il bypass multimediale sia a livello globale che per ogni singolo trunk PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6756-104">You must configure media bypass both globally and for each individual PSTN trunk.</span></span> <span data-ttu-id="e6756-105">Quando si Abilita il bypass multimediale a livello globale, sono disponibili due opzioni: **Ignora sempre** e **Usa le informazioni sul sito e le aree**geografiche.</span><span class="sxs-lookup"><span data-stu-id="e6756-105">When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="e6756-106">Come suggerisce il nome, il **bypass indica sempre** che il bypass verrà tentato per tutte le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6756-106">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls.</span></span> <span data-ttu-id="e6756-107">Il bypass viene usato **sempre** per le distribuzioni in cui non è necessario abilitare il controllo di ammissione alle chiamate e non è necessario specificare informazioni dettagliate sulla configurazione per il tentativo di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e6756-107">**Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass.</span></span> <span data-ttu-id="e6756-108">Inoltre, **sempre l'esclusione** viene usata quando esiste una connettività completa tra client e gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6756-108">Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways.</span></span> <span data-ttu-id="e6756-109">In questa configurazione tutte le subnet sono mappate a uno e solo un ID di bypass, calcolato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="e6756-109">In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="e6756-110">Con le **informazioni sull'uso di siti e aree**geografiche, l'ID di bypass associato alla configurazione del sito e dell'area geografica viene usato per prendere la decisione di bypass.</span><span class="sxs-lookup"><span data-stu-id="e6756-110">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision.</span></span> <span data-ttu-id="e6756-111">Questa configurazione offre la flessibilità necessaria per configurare il bypass per le topologie più comuni, in quanto offre un controllo preciso quando si verifica un bypass, oltre a supportare le interazioni con il controllo di ammissione alle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="e6756-111">This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC).</span></span> <span data-ttu-id="e6756-112">Il sistema cerca di semplificare l'attività assegnando automaticamente gli ID di bypass come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e6756-112">The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="e6756-113">Il sistema assegna automaticamente un singolo ID di bypass univoco a ogni area geografica.</span><span class="sxs-lookup"><span data-stu-id="e6756-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="e6756-114">Qualsiasi sito connesso a un'area geografica su un collegamento WAN senza vincoli di larghezza di banda eredita lo stesso ID di bypass dell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="e6756-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="e6756-115">Un sito associato all'area geografica su un collegamento WAN con larghezza di banda vincolata viene assegnato un ID di bypass diverso da quello dell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="e6756-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="e6756-116">Le subnet associate a ogni sito ereditano l'ID di bypass per il sito.</span><span class="sxs-lookup"><span data-stu-id="e6756-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e6756-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6756-117">See Also</span></span>


[<span data-ttu-id="e6756-118">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6756-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="e6756-119">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6756-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="e6756-120">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6756-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

