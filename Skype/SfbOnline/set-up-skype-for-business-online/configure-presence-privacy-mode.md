---
title: Configurare la modalità di privacy della presenza
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: 'Informazioni su come configurare la modalità di privacy per gli utenti in modo che possano controllare meglio la visualizzazione della disponibilità degli utenti. '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753441"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="0c66c-103">Configurare la modalità di privacy della presenza</span><span class="sxs-lookup"><span data-stu-id="0c66c-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c66c-104">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="0c66c-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="0c66c-105">Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="0c66c-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="0c66c-106">Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario disporre del ruolo di amministratore di [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) come amministratore globale o amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0c66c-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="0c66c-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="0c66c-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="0c66c-108">L'impostazione della presenza di Skype for Business online offre alle persone un maggior controllo su chi può vedere se sono disponibili, in riunione o fuori sede.</span><span class="sxs-lookup"><span data-stu-id="0c66c-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="0c66c-109">Per informazioni dettagliate sulle impostazioni di privacy e presenza di Skype for Business, consulta [Configurare la presenza in Skype for Business online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="0c66c-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="0c66c-110">Scegliere l'impostazione della presenza online predefinita per tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0c66c-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="0c66c-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c66c-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="0c66c-112">Accedi all'interfaccia di amministrazione di Skype for Business online **>'> generale.**</span><span class="sxs-lookup"><span data-stu-id="0c66c-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="0c66c-113">In **Modalità privacy presenza** scegliere l'impostazione e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0c66c-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="0c66c-114">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="0c66c-114">**Setting**</span></span>|<span data-ttu-id="0c66c-115">**Chi può visualizzare la presenza di un utente**</span><span class="sxs-lookup"><span data-stu-id="0c66c-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0c66c-116">**Visualizza automaticamente le informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="0c66c-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="0c66c-117">Qualunque utente di Skype for Business non appartenente al gruppo di privacy **Esterno** o **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="0c66c-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="0c66c-118">**Visualizzare le informazioni sulla presenza solo per i contatti di un utente**</span><span class="sxs-lookup"><span data-stu-id="0c66c-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="0c66c-119">Tutti gli utenti nell'elenco contatti di un utente che non appartengono **al gruppo di** privacy esterno **o** bloccato.</span><span class="sxs-lookup"><span data-stu-id="0c66c-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="0c66c-120">I singoli utenti possono modificare questa impostazione nella finestra di dialogo **Opzioni** di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0c66c-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="0c66c-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0c66c-121">Related topics</span></span>
[<span data-ttu-id="0c66c-122">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="0c66c-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0c66c-123">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="0c66c-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
