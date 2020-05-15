---
title: Assegnare o modificare una posizione di emergenza per un utente
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite informazioni su come assegnare o modificare una posizione di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232477"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="2014c-103">Assegnare o modificare una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="2014c-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="2014c-104">Quando si configurano piani di chiamata, è necessario assegnare una posizione di emergenza a ogni numero di telefono o utente.</span><span class="sxs-lookup"><span data-stu-id="2014c-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="2014c-105">Nei paesi europei, la posizione di emergenza è associata al numero di telefono quando viene scaricata da Office 365 o quando si trasferisce un numero di telefono in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2014c-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="2014c-106">Negli Stati Uniti, la posizione di emergenza è associata al numero di telefono quando viene assegnata all'utente.</span><span class="sxs-lookup"><span data-stu-id="2014c-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="2014c-107">L'indirizzo di emergenza può essere modificato se l'utente a cui viene assegnato si sposta in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="2014c-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="2014c-108">Per altre informazioni su indirizzi e posizioni di emergenza, vedere [gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="2014c-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="2014c-109">Per informazioni su come ottenere un piano per le chiamate e sulla quantità di costi, vedere licenze per i [componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)per i team.</span><span class="sxs-lookup"><span data-stu-id="2014c-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="2014c-110">È possibile assegnare o modificare una posizione di emergenza per un utente nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2014c-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2014c-111">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2014c-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2014c-112">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **Voice**  >  **numeri di telefono**vocale.</span><span class="sxs-lookup"><span data-stu-id="2014c-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="2014c-113">Nella pagina **numeri di telefono** selezionare un numero utente nell'elenco e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="2014c-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="2014c-114">Nel riquadro **modifica** , in **posizione di emergenza**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2014c-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="2014c-115">Per assegnare una posizione di emergenza, cercare e selezionare una posizione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2014c-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="2014c-116">Per modificare la posizione di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente e quindi cercare e selezionare la posizione che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="2014c-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="2014c-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2014c-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="2014c-118">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="2014c-118">Using PowerShell</span></span>

<span data-ttu-id="2014c-119">Vedere [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="2014c-119">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="2014c-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2014c-120">Related topics</span></span>

- [<span data-ttu-id="2014c-121">Gestire le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="2014c-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="2014c-122">Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2014c-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="2014c-123">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2014c-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="2014c-124">Assegnare o modificare un luogo per una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="2014c-124">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="2014c-125">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="2014c-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="2014c-126">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="2014c-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="2014c-127">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="2014c-127">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
