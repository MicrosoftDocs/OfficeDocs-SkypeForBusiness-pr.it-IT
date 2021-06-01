---
title: Apportare modifiche alle impostazioni Riunione Skype broadcast per l'organizzazione
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
description: È possibile abilitare Riunione Skype broadcast e apportare modifiche alle impostazioni e ai criteri per tali riunioni.
ms.openlocfilehash: fae53601c858bf67db57352e18dbc9799243f996
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238648"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="6f224-103">Apportare modifiche alle impostazioni Riunione Skype broadcast per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6f224-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="6f224-104">L Microsoft Teams di amministrazione ha sostituito l'Skype for Business di amministrazione (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="6f224-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="6f224-105">Tutte le impostazioni per la Skype for Business sono ora disponibili nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6f224-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="6f224-106">È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire Skype for Business funzionalità di Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6f224-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="6f224-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="6f224-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="6f224-108">È possibile abilitare Riunione Skype broadcast e apportare modifiche alle impostazioni e ai criteri per tali riunioni.</span><span class="sxs-lookup"><span data-stu-id="6f224-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="6f224-109">**Abilitare Riunione Skype broadcast** Abilita Riunione Skype Broadcast.</span><span class="sxs-lookup"><span data-stu-id="6f224-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="6f224-110">Dopo aver abilitato Riunione Skype broadcast, è necessario configurare la [rete per](set-up-your-network-for-skype-meeting-broadcast.md)Riunione Skype Broadcast .</span><span class="sxs-lookup"><span data-stu-id="6f224-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="6f224-111">Eseguire questo passaggio se si vogliono tenere webinar e altre trasmissioni per utenti esterni all'azienda.</span><span class="sxs-lookup"><span data-stu-id="6f224-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="6f224-112">**Abilitare Riunione Skype Broadcast Preview per l'organizzazione** I Skype for Business dei clienti consentono di accedere in anticipo a nuovi prodotti e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6f224-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="6f224-113">In questo modo l'organizzazione offre un'anteprima delle novità in arrivo e l'opportunità di testare le nuove funzionalità del proprio ambiente e inviare feedback prima di rilasciare le build dei prodotti al pubblico generale.</span><span class="sxs-lookup"><span data-stu-id="6f224-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="6f224-114">Skype for Business anteprima</span><span class="sxs-lookup"><span data-stu-id="6f224-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="6f224-115">**Consentire agli organizzatori di pianificare riunioni anonime** In questo modo gli organizzatori possono creare eventi di trasmissione che consentono a chiunque all'esterno dell'organizzazione di partecipare senza l'obbligo di accedere.</span><span class="sxs-lookup"><span data-stu-id="6f224-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="6f224-116">**Consentire la registrazione di riunioni in broadcast** In questo modo tutte le riunioni devono essere registrate dal relatore o dall'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="6f224-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="6f224-117">**URL del supporto tecnico per i partecipanti** Immettere un collegamento per i partecipanti alla trasmissione della riunione da usare se hanno bisogno di aiuto per connettersi o partecipare a una riunione in broadcast.</span><span class="sxs-lookup"><span data-stu-id="6f224-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6f224-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6f224-118">Related topics</span></span>

[<span data-ttu-id="6f224-119">Configurare la rete per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="6f224-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
