---
title: Apportare modifiche alle impostazioni di Skype Meeting Broadcast per l'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
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
- SMB
- ms.lync.lac.BroadcastMeetings
description: È possibile abilitare Skype Meeting Broadcast e apportare modifiche alle impostazioni e ai criteri per tali riunioni.
ms.openlocfilehash: 75b1894f486d6448662c459b0d77d4f5d3057a2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106552"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="ee7a7-103">Apportare modifiche alle impostazioni di Skype Meeting Broadcast per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ee7a7-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee7a7-104">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="ee7a7-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="ee7a7-105">Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="ee7a7-106">Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) dell'amministratore globale o dell'amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="ee7a7-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="ee7a7-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="ee7a7-108">È possibile abilitare Skype Meeting Broadcast e apportare modifiche alle impostazioni e ai criteri per tali riunioni.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="ee7a7-109">**Abilitare Skype Meeting Broadcast** Abilita Skype Meeting Broadcast.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="ee7a7-110">Dopo aver abilitato Skype Meeting Broadcast, devi [configurare la rete per Skype Meeting Broadcast.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="ee7a7-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="ee7a7-111">Eseguire questo passaggio se si vogliono tenere webinar e altre trasmissioni per utenti esterni all'azienda.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="ee7a7-112">**Abilitare le funzionalità Di anteprima di Skype Meeting Broadcast per la mia organizzazione** I programmi per i clienti Skype for Business offrono accesso anticipato a nuovi prodotti e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="ee7a7-113">In questo modo l'organizzazione offre un'anteprima delle novità in arrivo e l'opportunità di testare le nuove funzionalità del proprio ambiente e inviare feedback prima di rilasciare le build dei prodotti al pubblico generale.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="ee7a7-114">Anteprima di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ee7a7-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="ee7a7-115">**Consentire agli organizzatori di pianificare riunioni anonime** In questo modo gli organizzatori possono creare eventi di trasmissione che consentono a chiunque all'esterno dell'organizzazione di partecipare senza l'obbligo di accedere.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="ee7a7-116">**Consentire la registrazione di riunioni in broadcast** In questo modo tutte le riunioni devono essere registrate dal relatore o dall'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="ee7a7-117">**URL del supporto tecnico per i partecipanti** Immettere un collegamento per i partecipanti alla trasmissione della riunione da usare se hanno bisogno di aiuto per connettersi o partecipare a una riunione in broadcast.</span><span class="sxs-lookup"><span data-stu-id="ee7a7-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ee7a7-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ee7a7-118">Related topics</span></span>

[<span data-ttu-id="ee7a7-119">Configurare la rete per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="ee7a7-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
