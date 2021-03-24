---
title: Assegnare o modificare una posizione di emergenza per un utente
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
description: In questo articolo viene spiegato come assegnare o modificare una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102982"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="f1ce6-103">Assegnare o modificare una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="f1ce6-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="f1ce6-104">Durante la configurazione dei Piani per le chiamate, è necessario assegnare una posizione di emergenza a ogni numero di telefono o utente.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="f1ce6-105">Nei paesi europei, la posizione di emergenza è associata al numero di telefono quando lo si ottiene da Microsoft 365 o Office 365 o quando si trasferisce un numero di telefono a Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f1ce6-106">Negli Stati Uniti, la posizione di emergenza è associata al numero di telefono quando viene assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="f1ce6-107">L'indirizzo per gli interventi di emergenza può essere modificato se l'utente a cui è assegnato si sposta in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="f1ce6-108">Per altre informazioni sugli indirizzi e le posizioni per gli interventi di emergenza, vedere Che cosa sono le località di emergenza, i [luoghi e il routing delle chiamate?](./what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f1ce6-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="f1ce6-109">Per informazioni su come ottenere un Piano per chiamate e sul costo, vedere Licenze [per i componenti aggiuntivi di Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="f1ce6-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="f1ce6-110">È possibile assegnare o modificare una posizione per gli interventi di emergenza per un utente nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f1ce6-111">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f1ce6-112">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Numeri di telefono**  >  **vocali.**</span><span class="sxs-lookup"><span data-stu-id="f1ce6-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="f1ce6-113">Nella pagina **Numeri di telefono** fare clic sulla scheda **Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="f1ce6-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="f1ce6-114">Nel riquadro **Modifica,** in **Posizione emergenza,** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1ce6-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="f1ce6-115">Per assegnare una posizione per gli interventi di emergenza, cercare e selezionare una posizione per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="f1ce6-116">Per modificare la posizione di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente e quindi cercare e selezionare la posizione da assegnare.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="f1ce6-117">A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare l'utente di posta elettronica **con informazioni sul numero di telefono.**</span><span class="sxs-lookup"><span data-stu-id="f1ce6-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="f1ce6-118">Per impostazione predefinita, questa opzione è impostata su .</span><span class="sxs-lookup"><span data-stu-id="f1ce6-118">By default, this is on.</span></span>

5. <span data-ttu-id="f1ce6-119">Fare clic **su Applica**.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="f1ce6-120">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1ce6-120">Using PowerShell</span></span>

<span data-ttu-id="f1ce6-121">Vedere [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="f1ce6-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="f1ce6-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1ce6-122">Related topics</span></span>

- [<span data-ttu-id="f1ce6-123">Gestire le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="f1ce6-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="f1ce6-124">Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f1ce6-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="f1ce6-125">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f1ce6-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="f1ce6-126">Assegnare o modificare un luogo per una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="f1ce6-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="f1ce6-127">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="f1ce6-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="f1ce6-128">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="f1ce6-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="f1ce6-129">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="f1ce6-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)