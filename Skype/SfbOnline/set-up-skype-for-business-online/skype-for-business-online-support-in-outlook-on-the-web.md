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
description: Outlook sul Web (Outlook Web App) in Microsoft 365 o Office 365 offre un client Web Skype for Business di base dalla barra di spostamento. Questo client di base è disponibile per gli utenti online il cui amministratore non ha configurato un URL di vanità per i Microsoft 365 e Office 365. Finché l'account dell'utente è online e non ha un URL di vanità, continuerà a vedere l'esperienza anche se l'organizzazione ha alcuni account utente ospitati in locale. Gli utenti che hanno account utente locali (indipendentemente dal fatto che hanno un URL di vanità o meno) o che siano gestiti da Microsoft potranno vedere l'esperienza di Lync nell'app Web Outlook web app.
ms.openlocfilehash: aa6f82f6647db1816c630486bee0d415d05b3b77
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239571"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="58483-106">Supporto per Skype for Business Online in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="58483-106">Skype for Business Online support in Outlook on the web</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="58483-107">Outlook sul Web (Outlook Web App) in Microsoft 365 o Office 365 offre un client Web Skype for Business di base dalla barra di spostamento.</span><span class="sxs-lookup"><span data-stu-id="58483-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="58483-108">Questo client di base è disponibile per gli utenti online il cui amministratore non ha configurato un URL di vanità per i Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="58483-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="58483-109">Finché l'account dell'utente è online e non ha un URL di vanità, continuerà a vedere l'esperienza anche se l'organizzazione ha alcuni account utente ospitati in locale.</span><span class="sxs-lookup"><span data-stu-id="58483-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="58483-110">Gli utenti che hanno account utente locali (indipendentemente dal fatto che hanno un URL di vanità o meno) o che siano gestiti da Microsoft potranno vedere l'esperienza di Lync nell'app Web Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="58483-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="58483-111">La tabella seguente riepiloga le diverse configurazioni disponibili e il client Web usato.</span><span class="sxs-lookup"><span data-stu-id="58483-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="58483-112">**Posizione dell'account utente**</span><span class="sxs-lookup"><span data-stu-id="58483-112">**User account is located**</span></span> <br/> |<span data-ttu-id="58483-113">**L'URL di reindirizzamento a microsito è configurato oppure è presente un'organizzazione dedicata**</span><span class="sxs-lookup"><span data-stu-id="58483-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="58483-114">**Esperienza Skype for Business o Lync?**</span><span class="sxs-lookup"><span data-stu-id="58483-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="58483-115">Online</span><span class="sxs-lookup"><span data-stu-id="58483-115">Online</span></span>  <br/> |<span data-ttu-id="58483-116">No</span><span class="sxs-lookup"><span data-stu-id="58483-116">No</span></span>  <br/> |<span data-ttu-id="58483-117">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58483-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="58483-118">Online</span><span class="sxs-lookup"><span data-stu-id="58483-118">Online</span></span>  <br/> |<span data-ttu-id="58483-119">Sì</span><span class="sxs-lookup"><span data-stu-id="58483-119">Yes</span></span>  <br/> |<span data-ttu-id="58483-120">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="58483-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="58483-121">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="58483-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="58483-122">No</span><span class="sxs-lookup"><span data-stu-id="58483-122">No</span></span>  <br/> |<span data-ttu-id="58483-123">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58483-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="58483-124">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="58483-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="58483-125">Sì</span><span class="sxs-lookup"><span data-stu-id="58483-125">Yes</span></span>  <br/> |<span data-ttu-id="58483-126">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="58483-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="58483-127">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="58483-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="58483-128">No</span><span class="sxs-lookup"><span data-stu-id="58483-128">No</span></span>  <br/> |<span data-ttu-id="58483-129">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="58483-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="58483-130">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="58483-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="58483-131">Sì</span><span class="sxs-lookup"><span data-stu-id="58483-131">Yes</span></span>  <br/> |<span data-ttu-id="58483-132">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="58483-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="58483-133">Pure in prem</span><span class="sxs-lookup"><span data-stu-id="58483-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="58483-134">No</span><span class="sxs-lookup"><span data-stu-id="58483-134">No</span></span>  <br/> |<span data-ttu-id="58483-135">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="58483-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="58483-136">Pure in prem</span><span class="sxs-lookup"><span data-stu-id="58483-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="58483-137">Sì</span><span class="sxs-lookup"><span data-stu-id="58483-137">Yes</span></span>  <br/> |<span data-ttu-id="58483-138">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="58483-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="58483-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="58483-139">Related topics</span></span>
[<span data-ttu-id="58483-140">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="58483-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="58483-141">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="58483-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
