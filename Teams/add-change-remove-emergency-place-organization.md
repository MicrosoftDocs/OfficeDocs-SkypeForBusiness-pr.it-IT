---
title: Aggiungere, modificare, rimuovere luoghi per le posizioni di emergenza
author: cichur
ms.author: v-cichur
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione nell'Microsoft Teams di amministrazione.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121504"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="e7473-103">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e7473-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="e7473-104">A seconda del numero di posizioni fisiche dell'organizzazione, è possibile aggiungere luoghi per edifici, piani e uffici per creare una posizione di emergenza più specifica.</span><span class="sxs-lookup"><span data-stu-id="e7473-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="e7473-105">Per [altre informazioni, vedere](what-are-emergency-locations-addresses-and-call-routing.md) Gestire le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e7473-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="e7473-106">Per informazioni su come ottenere un piano per chiamate e sul costo, vedere Teams [licenze per i componenti aggiuntivi.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e7473-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="e7473-107">È possibile gestire le posizioni di emergenza per l'organizzazione nell'Microsoft Teams di amministrazione o usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7473-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="e7473-108">Aggiungere un luogo a un luogo per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="e7473-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7473-109">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7473-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e7473-110">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**</span><span class="sxs-lookup"><span data-stu-id="e7473-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="e7473-111">Nell'elenco fare clic sul nome della posizione per cui si vuole aggiungere una posizione.</span><span class="sxs-lookup"><span data-stu-id="e7473-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="e7473-112">Nella scheda **Posizioni** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e7473-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="e7473-113">Immettere un nome di luogo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="e7473-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7473-114">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7473-114">Using PowerShell</span></span>

<span data-ttu-id="e7473-115">Vedere [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="e7473-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="e7473-116">Cambiare un luogo per un luogo per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="e7473-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7473-117">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7473-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e7473-118">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**</span><span class="sxs-lookup"><span data-stu-id="e7473-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="e7473-119">Nell'elenco fare clic sul nome della posizione di cui si vuole modificare una posizione.</span><span class="sxs-lookup"><span data-stu-id="e7473-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="e7473-120">Nella scheda **Posizioni** selezionare la posizione da modificare e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e7473-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="e7473-121">Aggiornare le informazioni sulla posizione e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="e7473-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7473-122">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7473-122">Using PowerShell</span></span>

<span data-ttu-id="e7473-123">Vedere [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="e7473-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="e7473-124">Rimuovere un luogo da un luogo per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="e7473-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7473-125">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7473-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e7473-126">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**</span><span class="sxs-lookup"><span data-stu-id="e7473-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="e7473-127">Nell'elenco fare clic sul nome della posizione di cui si vuole rimuovere una posizione.</span><span class="sxs-lookup"><span data-stu-id="e7473-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="e7473-128">Nella scheda **Posizioni** selezionare la posizione da rimuovere e quindi fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="e7473-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7473-129">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7473-129">Using PowerShell</span></span>

<span data-ttu-id="e7473-130">Vedere [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="e7473-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e7473-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e7473-131">Related topics</span></span>

- [<span data-ttu-id="e7473-132">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e7473-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="e7473-133">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="e7473-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="e7473-134">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="e7473-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)