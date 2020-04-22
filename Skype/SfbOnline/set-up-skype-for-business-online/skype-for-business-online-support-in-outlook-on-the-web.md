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
description: Outlook sul Web (Outlook Web App) in Office 365 offre un client web Skype for business di base dalla barra di spostamento. Questo client di base è disponibile per gli utenti online il cui amministratore non ha configurato un URL di vanità per il proprio Microsoft 365 o Office 365. Finché l'account dell'utente è online e non ha un URL di vanità, ne vedrà ancora l'esperienza, anche se l'organizzazione ha alcuni account utente ospitati in locale. Gli utenti che dispongono di un account utente locale (se hanno un URL di vanità o meno) o sono gestiti da Microsoft vedranno l'esperienza di Lync in Outlook Web App.
ms.openlocfilehash: 9ea26932db8551992ab441263e55548646039c7e
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777171"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="d104e-106">Supporto per Skype for Business Online in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="d104e-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="d104e-p102">Outlook sul Web (Outlook Web App) in Office 365 offre un client web Skype for business di base dalla barra di spostamento. Questo client di base è disponibile per gli utenti online il cui amministratore non ha configurato un URL di vanità per il proprio Microsoft 365 o Office 365. Finché l'account dell'utente è online e non ha un URL di vanità, ne vedrà ancora l'esperienza, anche se l'organizzazione ha alcuni account utente ospitati in locale. Gli utenti che dispongono di un account utente locale (se hanno un URL di vanità o meno) o sono gestiti da Microsoft vedranno l'esperienza di Lync in Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="d104e-p102">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 or Office 365. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="d104e-111">La tabella seguente riepiloga le diverse configurazioni che potresti avere e il client Web usato.</span><span class="sxs-lookup"><span data-stu-id="d104e-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d104e-112">**Posizione dell'account utente**</span><span class="sxs-lookup"><span data-stu-id="d104e-112">**User account is located**</span></span> <br/> |<span data-ttu-id="d104e-113">**L'URL di reindirizzamento a microsito è configurato oppure è presente un'organizzazione dedicata**</span><span class="sxs-lookup"><span data-stu-id="d104e-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="d104e-114">**Esperienza Skype for Business o Lync?**</span><span class="sxs-lookup"><span data-stu-id="d104e-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="d104e-115">Online</span><span class="sxs-lookup"><span data-stu-id="d104e-115">Online</span></span>  <br/> |<span data-ttu-id="d104e-116">No</span><span class="sxs-lookup"><span data-stu-id="d104e-116">No</span></span>  <br/> |<span data-ttu-id="d104e-117">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d104e-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-118">Online</span><span class="sxs-lookup"><span data-stu-id="d104e-118">Online</span></span>  <br/> |<span data-ttu-id="d104e-119">Sì</span><span class="sxs-lookup"><span data-stu-id="d104e-119">Yes</span></span>  <br/> |<span data-ttu-id="d104e-120">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="d104e-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-121">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="d104e-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d104e-122">No</span><span class="sxs-lookup"><span data-stu-id="d104e-122">No</span></span>  <br/> |<span data-ttu-id="d104e-123">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d104e-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-124">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="d104e-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d104e-125">Sì</span><span class="sxs-lookup"><span data-stu-id="d104e-125">Yes</span></span>  <br/> |<span data-ttu-id="d104e-126">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="d104e-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-127">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="d104e-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d104e-128">No</span><span class="sxs-lookup"><span data-stu-id="d104e-128">No</span></span>  <br/> |<span data-ttu-id="d104e-129">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="d104e-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-130">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="d104e-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d104e-131">Sì</span><span class="sxs-lookup"><span data-stu-id="d104e-131">Yes</span></span>  <br/> |<span data-ttu-id="d104e-132">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="d104e-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-133">Puro su Prem</span><span class="sxs-lookup"><span data-stu-id="d104e-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="d104e-134">No</span><span class="sxs-lookup"><span data-stu-id="d104e-134">No</span></span>  <br/> |<span data-ttu-id="d104e-135">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="d104e-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d104e-136">Puro su Prem</span><span class="sxs-lookup"><span data-stu-id="d104e-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="d104e-137">Sì</span><span class="sxs-lookup"><span data-stu-id="d104e-137">Yes</span></span>  <br/> |<span data-ttu-id="d104e-138">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="d104e-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="d104e-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d104e-139">Related topics</span></span>
[<span data-ttu-id="d104e-140">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d104e-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d104e-141">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="d104e-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
