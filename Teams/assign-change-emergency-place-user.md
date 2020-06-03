---
title: Assegnare, modificare le posizioni per i percorsi di emergenza per gli utenti
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
description: In questo articolo verrà illustrato come assegnare o modificare la posizione di un luogo di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539513"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="a64ea-103">Assegnare o modificare la posizione di un luogo di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="a64ea-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="a64ea-104">Ogni numero di telefono attivo deve avere una posizione di emergenza associata quando si assegna il numero di telefono a un utente.</span><span class="sxs-lookup"><span data-stu-id="a64ea-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="a64ea-105">(Si associa l'indirizzo quando si riceve un numero di telefono in Office 365 o quando si trasferisce un numero di telefono). Quando si associa il numero a una posizione di emergenza, è anche possibile aggiungere una posizione per specificare un percorso più preciso all'interno di una posizione fisica.</span><span class="sxs-lookup"><span data-stu-id="a64ea-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="a64ea-106">Una posizione può essere il piano, l'ala dell'edificio o il numero di ufficio in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="a64ea-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="a64ea-107">È possibile avere un numero illimitato di posizioni per una determinata posizione di emergenza e modificare la posizione se l'utente si sposta in un altro ufficio o edificio.</span><span class="sxs-lookup"><span data-stu-id="a64ea-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="a64ea-108">Ad esempio, se l'utente si sposta da piano 34 a piano 35.</span><span class="sxs-lookup"><span data-stu-id="a64ea-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="a64ea-109">Per informazioni su come ottenere piani per le chiamate e su quanto costano, vedere licenze per i [componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)per i team.</span><span class="sxs-lookup"><span data-stu-id="a64ea-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="a64ea-110">È possibile assegnare o modificare la posizione di un luogo di emergenza per un utente nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a64ea-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a64ea-111">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a64ea-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a64ea-112">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **Voice**  >  **numeri di telefono**vocale.</span><span class="sxs-lookup"><span data-stu-id="a64ea-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="a64ea-113">Nella pagina **numeri di telefono** fare clic sulla scheda **numeri** , selezionare un numero utente nell'elenco e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a64ea-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="a64ea-114">Nel riquadro **modifica** , in **posizione di emergenza**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a64ea-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="a64ea-115">Per assegnare una posizione, cercare la posizione o il luogo e quindi selezionare il luogo nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="a64ea-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="a64ea-116">Per modificare la posizione già assegnata all'utente, fare clic su **X** per rimuovere il percorso e il luogo esistenti, cercare e quindi selezionare la posizione che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="a64ea-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="a64ea-117">A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni relative al numero di telefono, disattivare o attivare l' **utente di posta elettronica con le informazioni sui numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="a64ea-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="a64ea-118">Per impostazione predefinita, questa opzione è attivata.</span><span class="sxs-lookup"><span data-stu-id="a64ea-118">By default, this is on.</span></span>

5. <span data-ttu-id="a64ea-119">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="a64ea-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="a64ea-120">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a64ea-120">Using PowerShell</span></span>

<span data-ttu-id="a64ea-121">Vedere [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="a64ea-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a64ea-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a64ea-122">Related topics</span></span>

- [<span data-ttu-id="a64ea-123">Gestire le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="a64ea-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a64ea-124">Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a64ea-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="a64ea-125">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a64ea-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="a64ea-126">Assegnare o modificare una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="a64ea-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="a64ea-127">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="a64ea-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="a64ea-128">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="a64ea-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
