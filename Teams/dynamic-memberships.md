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
description: Scopri come Microsoft Teams i team associati a Microsoft 365 gruppi usando l'appartenenza dinamica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856325"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="93cf9-103">Panoramica sull'appartenenza dinamica per i team</span><span class="sxs-lookup"><span data-stu-id="93cf9-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="93cf9-104">Microsoft Teams supporta i team associati a Microsoft 365 gruppi usando *l'appartenenza dinamica.*</span><span class="sxs-lookup"><span data-stu-id="93cf9-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="93cf9-105">L'appartenenza dinamica consente di definire l'appartenenza di un team in base a una o più regole che controllano la presenza di determinati attributi utente in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="93cf9-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="93cf9-106">Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi degli utenti cambiano o gli utenti si uniscono e lasciano il tenant.</span><span class="sxs-lookup"><span data-stu-id="93cf9-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="93cf9-107">Con l'appartenenza dinamica è possibile configurare i team per determinate coorti di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93cf9-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="93cf9-108">Gli scenari possibili includono:</span><span class="sxs-lookup"><span data-stu-id="93cf9-108">Possible scenarios include:</span></span>
- <span data-ttu-id="93cf9-109">Un ospedale può creare team distinti per infermieri, medici e medici per trasmettere le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="93cf9-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="93cf9-110">Questo è particolarmente importante se l'ospedale si basa sui dipendenti temporanei.</span><span class="sxs-lookup"><span data-stu-id="93cf9-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="93cf9-111">Un'università può creare un team per tutti i docenti all'interno di un determinato istituto di istruzione, incluso un istituto di istruzione aggiunto che cambia di frequente.</span><span class="sxs-lookup"><span data-stu-id="93cf9-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="93cf9-112">Una compagnia aerea vuole creare un team per ogni volo (ad esempio un non-stop di martedì pomeriggio da Chicago ad Atlanta) e assegnare o rimuovere automaticamente un membro del personale di volo che cambia spesso in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="93cf9-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="93cf9-113">Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set specifico di criteri, invece di gestire manualmente l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="93cf9-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="93cf9-114">Per eseguire questa operazione, è necessario che le licenze di Azure AD Premium P1 e l'appartenenza al team possano essere assegnate da un amministratore [tenant](/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure AD di qualsiasi utente, purché si abbia un tenant e un account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="93cf9-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="93cf9-115">Microsoft Teams può richiedere da pochi minuti a un massimo di 2 ore per riflettere le modifiche dinamiche dell'appartenenza dopo che sono state applicate nel gruppo Microsoft 365 per un team.</span><span class="sxs-lookup"><span data-stu-id="93cf9-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="93cf9-116">Quando si usano team con gruppi dinamici:</span><span class="sxs-lookup"><span data-stu-id="93cf9-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="93cf9-117">Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="93cf9-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="93cf9-118">I proprietari non potranno aggiungere o rimuovere utenti come membri del team, perché i membri sono definiti da regole di gruppo dinamiche.</span><span class="sxs-lookup"><span data-stu-id="93cf9-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="93cf9-119">Teams client non consentono la gestione dei membri per il team.</span><span class="sxs-lookup"><span data-stu-id="93cf9-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="93cf9-120">Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare richieste di partecipazione e lasciare il team sono tutte nascoste.</span><span class="sxs-lookup"><span data-stu-id="93cf9-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="93cf9-121">Per creare un team che usa l'appartenenza dinamica, iniziare [creando](/azure/active-directory/users-groups-roles/groups-create-rule) un gruppo Microsoft 365 e quindi [creare un team da tale gruppo.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="93cf9-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="93cf9-122">È possibile modificare un team esistente in modo che abbia un'appartenenza dinamica.</span><span class="sxs-lookup"><span data-stu-id="93cf9-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="93cf9-123">Per informazioni, vedere Modificare l'appartenenza a gruppi [statici in Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="93cf9-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="93cf9-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="93cf9-124">Related topics</span></span>

[<span data-ttu-id="93cf9-125">Limiti e specifiche per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="93cf9-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="93cf9-126">Regole di appartenenza dinamiche per i gruppi in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="93cf9-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
