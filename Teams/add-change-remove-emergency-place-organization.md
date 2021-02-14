---
title: Aggiungere, modificare, rimuovere posizioni per le posizioni per gli interventi di emergenza
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806276"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="751e6-103">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="751e6-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="751e6-104">A seconda del numero di posizioni fisiche presenti nell'organizzazione, puoi aggiungere posizioni per edifici, piani e uffici per creare una posizione per gli interventi di emergenza più specifica.</span><span class="sxs-lookup"><span data-stu-id="751e6-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="751e6-105">Per [ulteriori informazioni, consulta Gestire](what-are-emergency-locations-addresses-and-call-routing.md) le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="751e6-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="751e6-106">Per informazioni su come ottenere un piano per chiamate e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="751e6-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="751e6-107">È possibile gestire le posizioni per gli interventi di emergenza dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="751e6-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="751e6-108">Aggiungere una posizione a una posizione per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="751e6-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="751e6-109">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="751e6-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="751e6-110">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**</span><span class="sxs-lookup"><span data-stu-id="751e6-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="751e6-111">Nell'elenco fare clic sul nome della posizione per cui si vuole aggiungere una posizione.</span><span class="sxs-lookup"><span data-stu-id="751e6-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="751e6-112">Nella scheda **Posizioni** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="751e6-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="751e6-113">Immettere un nome per il luogo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="751e6-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="751e6-114">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="751e6-114">Using PowerShell</span></span>

<span data-ttu-id="751e6-115">Vedi [New-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="751e6-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="751e6-116">Modificare un luogo per una posizione per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="751e6-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="751e6-117">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="751e6-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="751e6-118">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**</span><span class="sxs-lookup"><span data-stu-id="751e6-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="751e6-119">Nell'elenco fare clic sul nome della posizione di cui si vuole modificare una posizione.</span><span class="sxs-lookup"><span data-stu-id="751e6-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="751e6-120">Nella scheda **Posizioni** selezionare la posizione da modificare e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="751e6-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="751e6-121">Aggiornare le informazioni sulla posizione e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="751e6-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="751e6-122">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="751e6-122">Using PowerShell</span></span>

<span data-ttu-id="751e6-123">Vedi [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="751e6-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="751e6-124">Rimuovere una posizione da una posizione per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="751e6-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="751e6-125">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="751e6-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="751e6-126">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**</span><span class="sxs-lookup"><span data-stu-id="751e6-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="751e6-127">Nell'elenco fare clic sul nome della posizione da cui si vuole rimuovere una posizione.</span><span class="sxs-lookup"><span data-stu-id="751e6-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="751e6-128">Nella scheda **Posizioni** selezionare la posizione da rimuovere e quindi fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="751e6-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="751e6-129">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="751e6-129">Using PowerShell</span></span>

<span data-ttu-id="751e6-130">Vedi [Remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="751e6-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="751e6-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="751e6-131">Related topics</span></span>

- [<span data-ttu-id="751e6-132">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="751e6-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="751e6-133">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="751e6-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="751e6-134">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="751e6-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
