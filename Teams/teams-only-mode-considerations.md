---
title: Considerazioni sulla modalità Solo teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: L'amministratore può imparare a preparare l'ambiente per un aggiornamento alla modalità Solo di Microsoft Teams nell'interfaccia di amministrazione di Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460996"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="4669c-103">Considerazioni sulla modalità Solo teams</span><span class="sxs-lookup"><span data-stu-id="4669c-103">Teams Only mode considerations</span></span>

<span data-ttu-id="4669c-104">Gli amministratori delle organizzazioni Microsoft 365 o Office 365 possono passare alla modalità Solo Teams per singoli utenti o per l'intero tenant.</span><span class="sxs-lookup"><span data-stu-id="4669c-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

<span data-ttu-id="4669c-105">L'aggiornamento alla modalità Solo teams offre agli utenti tutti i vantaggi di Microsoft Teams, l'hub per il lavoro in team in Microsoft 365 o Office 365, tramite un'unica esperienza client.</span><span class="sxs-lookup"><span data-stu-id="4669c-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="4669c-106">Gli utenti in modalità Solo teams riceveranno tutte le chiamate e le chat in Teams, indipendentemente dal fatto che il mittente utilizzi Skype for Business o Teams e trarre vantaggio dal supporto di interoperabilità e federazione.</span><span class="sxs-lookup"><span data-stu-id="4669c-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="4669c-107">Anche se migliaia di clienti hanno eseguito correttamente l'aggiornamento a Microsoft Teams, ci sono considerazioni che possono influire sulla sequenza temporale dell'aggiornamento e sull'esperienza utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4669c-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="4669c-108">Per un'esperienza utente ottimale, verificare che Teams soddisfi i requisiti interni di collaborazione e comunicazione, assicurarsi che la rete sia pronta per supportare Teams e implementare il piano di preparazione degli utenti prima di aggiornarli a Teams.</span><span class="sxs-lookup"><span data-stu-id="4669c-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4669c-109">Se si sta appena iniziando la pianificazione degli aggiornamenti, consultare la Guida introduttiva alla guida all'aggiornamento [a Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="4669c-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="4669c-110">**Considerazioni sulla** coesistenza: le organizzazioni che già usano Skype for Business online e/o Skype for Business Server possono introdurre Teams nel proprio ambiente con un ritmo che soddisfa le loro esigenze.</span><span class="sxs-lookup"><span data-stu-id="4669c-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="4669c-111">Le organizzazioni possono implementare in modo incrementale Teams nel set desiderato di utenti, se necessario, e gli utenti che usano Teams possono comunicare con gli utenti che usano Skype for Business e viceversa.</span><span class="sxs-lookup"><span data-stu-id="4669c-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="4669c-112">Per gestire questa esperienza, gli amministratori usano le modalità di coesistenza, che definiscono l'esperienza client dell'utente finale, il comportamento di instradamento delle chat e delle chiamate in arrivo e se le nuove riunioni sono pianificate in Teams o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4669c-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="4669c-113">Gli utenti possono eseguire la federazione con utenti di altre organizzazioni se l'utente viene aggiornato a **Solo Teams;** tuttavia, l'esperienza migliore viene fornita quando entrambi gli utenti usano Teams.</span><span class="sxs-lookup"><span data-stu-id="4669c-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="4669c-114">Gli utenti aggiornati a Teams possono comunque partecipare alle riunioni Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4669c-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4669c-115">Per informazioni più dettagliate sulla coesistenza, vedere Informazioni sulla coesistenza e l'interoperabilità di [Microsoft Teams e Skype for Business.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="4669c-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="4669c-116">Per ulteriori informazioni su Teams e Skype (Consumer), consulta [Teams e l'interoperabilità di Skype.](teams-skype-interop.md)</span><span class="sxs-lookup"><span data-stu-id="4669c-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="4669c-117">**Considerazioni specifiche per gli** utenti: alcuni scenari di utenti sono ancora in evoluzione e gli amministratori possono decidere di posticipare temporaneamente l'aggiornamento di alcuni utenti durante l'aggiornamento di altri utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4669c-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="4669c-118">In particolare, stiamo ancora lavorando agli scenari di indirizzamento per gli utenti il cui dispositivo principale è basato su VDI.</span><span class="sxs-lookup"><span data-stu-id="4669c-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="4669c-119">Per gli annunci di siti, monitorare la roadmap [di Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="4669c-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="4669c-120">Prima di passare alla modalità Solo teams, devi sostituire o aggiornare i dispositivi che non supportano Teams.</span><span class="sxs-lookup"><span data-stu-id="4669c-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4669c-121">**Ricorda:** il passaggio a Teams non è solo una migrazione tecnica.</span><span class="sxs-lookup"><span data-stu-id="4669c-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="4669c-122">Un aggiornamento riuscito valuta sia la conformità tecnica che la conformità degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="4669c-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="4669c-123">Consulta le nostre indicazioni per l'aggiornamento da Skype for Business [a](upgrade-framework.md) Teams per ulteriori informazioni sulla pianificazione di un aggiornamento a Teams.</span><span class="sxs-lookup"><span data-stu-id="4669c-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
