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
description: Informazioni sui passaggi per reimpostare l'ID conferenza di una riunione dell'utente in Microsoft teams e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni.
ms.openlocfilehash: fbda2d65868d9f4082ae7b3ee835d0560c609e11
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666198"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="be5e5-103">Reimpostare un ID conferenza per un utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be5e5-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="be5e5-104">Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono di accesso esterno che possono essere usati dai chiamanti per chiamare una riunione.</span><span class="sxs-lookup"><span data-stu-id="be5e5-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="be5e5-105">Quando l'utente compone il numero di telefono, l'operatore automatico per la riunione chiederà al chiamante di immettere l'ID conferenza in modo che possa partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="be5e5-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be5e5-106">Se il provider di servizi di conferenza è Microsoft, l'ID conferenza degli utenti è impostato su Solo dinamico per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="be5e5-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="be5e5-107">Sfortunatamente, non c'è possibilità di modificarla per diventare statica, dato che ora non è supportata.</span><span class="sxs-lookup"><span data-stu-id="be5e5-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="be5e5-108">Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Microsoft teams abilitati per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="be5e5-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="be5e5-109">Reimpostare l'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="be5e5-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="be5e5-110">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="be5e5-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="be5e5-111">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="be5e5-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="be5e5-112">Fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="be5e5-112">Click **Edit**.</span></span>

3. <span data-ttu-id="be5e5-113">In **audioconferenza** fare clic su **Reimposta ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="be5e5-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="be5e5-114">Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="be5e5-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="be5e5-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="be5e5-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="be5e5-116">Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma è possibile disattivarli.</span><span class="sxs-lookup"><span data-stu-id="be5e5-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="be5e5-117">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="be5e5-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="be5e5-118">Questo messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica principale, in molti casi, nella cassetta postale Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="be5e5-118">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="be5e5-119">Il messaggio di posta elettronica contiene il nuovo ID conferenza, i numeri di telefono di accesso esterno predefiniti e le istruzioni per l'aggiornamento delle riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="be5e5-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="be5e5-120">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="be5e5-120">What else should I know?</span></span>

- <span data-ttu-id="be5e5-121">È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su **Invia informazioni conferenza in posta elettronica** per l'utente nella sezione **audioconferenza** .</span><span class="sxs-lookup"><span data-stu-id="be5e5-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="be5e5-122">Il PIN non è incluso.</span><span class="sxs-lookup"><span data-stu-id="be5e5-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="be5e5-123">Un ID conferenza conterrà 8 cifre e non è possibile modificarne la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="be5e5-123">A conference ID will contain 8 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="be5e5-124">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="be5e5-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="be5e5-125">Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="be5e5-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="be5e5-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="be5e5-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="be5e5-127">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be5e5-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="be5e5-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="be5e5-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="be5e5-129">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="be5e5-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="be5e5-130">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="be5e5-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="be5e5-131">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="be5e5-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="be5e5-132">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be5e5-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="be5e5-133">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="be5e5-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="be5e5-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="be5e5-134">Related topics</span></span>

[<span data-ttu-id="be5e5-135">Reimpostare il PIN di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="be5e5-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
