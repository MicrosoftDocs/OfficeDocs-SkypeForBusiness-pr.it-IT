---
title: Aggiungere, modificare, rimuovere posizioni di emergenza
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
description: "Informazioni su come aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams. "
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799946"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="86707-103">Aggiungere, modificare o rimuovere un percorso per l'organizzazione di emergenza</span><span class="sxs-lookup"><span data-stu-id="86707-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="86707-104">Una posizione di emergenza deve essere associata a un numero di telefono, ma quando ciò accade può variare tra paesi e aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="86707-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="86707-105">Ad esempio, negli Stati Uniti è necessario associare un percorso di emergenza quando si assegna il numero di telefono all'utente.</span><span class="sxs-lookup"><span data-stu-id="86707-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="86707-106">Nel Regno Unito è necessario associare un percorso di emergenza al numero di telefono quando si ottengono i numeri di telefono da Microsoft 365 o Office 365 o si trasferiscono i numeri di telefono dal provider di servizi corrente.</span><span class="sxs-lookup"><span data-stu-id="86707-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="86707-107">Indipendentemente dal paese o dall'area geografica in cui ci si trova, è possibile aggiungere una posizione o un luogo in un luogo di emergenza e rimuovere una posizione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="86707-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="86707-108">A seconda del numero di posizioni fisiche nell'organizzazione, è possibile creare posizioni per edifici, pavimenti e uffici.</span><span class="sxs-lookup"><span data-stu-id="86707-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="86707-109">Vedere [gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="86707-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="86707-110">Per informazioni su come ottenere un piano per le chiamate e sulla quantità di costi, vedere licenze per i [componenti aggiuntivi](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)per i team.</span><span class="sxs-lookup"><span data-stu-id="86707-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="86707-111">È possibile gestire le posizioni di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86707-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="86707-112">Aggiungere una posizione di emergenza</span><span class="sxs-lookup"><span data-stu-id="86707-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="86707-113">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86707-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="86707-114">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="86707-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="86707-115">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="86707-115">Click **Add**.</span></span>
3. <span data-ttu-id="86707-116">Immettere un nome e una descrizione per la posizione.</span><span class="sxs-lookup"><span data-stu-id="86707-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="86707-117">Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="86707-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="86707-118">In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna è importante capire che per attivare correttamente un numero di telefono in Microsoft 365 o Office 365, l'indirizzo impostato nella posizione di emergenza, usato per acquisire il numero, deve corrispondere al prefisso del numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="86707-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="86707-119">Se l'indirizzo non viene trovato e si vuole modificare manualmente l'indirizzo, attivare **modifica manualmente l'** indirizzo.</span><span class="sxs-lookup"><span data-stu-id="86707-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="86707-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="86707-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="86707-121">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="86707-121">Using PowerShell</span></span>

<span data-ttu-id="86707-122">Vedere [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="86707-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="86707-123">Modificare la posizione per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="86707-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="86707-124">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86707-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="86707-125">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="86707-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="86707-126">Nell'elenco selezionare la posizione che si vuole modificare e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="86707-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="86707-127">Apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="86707-127">Make the changes you want.</span></span>
4. <span data-ttu-id="86707-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="86707-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="86707-129">È possibile modificare le informazioni relative all'indirizzo per una posizione solo se l'indirizzo non è convalidato.</span><span class="sxs-lookup"><span data-stu-id="86707-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="86707-130">Se l'indirizzo è già convalidato ed è necessario modificare l'indirizzo, eliminare la posizione e quindi creare una nuova posizione con l'indirizzo corretto.</span><span class="sxs-lookup"><span data-stu-id="86707-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="86707-131">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="86707-131">Using PowerShell</span></span>

<span data-ttu-id="86707-132">Vedere [set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="86707-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="86707-133">Rimuovere una posizione di emergenza</span><span class="sxs-lookup"><span data-stu-id="86707-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="86707-134">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86707-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="86707-135">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="86707-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="86707-136">Nell'elenco selezionare la posizione che si desidera rimuovere e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="86707-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="86707-137">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="86707-137">Using PowerShell</span></span>

<span data-ttu-id="86707-138">Vedere [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="86707-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="86707-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="86707-139">Related topics</span></span>

- [<span data-ttu-id="86707-140">Gestire le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="86707-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="86707-141">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="86707-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="86707-142">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="86707-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="86707-143">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="86707-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
