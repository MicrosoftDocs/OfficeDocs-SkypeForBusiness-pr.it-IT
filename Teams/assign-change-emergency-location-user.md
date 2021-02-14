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
description: In questo articolo imparerai ad assegnare o modificare una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809566"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="64c6b-103">Assegnare o modificare una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="64c6b-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="64c6b-104">Quando si configurano i Piani per chiamate, è necessario assegnare una posizione per gli interventi di emergenza a ogni numero di telefono o utente.</span><span class="sxs-lookup"><span data-stu-id="64c6b-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="64c6b-105">Nei paesi europei, la posizione per gli interventi di emergenza è associata al numero di telefono quando la ottieni da Microsoft 365 o Office 365 o quando trasferisci un numero di telefono in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="64c6b-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="64c6b-106">Negli Stati Uniti, la posizione per gli interventi di emergenza viene associata al numero di telefono quando viene assegnata all'utente.</span><span class="sxs-lookup"><span data-stu-id="64c6b-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="64c6b-107">L'indirizzo per gli interventi di emergenza può essere modificato se l'utente a cui è assegnato si sposta in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="64c6b-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="64c6b-108">Per ulteriori informazioni su indirizzi e posizioni per gli interventi di emergenza, consulta Cosa sono il routing delle chiamate, le posizioni e le posizioni [per gli interventi di emergenza?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="64c6b-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="64c6b-109">Per informazioni su come ottenere un Piano per chiamate e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="64c6b-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
  
<span data-ttu-id="64c6b-110">Puoi assegnare o modificare la posizione per gli interventi di emergenza di un utente nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64c6b-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="64c6b-111">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64c6b-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="64c6b-112">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su**  >  **Numeri di telefono vocali.**</span><span class="sxs-lookup"><span data-stu-id="64c6b-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="64c6b-113">Nella pagina **Numeri di telefono** fare clic sulla scheda **Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="64c6b-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="64c6b-114">Nel riquadro **Modifica,** in **Posizione per gli interventi di** emergenza, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64c6b-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="64c6b-115">Per assegnare una posizione per gli interventi di emergenza, cercala e selezionala.</span><span class="sxs-lookup"><span data-stu-id="64c6b-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="64c6b-116">Per modificare la posizione per gli interventi di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente, quindi cercare e selezionare la posizione da assegnare.</span><span class="sxs-lookup"><span data-stu-id="64c6b-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="64c6b-117">A seconda che si voglia inviare un messaggio di posta elettronica con le informazioni sul numero di telefono all'utente, disattivare o attivare l'e-mail con informazioni **sul numero di telefono.**</span><span class="sxs-lookup"><span data-stu-id="64c6b-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="64c6b-118">Per impostazione predefinita, questa opzione è on.</span><span class="sxs-lookup"><span data-stu-id="64c6b-118">By default, this is on.</span></span>

5. <span data-ttu-id="64c6b-119">Fare clic **su Applica.**</span><span class="sxs-lookup"><span data-stu-id="64c6b-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="64c6b-120">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="64c6b-120">Using PowerShell</span></span>

<span data-ttu-id="64c6b-121">Vedi [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)</span><span class="sxs-lookup"><span data-stu-id="64c6b-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="64c6b-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="64c6b-122">Related topics</span></span>

- [<span data-ttu-id="64c6b-123">Gestire le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="64c6b-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="64c6b-124">Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="64c6b-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="64c6b-125">Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="64c6b-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="64c6b-126">Assegnare o modificare un luogo per una posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="64c6b-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="64c6b-127">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="64c6b-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="64c6b-128">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="64c6b-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="64c6b-129">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="64c6b-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
