---
title: Supporto per Skype for Business Online in Outlook sul Web
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: La versione online di Outlook (Outlook Web App) in Office 365 offre un client Web Skype for Business di base dalla barra di navigazione. Questo client di base è disponibile per gli utenti Online cui amministratore non ha configurato un URL di reindirizzamento a microsito per la propria organizzazione Office 365. A condizione che l'account dell'utente è in linea e non dispone di un URL di reindirizzamento a microsito, cui viene visualizzata l'esperienza anche se l'organizzazione presenta alcuni account utente che sono ospitati in locale. Gli utenti che hanno utente account in locale (che hanno un URL di reindirizzamento a microsito o non) o gestiti da Microsoft vedranno l'esperienza di Lync in Outlook web app.
ms.openlocfilehash: 4ba094640ddfb77e39640f6a610da150320dd867
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="3d75d-106">Supporto per Skype for Business Online in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="3d75d-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="3d75d-107">La versione online di Outlook (Outlook Web App) in Office 365 offre un client Web Skype for Business di base dalla barra di navigazione.</span><span class="sxs-lookup"><span data-stu-id="3d75d-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="3d75d-108">Questo client di base è disponibile per gli utenti Online cui amministratore non ha configurato un URL di reindirizzamento a microsito per la propria organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d75d-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="3d75d-109">A condizione che l'account dell'utente è in linea e non dispone di un URL di reindirizzamento a microsito, cui viene visualizzata l'esperienza anche se l'organizzazione presenta alcuni account utente che sono ospitati in locale.</span><span class="sxs-lookup"><span data-stu-id="3d75d-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="3d75d-110">Gli utenti che hanno utente account in locale (che hanno un URL di reindirizzamento a microsito o non) o gestiti da Microsoft vedranno l'esperienza di Lync in Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="3d75d-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="3d75d-111">Nella tabella seguente sono riepilogate le installazioni diverse che possono verificarsi e il client web utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3d75d-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="3d75d-112">**Posizione dell'account utente**</span><span class="sxs-lookup"><span data-stu-id="3d75d-112">**User account is located**</span></span> <br/> |<span data-ttu-id="3d75d-113">**L'URL di reindirizzamento a microsito è configurato oppure è presente un'organizzazione dedicata**</span><span class="sxs-lookup"><span data-stu-id="3d75d-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="3d75d-114">**Esperienza Skype for Business o Lync?**</span><span class="sxs-lookup"><span data-stu-id="3d75d-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="3d75d-115">Online</span><span class="sxs-lookup"><span data-stu-id="3d75d-115">Online</span></span>  <br/> |<span data-ttu-id="3d75d-116">No</span><span class="sxs-lookup"><span data-stu-id="3d75d-116">No</span></span>  <br/> |<span data-ttu-id="3d75d-117">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d75d-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-118">Online</span><span class="sxs-lookup"><span data-stu-id="3d75d-118">Online</span></span>  <br/> |<span data-ttu-id="3d75d-119">Sì</span><span class="sxs-lookup"><span data-stu-id="3d75d-119">Yes</span></span>  <br/> |<span data-ttu-id="3d75d-120">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="3d75d-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-121">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="3d75d-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="3d75d-122">No</span><span class="sxs-lookup"><span data-stu-id="3d75d-122">No</span></span>  <br/> |<span data-ttu-id="3d75d-123">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d75d-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-124">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="3d75d-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="3d75d-125">Sì</span><span class="sxs-lookup"><span data-stu-id="3d75d-125">Yes</span></span>  <br/> |<span data-ttu-id="3d75d-126">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="3d75d-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-127">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="3d75d-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="3d75d-128">No</span><span class="sxs-lookup"><span data-stu-id="3d75d-128">No</span></span>  <br/> |<span data-ttu-id="3d75d-129">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="3d75d-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-130">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="3d75d-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="3d75d-131">Sì</span><span class="sxs-lookup"><span data-stu-id="3d75d-131">Yes</span></span>  <br/> |<span data-ttu-id="3d75d-132">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="3d75d-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-133">Solo bianco in % beni</span><span class="sxs-lookup"><span data-stu-id="3d75d-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="3d75d-134">No</span><span class="sxs-lookup"><span data-stu-id="3d75d-134">No</span></span>  <br/> |<span data-ttu-id="3d75d-135">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="3d75d-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="3d75d-136">Solo bianco in % beni</span><span class="sxs-lookup"><span data-stu-id="3d75d-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="3d75d-137">Sì</span><span class="sxs-lookup"><span data-stu-id="3d75d-137">Yes</span></span>  <br/> |<span data-ttu-id="3d75d-138">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="3d75d-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="3d75d-139">See also</span><span class="sxs-lookup"><span data-stu-id="3d75d-139">Related topics</span></span>
[<span data-ttu-id="3d75d-140">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3d75d-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3d75d-141">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="3d75d-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 