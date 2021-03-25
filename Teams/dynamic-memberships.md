---
title: Panoramica sull'appartenenza dinamica per i team
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Scopri come Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 usando l'appartenenza dinamica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120768"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="428f1-103">Panoramica sull'appartenenza dinamica per i team</span><span class="sxs-lookup"><span data-stu-id="428f1-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="428f1-104">Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 usando *l'appartenenza dinamica.*</span><span class="sxs-lookup"><span data-stu-id="428f1-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="428f1-105">L'appartenenza dinamica consente di definire l'appartenenza di un team in base a una o più regole che controllano la presenza di determinati attributi utente in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="428f1-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="428f1-106">Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi degli utenti cambiano o gli utenti si uniscono e lasciano il tenant.</span><span class="sxs-lookup"><span data-stu-id="428f1-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="428f1-107">Con l'appartenenza dinamica è possibile configurare i team per determinate coorti di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="428f1-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="428f1-108">Gli scenari possibili includono:</span><span class="sxs-lookup"><span data-stu-id="428f1-108">Possible scenarios include:</span></span>
- <span data-ttu-id="428f1-109">Un ospedale può creare team distinti per infermieri, medici e medici per trasmettere le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="428f1-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="428f1-110">Questo è particolarmente importante se l'ospedale si basa sui dipendenti temporanei.</span><span class="sxs-lookup"><span data-stu-id="428f1-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="428f1-111">Un'università può creare un team per tutti i docenti all'interno di un determinato istituto di istruzione, incluso un istituto di istruzione aggiunto che cambia di frequente.</span><span class="sxs-lookup"><span data-stu-id="428f1-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="428f1-112">Una compagnia aerea vuole creare un team per ogni volo (ad esempio un non-stop di martedì pomeriggio da Chicago ad Atlanta) e assegnare o rimuovere automaticamente un membro del personale di volo che cambia spesso in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="428f1-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="428f1-113">Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set specifico di criteri, invece di gestire manualmente l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="428f1-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="428f1-114">Per eseguire questa operazione, è necessario che le licenze P1 Premium di Azure AD e l'appartenenza al team possano essere assegnate da un amministratore [tenant](/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure AD di qualsiasi utente, purché si abbia un tenant e un account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="428f1-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="428f1-115">Microsoft Teams può richiedere da qualche minuto a un massimo di 2 ore per riflettere le modifiche dinamiche dell'appartenenza dopo che sono state applicate al gruppo Microsoft 365 per un team.</span><span class="sxs-lookup"><span data-stu-id="428f1-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="428f1-116">Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="428f1-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="428f1-117">Vedere [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md) per i limiti correnti per le dimensioni del team e del canale.</span><span class="sxs-lookup"><span data-stu-id="428f1-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="428f1-118">I proprietari non potranno aggiungere o rimuovere utenti come membri del team, perché i membri sono definiti da regole di gruppo dinamiche.</span><span class="sxs-lookup"><span data-stu-id="428f1-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="428f1-119">I membri non potranno lasciare i team supportati da gruppi dinamici.</span><span class="sxs-lookup"><span data-stu-id="428f1-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="428f1-120">Creazione e gestione di un gruppo di Microsoft 365 con appartenenza dinamica</span><span class="sxs-lookup"><span data-stu-id="428f1-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="428f1-121">Dopo l'accesso come amministratore del tenant, seguire le istruzioni in [Creare un gruppo dinamico e controllare lo stato.](/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="428f1-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="428f1-122">Se necessario, vedere [Regole di appartenenza dinamiche per i gruppi in Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="428f1-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="428f1-123">Creare un nuovo team con il gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="428f1-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="428f1-124">È ora possibile concedere il tempo necessario per l'applicazione delle modifiche all'appartenenza e creare un nuovo team come descritto in Creare un [team da un gruppo esistente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="428f1-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="428f1-125">Applicare l'appartenenza dinamica a un team esistente</span><span class="sxs-lookup"><span data-stu-id="428f1-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="428f1-126">È anche possibile usare un team esistente e cambiarlo in modo che abbia un'appartenenza dinamica, come descritto in Cambiare l'appartenenza statica ai gruppi [in dinamica in Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="428f1-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="428f1-127">Modifiche al comportamento del client</span><span class="sxs-lookup"><span data-stu-id="428f1-127">Changes in client behavior</span></span>

<span data-ttu-id="428f1-128">Una volta abilitata l'appartenenza dinamica per un team, i client di Teams non consentiranno più la gestione dei membri per il team.</span><span class="sxs-lookup"><span data-stu-id="428f1-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="428f1-129">Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare richieste di partecipazione e lasciare il team sono tutte nascoste.</span><span class="sxs-lookup"><span data-stu-id="428f1-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>