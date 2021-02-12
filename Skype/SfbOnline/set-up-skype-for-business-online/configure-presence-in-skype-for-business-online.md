---
title: Configurare la presenza in Skype for Business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
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
- O365P_OnlinePresenceDesc
description: 'Learn how to set up Skype for Business so you can see the availability of your co-workers. '
ms.openlocfilehash: f2b149a2b6277d356fe4478ee6de12ec6b078f48
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753451"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="960b5-103">Configurare la presenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="960b5-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="960b5-104">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="960b5-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="960b5-105">Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="960b5-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="960b5-106">Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario disporre del ruolo di amministratore di [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) come amministratore globale o amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="960b5-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="960b5-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="960b5-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="960b5-108">Per impostazione predefinita, chiunque possa comunicare con una delle persone della tua organizzazione utilizzando Skype for Business può anche vedere se quella persona è online.</span><span class="sxs-lookup"><span data-stu-id="960b5-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="960b5-109">Skype for Business mostra se una persona è disponibile online, in una riunione, offline o un altro indicatore.</span><span class="sxs-lookup"><span data-stu-id="960b5-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Esempio di stato online di una persona in Skype for Business.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="960b5-111">Come amministratore **[per](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** tutti gli utenti dell'azienda, puoi scegliere chi può vedere la loro presenza online in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="960b5-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="960b5-112">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="960b5-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="960b5-113">Accedi all'interfaccia di amministrazione > **interfaccia di amministrazione** Skype for  >  **Business.**</span><span class="sxs-lookup"><span data-stu-id="960b5-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="960b5-114">**Nell'interfaccia di amministrazione di Skype for Business,** scegli **Organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="960b5-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="960b5-115">In **modalità privacy presenza** selezionare una delle impostazioni seguenti e quindi scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="960b5-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="960b5-116">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="960b5-116">**Setting**</span></span>|<span data-ttu-id="960b5-117">**Chi può visualizzare la presenza di un utente**</span><span class="sxs-lookup"><span data-stu-id="960b5-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="960b5-118">**Visualizza automaticamente le informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="960b5-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="960b5-119">Qualsiasi utente Skype for Business della tua azienda che  non  è stato aggiunto all'elenco esterno o bloccato di una persona potrà vedere la sua presenza online.</span><span class="sxs-lookup"><span data-stu-id="960b5-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="960b5-120">**Visualizzare le informazioni sulla presenza solo per i contatti di un utente**</span><span class="sxs-lookup"><span data-stu-id="960b5-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="960b5-121">Tutti gli utenti nell'elenco Contatti di una persona che non sono stati aggiunti al proprio **elenco** esterno **o** bloccato.</span><span class="sxs-lookup"><span data-stu-id="960b5-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="960b5-122">I singoli utenti possono ignorare le impostazioni predefinite nella loro app Skype for Business: **Opzioni**  >  **strumenti**  >  **impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="960b5-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="960b5-123">Per informazioni su ciò che gli utenti possono modificare in Skype for Business, consulta questi articoli:</span><span class="sxs-lookup"><span data-stu-id="960b5-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="960b5-124">Controllare l'accesso alle informazioni sulla presenza in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="960b5-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="960b5-125">Impostare le opzioni di stato in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="960b5-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="960b5-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="960b5-126">Related topics</span></span>

[<span data-ttu-id="960b5-127">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="960b5-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="960b5-128">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="960b5-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


