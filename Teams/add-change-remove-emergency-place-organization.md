---
title: Aggiungere, modificare, rimuovere posizioni per i percorsi di emergenza
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per un luogo di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232497"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="18c91-103">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="18c91-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="18c91-104">A seconda del numero di posizioni fisiche nell'organizzazione, è possibile aggiungere posizioni per edifici, pavimenti e uffici per creare un percorso di emergenza più specifico.</span><span class="sxs-lookup"><span data-stu-id="18c91-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="18c91-105">Per altre informazioni, vedere [gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) .</span><span class="sxs-lookup"><span data-stu-id="18c91-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="18c91-106">Per informazioni su come ottenere un piano per le chiamate e sulla quantità di costi, vedere licenze per i [componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)per i team.</span><span class="sxs-lookup"><span data-stu-id="18c91-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="18c91-107">È possibile gestire le posizioni di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18c91-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="18c91-108">Aggiungere una posizione in un luogo di emergenza</span><span class="sxs-lookup"><span data-stu-id="18c91-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18c91-109">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18c91-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18c91-110">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="18c91-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="18c91-111">Nell'elenco fare clic sul nome della posizione per la quale si vuole aggiungere un luogo.</span><span class="sxs-lookup"><span data-stu-id="18c91-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="18c91-112">Nella scheda **posizioni** fare clic su **Aggiungi posizione**.</span><span class="sxs-lookup"><span data-stu-id="18c91-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="18c91-113">Immettere un nome di posizione e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="18c91-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="18c91-114">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="18c91-114">Using PowerShell</span></span>

<span data-ttu-id="18c91-115">Vedere [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="18c91-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="18c91-116">Modificare una posizione per un percorso di emergenza</span><span class="sxs-lookup"><span data-stu-id="18c91-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18c91-117">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18c91-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18c91-118">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="18c91-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="18c91-119">Nell'elenco fare clic sul nome della posizione per la quale si desidera modificare un punto.</span><span class="sxs-lookup"><span data-stu-id="18c91-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="18c91-120">Nella scheda **posizioni** selezionare la posizione che si vuole modificare e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="18c91-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="18c91-121">Aggiornare le informazioni sulla posizione e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="18c91-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="18c91-122">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="18c91-122">Using PowerShell</span></span>

<span data-ttu-id="18c91-123">Vedere [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="18c91-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="18c91-124">Rimuovere una posizione da un percorso di emergenza</span><span class="sxs-lookup"><span data-stu-id="18c91-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18c91-125">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18c91-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18c91-126">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="18c91-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="18c91-127">Nell'elenco fare clic sul nome della posizione per la quale si desidera rimuovere un luogo.</span><span class="sxs-lookup"><span data-stu-id="18c91-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="18c91-128">Nella scheda **posizioni** selezionare la posizione che si desidera rimuovere e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="18c91-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="18c91-129">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="18c91-129">Using PowerShell</span></span>

<span data-ttu-id="18c91-130">Vedere [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="18c91-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="18c91-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="18c91-131">Related topics</span></span>

- [<span data-ttu-id="18c91-132">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="18c91-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="18c91-133">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="18c91-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="18c91-134">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="18c91-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
