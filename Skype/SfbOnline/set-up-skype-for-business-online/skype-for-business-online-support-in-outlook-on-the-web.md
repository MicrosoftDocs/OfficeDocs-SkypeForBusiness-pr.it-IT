---
title: Supporto per Skype for Business Online in Outlook sul Web
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Outlook sul web (Outlook Web App) in Microsoft 365 o Office 365 offre un client Web skype for Business di base dalla barra di spostamento. Questo client di base è disponibile per gli utenti online il cui amministratore non ha configurato un URL di reindirizzamento a vanity per Microsoft 365 e Office 365. Finché l'account utente è online e non ha un URL di reindirizzamento a vanity, continuerà a vedere l'esperienza anche se l'organizzazione ha alcuni account utente ospitati in locale. Gli utenti che hanno account utente in locale (che hanno o meno un URL di reindirizzamento a una rete aziendale) o che sono gestiti da Microsoft potranno visualizzare l'esperienza Lync in Outlook Web App.
ms.openlocfilehash: ab426bdaf0261dcfb3375934eb1e5a6f5bd6df79
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164108"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="5adf6-106">Supporto per Skype for Business Online in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="5adf6-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="5adf6-p102">Outlook sul web (Outlook Web App) in Microsoft 365 o Office 365 offre un client Web skype for Business di base dalla barra di spostamento. Questo client di base è disponibile per gli utenti online il cui amministratore non ha configurato un URL di reindirizzamento a vanity per Microsoft 365 e Office 365. Finché l'account utente è online e non ha un URL di reindirizzamento a vanity, continuerà a vedere l'esperienza anche se l'organizzazione ha alcuni account utente ospitati in locale. Gli utenti che hanno account utente in locale (che hanno o meno un URL di reindirizzamento a una rete aziendale) o che sono gestiti da Microsoft potranno visualizzare l'esperienza Lync in Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="5adf6-p102">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="5adf6-111">La tabella seguente riepiloga le diverse configurazioni disponibili e il client Web in uso.</span><span class="sxs-lookup"><span data-stu-id="5adf6-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="5adf6-112">**Posizione dell'account utente**</span><span class="sxs-lookup"><span data-stu-id="5adf6-112">**User account is located**</span></span> <br/> |<span data-ttu-id="5adf6-113">**L'URL di reindirizzamento a microsito è configurato oppure è presente un'organizzazione dedicata**</span><span class="sxs-lookup"><span data-stu-id="5adf6-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="5adf6-114">**Esperienza Skype for Business o Lync?**</span><span class="sxs-lookup"><span data-stu-id="5adf6-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="5adf6-115">Online</span><span class="sxs-lookup"><span data-stu-id="5adf6-115">Online</span></span>  <br/> |<span data-ttu-id="5adf6-116">No</span><span class="sxs-lookup"><span data-stu-id="5adf6-116">No</span></span>  <br/> |<span data-ttu-id="5adf6-117">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5adf6-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-118">Online</span><span class="sxs-lookup"><span data-stu-id="5adf6-118">Online</span></span>  <br/> |<span data-ttu-id="5adf6-119">Sì</span><span class="sxs-lookup"><span data-stu-id="5adf6-119">Yes</span></span>  <br/> |<span data-ttu-id="5adf6-120">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="5adf6-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-121">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="5adf6-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="5adf6-122">No</span><span class="sxs-lookup"><span data-stu-id="5adf6-122">No</span></span>  <br/> |<span data-ttu-id="5adf6-123">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5adf6-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-124">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="5adf6-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="5adf6-125">Sì</span><span class="sxs-lookup"><span data-stu-id="5adf6-125">Yes</span></span>  <br/> |<span data-ttu-id="5adf6-126">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="5adf6-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-127">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="5adf6-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="5adf6-128">No</span><span class="sxs-lookup"><span data-stu-id="5adf6-128">No</span></span>  <br/> |<span data-ttu-id="5adf6-129">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="5adf6-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-130">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="5adf6-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="5adf6-131">Sì</span><span class="sxs-lookup"><span data-stu-id="5adf6-131">Yes</span></span>  <br/> |<span data-ttu-id="5adf6-132">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="5adf6-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-133">Solo in pre-</span><span class="sxs-lookup"><span data-stu-id="5adf6-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="5adf6-134">No</span><span class="sxs-lookup"><span data-stu-id="5adf6-134">No</span></span>  <br/> |<span data-ttu-id="5adf6-135">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="5adf6-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5adf6-136">Solo in pre-</span><span class="sxs-lookup"><span data-stu-id="5adf6-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="5adf6-137">Sì</span><span class="sxs-lookup"><span data-stu-id="5adf6-137">Yes</span></span>  <br/> |<span data-ttu-id="5adf6-138">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="5adf6-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="5adf6-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5adf6-139">Related topics</span></span>
[<span data-ttu-id="5adf6-140">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="5adf6-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5adf6-141">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="5adf6-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
