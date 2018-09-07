---
title: Supporto per Skype for Business Online in Outlook sul Web
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: La versione online di Outlook (Outlook Web App) in Office 365 offre un client Web Skype for Business di base dalla barra di navigazione. Questo client di base è disponibile per gli utenti Online cui amministratore non ha configurato un URL di reindirizzamento a microsito per la propria organizzazione Office 365. A condizione che l'account dell'utente è in linea e non dispone di un URL di reindirizzamento a microsito, cui viene visualizzata l'esperienza anche se l'organizzazione presenta alcuni account utente che sono ospitati in locale. Gli utenti che hanno utente account in locale (che hanno un URL di reindirizzamento a microsito o non) o gestiti da Microsoft vedranno l'esperienza di Lync in Outlook web app.
ms.openlocfilehash: 112da508d0f21175d309679a529f86d22a37d0d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863246"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="21a63-106">Supporto per Skype for Business Online in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="21a63-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="21a63-107">La versione online di Outlook (Outlook Web App) in Office 365 offre un client Web Skype for Business di base dalla barra di navigazione.</span><span class="sxs-lookup"><span data-stu-id="21a63-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="21a63-108">Questo client di base è disponibile per gli utenti Online cui amministratore non ha configurato un URL di reindirizzamento a microsito per la propria organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="21a63-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="21a63-109">A condizione che l'account dell'utente è in linea e non dispone di un URL di reindirizzamento a microsito, cui viene visualizzata l'esperienza anche se l'organizzazione presenta alcuni account utente che sono ospitati in locale.</span><span class="sxs-lookup"><span data-stu-id="21a63-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="21a63-110">Gli utenti che hanno utente account in locale (che hanno un URL di reindirizzamento a microsito o non) o gestiti da Microsoft vedranno l'esperienza di Lync in Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="21a63-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="21a63-111">Nella tabella seguente sono riepilogate le installazioni diverse che possono verificarsi e il client web utilizzato.</span><span class="sxs-lookup"><span data-stu-id="21a63-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="21a63-112">**Posizione dell'account utente**</span><span class="sxs-lookup"><span data-stu-id="21a63-112">**User account is located**</span></span> <br/> |<span data-ttu-id="21a63-113">**L'URL di reindirizzamento a microsito è configurato oppure è presente un'organizzazione dedicata**</span><span class="sxs-lookup"><span data-stu-id="21a63-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="21a63-114">**Esperienza Skype for Business o Lync?**</span><span class="sxs-lookup"><span data-stu-id="21a63-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="21a63-115">Online</span><span class="sxs-lookup"><span data-stu-id="21a63-115">Online</span></span>  <br/> |<span data-ttu-id="21a63-116">No</span><span class="sxs-lookup"><span data-stu-id="21a63-116">No</span></span>  <br/> |<span data-ttu-id="21a63-117">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="21a63-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-118">Online</span><span class="sxs-lookup"><span data-stu-id="21a63-118">Online</span></span>  <br/> |<span data-ttu-id="21a63-119">Sì</span><span class="sxs-lookup"><span data-stu-id="21a63-119">Yes</span></span>  <br/> |<span data-ttu-id="21a63-120">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="21a63-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-121">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="21a63-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="21a63-122">No</span><span class="sxs-lookup"><span data-stu-id="21a63-122">No</span></span>  <br/> |<span data-ttu-id="21a63-123">Esperienza Web di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="21a63-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-124">Ibrida ma ospitata online</span><span class="sxs-lookup"><span data-stu-id="21a63-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="21a63-125">Sì</span><span class="sxs-lookup"><span data-stu-id="21a63-125">Yes</span></span>  <br/> |<span data-ttu-id="21a63-126">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="21a63-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-127">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="21a63-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="21a63-128">No</span><span class="sxs-lookup"><span data-stu-id="21a63-128">No</span></span>  <br/> |<span data-ttu-id="21a63-129">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="21a63-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-130">Ibrida ma ospitata in locale</span><span class="sxs-lookup"><span data-stu-id="21a63-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="21a63-131">Sì</span><span class="sxs-lookup"><span data-stu-id="21a63-131">Yes</span></span>  <br/> |<span data-ttu-id="21a63-132">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="21a63-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-133">Solo bianco in % beni</span><span class="sxs-lookup"><span data-stu-id="21a63-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="21a63-134">No</span><span class="sxs-lookup"><span data-stu-id="21a63-134">No</span></span>  <br/> |<span data-ttu-id="21a63-135">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="21a63-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="21a63-136">Solo bianco in % beni</span><span class="sxs-lookup"><span data-stu-id="21a63-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="21a63-137">Sì</span><span class="sxs-lookup"><span data-stu-id="21a63-137">Yes</span></span>  <br/> |<span data-ttu-id="21a63-138">Esperienza Web di Lync</span><span class="sxs-lookup"><span data-stu-id="21a63-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="21a63-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="21a63-139">Related topics</span></span>
[<span data-ttu-id="21a63-140">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="21a63-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="21a63-141">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="21a63-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 