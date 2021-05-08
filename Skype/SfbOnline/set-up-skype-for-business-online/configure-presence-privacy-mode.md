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
description: 'Scopri come configurare la modalità di privacy per gli utenti in modo che possano controllare meglio il modo in cui le persone vedono la loro disponibilità. '
ms.openlocfilehash: f8589dfb648693f0c0c4331a1a16119a3d7fe748
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239953"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="ba729-103">Configurare la modalità di privacy della presenza</span><span class="sxs-lookup"><span data-stu-id="ba729-103">Configure presence privacy mode</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="ba729-104">L Microsoft Teams di amministrazione ha sostituito l'Skype for Business di amministrazione (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="ba729-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="ba729-105">Tutte le impostazioni per la Skype for Business sono ora disponibili nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ba729-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="ba729-106">È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire Skype for Business funzionalità di Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ba729-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="ba729-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="ba729-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="ba729-108">L Skype for Business presenza online offre agli utenti un maggiore controllo su chi può vedere se sono disponibili, in una riunione o fuori sede.</span><span class="sxs-lookup"><span data-stu-id="ba729-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="ba729-109">Per informazioni dettagliate sulle Skype for Business di presenza e privacy, vedere Configurare la presenza [in Skype for Business Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="ba729-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="ba729-110">Scegliere l'impostazione della presenza online predefinita per tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ba729-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="ba729-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ba729-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="ba729-112">Passare all'interfaccia di amministrazione di Skype for Business Online > **organizzazione > Generale**.</span><span class="sxs-lookup"><span data-stu-id="ba729-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="ba729-113">In **Modalità privacy presenza** scegliere l'impostazione e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="ba729-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="ba729-114">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="ba729-114">**Setting**</span></span>|<span data-ttu-id="ba729-115">**Who possibile visualizzare la presenza di un utente**</span><span class="sxs-lookup"><span data-stu-id="ba729-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba729-116">**Visualizza automaticamente le informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="ba729-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="ba729-117">Qualunque utente di Skype for Business non appartenente al gruppo di privacy **Esterno** o **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="ba729-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="ba729-118">**Visualizzare le informazioni sulla presenza solo ai contatti di un utente**</span><span class="sxs-lookup"><span data-stu-id="ba729-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="ba729-119">Chiunque nell'elenco contatti di un utente non appartenga al **gruppo di** **privacy** Esterno o Bloccato.</span><span class="sxs-lookup"><span data-stu-id="ba729-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="ba729-120">I singoli utenti possono modificare questa impostazione nella Skype for Business **finestra di dialogo** Opzioni.</span><span class="sxs-lookup"><span data-stu-id="ba729-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="ba729-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ba729-121">Related topics</span></span>
[<span data-ttu-id="ba729-122">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ba729-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ba729-123">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="ba729-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
