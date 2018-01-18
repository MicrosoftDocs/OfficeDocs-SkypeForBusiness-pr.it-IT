---
title: Utilizzo degli ID dinamici audioconferenze all'interno dell'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Il servizio di conferenza Audio viene viene aggiornato per fornire ogni Skype per Business e Microsoft Teams riunione con gli ID conferenza diversi. ID conferenza dinamici sono un miglioramento significativo tramite conferenza statico ID, in quanto forniscono:'
ms.openlocfilehash: 0838014e8a88d5e27b6bd84838ea105b9f75025a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="21f67-104">Utilizzo degli ID dinamici audioconferenze all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="21f67-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="21f67-105">Il servizio di conferenza Audio viene viene aggiornato per fornire ogni Skype per Business e Microsoft Teams riunione con gli ID conferenza diversi.</span><span class="sxs-lookup"><span data-stu-id="21f67-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="21f67-106">ID conferenza dinamici sono un miglioramento significativo tramite conferenza statico ID, in quanto forniscono:</span><span class="sxs-lookup"><span data-stu-id="21f67-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="21f67-107">**Protezione avanzata** La conferenza ID sono univoci per ogni Skype per riunione Business o Microsoft Teams e vengono generati quando viene programmato in base alla riunione.</span><span class="sxs-lookup"><span data-stu-id="21f67-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="21f67-108">**Una migliore esperienza per le riunioni vicine l'una all'altra** Alle riunioni di un singolo organizzatore sono trasmesse informazioni specifiche sul numero da chiamare che impediscono ai partecipanti telefonici di una riunione di essere confusi con i partecipanti di un'altra quando sono pianificate una vicino all'altra.</span><span class="sxs-lookup"><span data-stu-id="21f67-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="21f67-109">**Una transizione fluida** Quando la tua organizzazione è abilitata agli ID conferenza dinamici, tutte le riunioni che sono già state pianificate nella tua organizzazione con ID conferenza statici continueranno ad essere attive.</span><span class="sxs-lookup"><span data-stu-id="21f67-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="21f67-110">ID dinamici sono disponibili solo per gli utenti abilitati per * * Audio Conferencing * * in modo che Microsoft impostato come i provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="21f67-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="21f67-111">È possibile [Assegnare Microsoft come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md) per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="21f67-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="21f67-112">Quali modifiche verranno visualizzato agli utenti nell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="21f67-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="21f67-113">Dopo l'ID conferenza dinamici sono stati abilitati per l'organizzazione, qualsiasi nuova Skype per Business o Microsoft Teams riunioni che è pianificato per gli utenti nell'organizzazione abilitati per conferenze Audio avrà gli ID che sarà diversa dalla conferenza la ID conferenza statica aveva prima.</span><span class="sxs-lookup"><span data-stu-id="21f67-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="21f67-114">Gli organizzatori con statica ID conferenza prima necessario ricordare gli utenti di partecipare alle riunioni che ora devono utilizzare un nuovo ID conferenza nell'invito della riunione prima di consentire loro di partecipare.</span><span class="sxs-lookup"><span data-stu-id="21f67-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21f67-115">Riunioni pianificate da un utente con gli ID conferenza statico prima che l'organizzazione è stato abilitato per conferenza dinamico che ID continuerà a disporre gli ID conferenza statico, in modo che continuino a pianificare riunioni senza alcun impatto.</span><span class="sxs-lookup"><span data-stu-id="21f67-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="21f67-116">Negli esempi seguenti la nuova esperienza per due Skype per le riunioni aziendali che sono stati organizzate dall'utente stesso, ma entrambi ora avranno due ID conferenza diversi:</span><span class="sxs-lookup"><span data-stu-id="21f67-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="21f67-117">La **riunione n. 1** è stata pianificata dalle 09.00 alle 10.00 e ha 93907123 come proprio ID conferenza:</span><span class="sxs-lookup"><span data-stu-id="21f67-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="21f67-119">La **riunione n. 2** è stata pianificata dallo stesso utente dalle 10.00 alle 11.00 e ha 16353789 come proprio ID conferenza:</span><span class="sxs-lookup"><span data-stu-id="21f67-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="21f67-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="21f67-121">Related topics</span></span>

- [<span data-ttu-id="21f67-122">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="21f67-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- <span data-ttu-id="21f67-123">I servizi di conferenza telefonica con accesso esterno, anche noti con il nome di Servizi di conferenza PSTN, non sono disponibili per tutte le organizzazioni Office 365.</span><span class="sxs-lookup"><span data-stu-id="21f67-123">[Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing.md)</span></span>
    
- <span data-ttu-id="21f67-124">Per ulteriori informazioni, consulta [Servizi di conferenza telefonica con accesso esterno in Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="21f67-124">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
    

