---
title: Apportare modifiche alle impostazioni di Skype meeting broadcast per l'organizzazione
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
description: Puoi abilitare Skype meeting broadcast e modificare le impostazioni e i criteri per tali riunioni.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753411"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="665d9-103">Apportare modifiche alle impostazioni di Skype meeting broadcast per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="665d9-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="665d9-104">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="665d9-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="665d9-105">Tutte le impostazioni per la gestione di Skype for business si trovano ora nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="665d9-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="665d9-106">Per gestire le funzionalità di Skype for business nell'interfaccia di amministrazione di teams, è necessario essere assegnati al [ruolo di amministratore di Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) dell'amministratore globale o di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="665d9-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="665d9-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="665d9-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="665d9-108">Puoi abilitare Skype meeting broadcast e modificare le impostazioni e i criteri per tali riunioni.</span><span class="sxs-lookup"><span data-stu-id="665d9-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="665d9-109">**Abilitare Skype meeting broadcast** Abilita Skype meeting broadcast.</span><span class="sxs-lookup"><span data-stu-id="665d9-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="665d9-110">Dopo aver abilitato Skype meeting broadcast, è necessario [configurare la rete per Skype meeting broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="665d9-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="665d9-111">Eseguire questa procedura se si vogliono tenere webinar e altre trasmissioni per gli utenti esterni all'azienda.</span><span class="sxs-lookup"><span data-stu-id="665d9-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="665d9-112">**Abilitare le caratteristiche di Skype meeting broadcast Preview per l'organizzazione** I programmi clienti Skype for Business ti permettono di accedere in anticipo a nuovi prodotti e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="665d9-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="665d9-113">In questo modo l'organizzazione offre una sbirciatina in anteprima sulle novità e l'opportunità di testare le nuove funzionalità nel proprio ambiente e fornire commenti e suggerimenti prima di rilasciare le build di prodotto al pubblico in generale.</span><span class="sxs-lookup"><span data-stu-id="665d9-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="665d9-114">Anteprima di Skype for business</span><span class="sxs-lookup"><span data-stu-id="665d9-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="665d9-115">**Consentire agli organizzatori di pianificare riunioni anonime** Questo consente agli organizzatori di creare eventi broadcast che consentano a tutti gli utenti esterni all'organizzazione di partecipare senza un requisito per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="665d9-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="665d9-116">**Consentire la registrazione delle riunioni broadcast** Ciò consente di registrare le riunioni da parte del relatore o dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="665d9-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="665d9-117">**URL di supporto helpdesk per i partecipanti** Immettere un collegamento per i partecipanti alla riunione broadcast da usare se hanno bisogno di assistenza per la connessione o la partecipazione a una riunione broadcast.</span><span class="sxs-lookup"><span data-stu-id="665d9-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="665d9-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="665d9-118">Related topics</span></span>

[<span data-ttu-id="665d9-119">Configurare la rete per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="665d9-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
