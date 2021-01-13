---
title: Pianificare il controllo delle chiamate remote in Skype for business
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
description: Il controllo delle chiamate remote era una funzionalità nelle versioni precedenti di Lync Server, che consentiva agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro. Nelle versioni client per Skype for Business Server 2015 e in futuro, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'utilizzo.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813516"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="090db-105">Pianificare il controllo delle chiamate remote in Skype for business</span><span class="sxs-lookup"><span data-stu-id="090db-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="090db-106">Il controllo delle chiamate remote era una funzionalità nelle versioni precedenti di Lync Server, che consentiva agli utenti di controllare i telefoni PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="090db-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="090db-107">In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="090db-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="090db-108">*Nelle versioni client per Skype for Business Server 2015 e in futuro, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'utilizzo.*</span><span class="sxs-lookup"><span data-stu-id="090db-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="090db-109">Gli utenti del controllo delle chiamate remote nell'organizzazione ospitati nei front end server che eseguono Lync Server possono continuare a utilizzare il controllo delle chiamate remote, anche se utilizzano un client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="090db-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="090db-110">Tuttavia, per tutti gli utenti ospitati su Skype for Business Server, il controllo delle chiamate remote non è supportato.</span><span class="sxs-lookup"><span data-stu-id="090db-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="090db-111">Vedere la tabella seguente per le combinazioni di server/client e se è in grado di supportare il controllo delle chiamate remote o la chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="090db-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="090db-112">**Client Skype for business con interfaccia utente Skype abilitata**</span><span class="sxs-lookup"><span data-stu-id="090db-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="090db-113">**Client Skype for business con Lync UI abilitata**</span><span class="sxs-lookup"><span data-stu-id="090db-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="090db-114">**Client Skype for business 2016**</span><span class="sxs-lookup"><span data-stu-id="090db-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="090db-115">**Client Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="090db-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="090db-116">**Lync 2010 Client**</span><span class="sxs-lookup"><span data-stu-id="090db-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="090db-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="090db-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="090db-118">Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="090db-118">Call via Work</span></span>  <br/> |<span data-ttu-id="090db-119">1 </span><span class="sxs-lookup"><span data-stu-id="090db-119">1</span></span> <br/> |<span data-ttu-id="090db-120">Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="090db-120">Call via Work</span></span>  <br/> |<span data-ttu-id="090db-121">1 </span><span class="sxs-lookup"><span data-stu-id="090db-121">1</span></span> <br/> |<span data-ttu-id="090db-122">1 </span><span class="sxs-lookup"><span data-stu-id="090db-122">1</span></span> <br/> |
| <span data-ttu-id="090db-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090db-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="090db-124">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="090db-125">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="090db-126">1 </span><span class="sxs-lookup"><span data-stu-id="090db-126">1</span></span> <br/> |<span data-ttu-id="090db-127">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="090db-128">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="090db-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="090db-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="090db-130">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="090db-131">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="090db-132">1 </span><span class="sxs-lookup"><span data-stu-id="090db-132">1</span></span> <br/> |<span data-ttu-id="090db-133">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="090db-134">Controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="090db-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="090db-135">Nessuna caratteristica è supportata.</span><span class="sxs-lookup"><span data-stu-id="090db-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="090db-136">Per ulteriori informazioni, vedere [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) nella documentazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="090db-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="090db-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="090db-137">See also</span></span>

[<span data-ttu-id="090db-138">Pianificare la chiamata tramite il lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="090db-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="090db-139">Confronto delle funzionalità dei client desktop per Skype for business</span><span class="sxs-lookup"><span data-stu-id="090db-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="090db-140">Effettuare una chiamata Skype for business, ma utilizzare il telefono da tavolo PBX per l'audio</span><span class="sxs-lookup"><span data-stu-id="090db-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

