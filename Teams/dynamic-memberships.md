---
title: Panoramica dell'appartenenza dinamica per i team
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'appartenenza a un team dinamico basato su AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f48309b5816c61668d240087c1f2815fc94ebe4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184342"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="0f63d-103">Panoramica dell'appartenenza dinamica per i team</span><span class="sxs-lookup"><span data-stu-id="0f63d-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="0f63d-104">Microsoft teams supporta i team associati ai gruppi di Office 365 tramite *l'appartenenza dinamica*.</span><span class="sxs-lookup"><span data-stu-id="0f63d-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="0f63d-105">L'appartenenza dinamica consente di definire l'appartenenza a un team da una o più regole che controllano alcuni attributi utente in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0f63d-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="0f63d-106">Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi dell'utente cambiano o gli utenti partecipano e lasciano il tenant.</span><span class="sxs-lookup"><span data-stu-id="0f63d-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="0f63d-107">Con l'appartenenza dinamica puoi configurare Team per alcuni coorti di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0f63d-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="0f63d-108">Possibili scenari includono:</span><span class="sxs-lookup"><span data-stu-id="0f63d-108">Possible scenarios include:</span></span>
- <span data-ttu-id="0f63d-109">Un ospedale può creare team distinti per infermieri, medici e chirurghi per trasmettere comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="0f63d-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="0f63d-110">Questo aspetto è particolarmente importante se l'ospedale si basa su dipendenti temporanei.</span><span class="sxs-lookup"><span data-stu-id="0f63d-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="0f63d-111">Un'università può creare un team per tutti i docenti all'interno di un determinato collegio, tra cui una facoltà aggiuntiva che cambia spesso.</span><span class="sxs-lookup"><span data-stu-id="0f63d-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="0f63d-112">Una compagnia aerea vuole creare un team per ogni volo (ad esempio un martedì pomeriggio non-stop da Chicago ad Atlanta) e avere un equipaggio di volo che cambia spesso automaticamente assegnato o rimosso in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0f63d-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="0f63d-113">Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set di criteri specifico, invece di gestire manualmente l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="0f63d-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="0f63d-114">In questo modo, le licenze Azure AD Premium P1 e l'appartenenza al team possono essere [assegnate da un amministratore del tenant](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure ad di qualsiasi utente, purché si disponga di un tenant e di un account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0f63d-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="0f63d-115">Microsoft teams può richiedere in qualsiasi momento da pochi minuti a un massimo di 2 ore per riflettere le modifiche dinamiche dell'appartenenza dopo avere avuto effetto nel gruppo Office 365 per un team.</span><span class="sxs-lookup"><span data-stu-id="0f63d-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="0f63d-116">Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="0f63d-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="0f63d-117">Vedere [limiti e specifiche per Microsoft teams](limits-specifications-teams.md) per i limiti correnti sulle dimensioni del team e del canale.</span><span class="sxs-lookup"><span data-stu-id="0f63d-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="0f63d-118">I proprietari non saranno in grado di aggiungere o rimuovere utenti come membri del team, poiché i membri sono definiti da regole di gruppo dinamiche.</span><span class="sxs-lookup"><span data-stu-id="0f63d-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="0f63d-119">I membri non saranno in grado di abbandonare i team da gruppi dinamici.</span><span class="sxs-lookup"><span data-stu-id="0f63d-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="0f63d-120">Creazione e gestione di un gruppo di Office 365 con appartenenza dinamica</span><span class="sxs-lookup"><span data-stu-id="0f63d-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="0f63d-121">Durante l'accesso come amministratore del tenant, seguire le istruzioni in [creare un gruppo dinamico e verificare lo stato](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="0f63d-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="0f63d-122">Se necessario, fare riferimento alle [regole di appartenenza dinamiche per i gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="0f63d-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="0f63d-123">Creare un nuovo team con il gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="0f63d-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="0f63d-124">Ora consente di rendere effettive le modifiche apportate all'appartenenza e creare un nuovo team come descritto in [migliorare i gruppi di Office 365 esistenti con Microsoft teams](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0f63d-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="0f63d-125">Applicare l'appartenenza dinamica a un team esistente</span><span class="sxs-lookup"><span data-stu-id="0f63d-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="0f63d-126">Puoi anche prendere un team esistente e modificarlo in modo che abbia un abbonamento dinamico, come descritto in [modificare l'appartenenza a gruppi statici in Dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="0f63d-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="0f63d-127">Modifiche al comportamento del client</span><span class="sxs-lookup"><span data-stu-id="0f63d-127">Changes in client behavior</span></span>

<span data-ttu-id="0f63d-128">Una volta abilitata l'appartenenza dinamica per un team, i client di teams non consentiranno più la gestione dei membri per il team.</span><span class="sxs-lookup"><span data-stu-id="0f63d-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="0f63d-129">Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare le richieste di join e uscire dal team sono tutte nascoste.</span><span class="sxs-lookup"><span data-stu-id="0f63d-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
