---
title: Pianificare il controllo delle chiamate remote in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Il controllo delle chiamate remote era una funzionalità delle versioni precedenti di Lync Server che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama tramite lavoro. Nelle versioni client per Skype for Business Server 2015 e in futuro, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'uso.
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114612"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="a3407-105">Pianificare il controllo delle chiamate remote in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a3407-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="a3407-106">Il controllo delle chiamate remote era una funzionalità delle versioni precedenti di Lync Server che consente agli utenti di controllare i telefoni PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3407-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="a3407-107">In Skype for Business Server, questa funzionalità è stata sostituita con Chiama tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3407-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="a3407-108">*Nelle versioni client per Skype for Business Server 2015 e in futuro, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'uso.*</span><span class="sxs-lookup"><span data-stu-id="a3407-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="a3407-109">Gli utenti del controllo delle chiamate remote nell'organizzazione ospitati nei Front End Server che eseguono Lync Server possono continuare a utilizzare il controllo delle chiamate remote, anche se utilizzano un client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a3407-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="a3407-110">Tuttavia, per tutti gli utenti ospitati in Skype for Business Server, il controllo delle chiamate remote non è supportato.</span><span class="sxs-lookup"><span data-stu-id="a3407-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="a3407-111">Vedere la tabella seguente per le combinazioni server/client e se sono in grado di supportare il controllo delle chiamate remote o chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3407-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="a3407-112">**Client Skype for Business con interfaccia utente Skype abilitata**</span><span class="sxs-lookup"><span data-stu-id="a3407-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="a3407-113">**Client Skype for Business con interfaccia utente di Lync abilitata**</span><span class="sxs-lookup"><span data-stu-id="a3407-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="a3407-114">**Skype for Business 2016 Client**</span><span class="sxs-lookup"><span data-stu-id="a3407-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="a3407-115">**Lync 2013 Client**</span><span class="sxs-lookup"><span data-stu-id="a3407-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="a3407-116">**Lync 2010 Client**</span><span class="sxs-lookup"><span data-stu-id="a3407-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a3407-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a3407-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="a3407-118">Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="a3407-118">Call via Work</span></span>  <br/> |<span data-ttu-id="a3407-119">1</span><span class="sxs-lookup"><span data-stu-id="a3407-119">1</span></span> <br/> |<span data-ttu-id="a3407-120">Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="a3407-120">Call via Work</span></span>  <br/> |<span data-ttu-id="a3407-121">1</span><span class="sxs-lookup"><span data-stu-id="a3407-121">1</span></span> <br/> |<span data-ttu-id="a3407-122">1</span><span class="sxs-lookup"><span data-stu-id="a3407-122">1</span></span> <br/> |
| <span data-ttu-id="a3407-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3407-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="a3407-124">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a3407-125">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a3407-126">1</span><span class="sxs-lookup"><span data-stu-id="a3407-126">1</span></span> <br/> |<span data-ttu-id="a3407-127">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a3407-128">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="a3407-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a3407-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="a3407-130">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a3407-131">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a3407-132">1</span><span class="sxs-lookup"><span data-stu-id="a3407-132">1</span></span> <br/> |<span data-ttu-id="a3407-133">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a3407-134">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="a3407-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="a3407-135">Nessuna delle due funzionalità è supportata.</span><span class="sxs-lookup"><span data-stu-id="a3407-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="a3407-136">Per ulteriori informazioni, vedere [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) nella documentazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3407-136">For more information, see [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3407-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3407-137">See also</span></span>

[<span data-ttu-id="a3407-138">Pianificare la chiamata tramite lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a3407-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="a3407-139">Confronto delle funzionalità del client desktop per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a3407-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="a3407-140">Effettuare una chiamata Skype for Business ma usare il telefono da tavolo PBX per l'audio</span><span class="sxs-lookup"><span data-stu-id="a3407-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)