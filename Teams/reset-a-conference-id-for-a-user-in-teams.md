---
title: Reimpostare un ID conferenza per un utente in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione di un utente in Microsoft Teams e ottenere i collegamenti agli strumenti di aggiornamento e migrazione delle riunioni.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662126"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="f1f1a-103">Reimpostare un ID conferenza per un utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1f1a-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="f1f1a-104">Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono per l'accesso esterno che possono essere usati dai chiamanti per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="f1f1a-105">Quando l'utente compone il numero di telefono, l'operatore automatico della riunione chiederà al chiamante di immettere l'ID conferenza per poter partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1f1a-106">Gli ID conferenza vengono generati automaticamente, saranno compresi tra 7 e 9 cifre e vengono impostati quando abiliti l'Audioconferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="f1f1a-107">**Gli ID conferenza statici non sono supportati.**</span><span class="sxs-lookup"><span data-stu-id="f1f1a-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="f1f1a-108">Reimpostazione dell'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="f1f1a-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="f1f1a-109">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="f1f1a-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f1f1a-110">Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f1f1a-111">Fare **clic su Modifica.**</span><span class="sxs-lookup"><span data-stu-id="f1f1a-111">Click **Edit**.</span></span>

3. <span data-ttu-id="f1f1a-112">In **Audioconferenza fare** clic **su Reimposta ID conferenza.**</span><span class="sxs-lookup"><span data-stu-id="f1f1a-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="f1f1a-113">Nella finestra **Reimposta ID conferenza,** fai clic su **Reimposta.**</span><span class="sxs-lookup"><span data-stu-id="f1f1a-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="f1f1a-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="f1f1a-115">Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma questa opzione può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="f1f1a-116">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="f1f1a-117">Questo messaggio verrà inviato all'indirizzo di posta elettronica principale, in molti casi alla cassetta postale di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="f1f1a-118">L'e-mail contiene il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso e le istruzioni per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="f1f1a-119">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="f1f1a-119">What else should I know?</span></span>

- <span data-ttu-id="f1f1a-120">Facendo clic su Invia informazioni conferenza tramite posta elettronica per l'utente nella sezione  Audioconferenza, è possibile inviare all'utente tutte le informazioni relative alla conferenza in un messaggio di posta elettronica contenente l'ID conferenza e i numeri di telefono per l'accesso **esterno.**</span><span class="sxs-lookup"><span data-stu-id="f1f1a-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="f1f1a-121">Il PIN non è incluso.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="f1f1a-122">Il servizio Teams crea un ID conferenza di 7-9 cifre.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="f1f1a-123">Non è possibile modificarne la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-123">You can't change its length.</span></span>
    
- <span data-ttu-id="f1f1a-124">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="f1f1a-125">Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f1f1a-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f1f1a-127">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1f1a-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f1f1a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f1f1a-129">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f1f1a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f1f1a-130">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f1f1a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f1f1a-131">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="f1f1a-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f1f1a-132">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1f1a-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f1f1a-133">Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="f1f1a-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f1f1a-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1f1a-134">Related topics</span></span>

[<span data-ttu-id="f1f1a-135">Reimpostare il PIN di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f1f1a-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
