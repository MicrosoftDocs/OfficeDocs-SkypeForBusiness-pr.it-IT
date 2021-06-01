---
title: Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN, e su come impostare la lunghezza delle riunioni in Skype for Business.
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238601"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="eb5ed-103">Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="eb5ed-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> <span data-ttu-id="eb5ed-104">Per informazioni su come impostare la lunghezza del PIN in Microsoft Teams, consulta [Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="eb5ed-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="eb5ed-105">Quando imposti un'audioconferenza per Skype for Business, ottieni un ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="eb5ed-106">Un bridge di conferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="eb5ed-107">Il numero di telefono impostato verrà incluso negli inviti alla riunione per l'app Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="eb5ed-108">Il bridge di conferenza risponde a una chiamata di un utente che partecipa a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="eb5ed-109">Risponde al chiamante con le istruzioni vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche e chiedere ai chiamanti di registrare il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="eb5ed-110">**Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="eb5ed-111">Gli organizzatori della riunione utilizzano i PIN per avviare le riunioni quando non riescono a partecipare utilizzando l'app Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="eb5ed-112">Impostazione della lunghezza del PIN</span><span class="sxs-lookup"><span data-stu-id="eb5ed-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="eb5ed-113">**Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Impostazioni bridge Microsoft **per audioconferenze.**  >  </span><span class="sxs-lookup"><span data-stu-id="eb5ed-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="eb5ed-114">In **Lunghezza** PIN di sicurezza selezionare il numero di cifre desiderato per il PIN e quindi fare clic su  >   **Salva.**</span><span class="sxs-lookup"><span data-stu-id="eb5ed-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb5ed-115">Un PIN è diverso da un ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="eb5ed-116">Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="eb5ed-117">Vengono utilizzati per identificare la riunione.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-117">They are used to identify the meeting.</span></span> <span data-ttu-id="eb5ed-118">Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="eb5ed-119">Vuoi saperne di più sulle impostazioni del PIN?</span><span class="sxs-lookup"><span data-stu-id="eb5ed-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="eb5ed-120">I PIN possono essere da 4 a 12 cifre. il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="eb5ed-121">Solo i numeri vengono utilizati quando si creano dei PIN.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="eb5ed-122">Lettere e caratteri speciali non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="eb5ed-123">L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="eb5ed-124">L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="eb5ed-125">Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="eb5ed-126">Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="eb5ed-127">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="eb5ed-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="eb5ed-128">Per risparmiare tempo o automatizzare questa operazione, è possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)</span><span class="sxs-lookup"><span data-stu-id="eb5ed-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="eb5ed-129">Per impostare a 8 il numero di cifre del PIN:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="eb5ed-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="eb5ed-130">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eb5ed-131">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="eb5ed-132">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb5ed-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb5ed-133">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb5ed-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="eb5ed-134">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="eb5ed-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="eb5ed-135">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="eb5ed-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="eb5ed-136">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="eb5ed-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="eb5ed-137">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="eb5ed-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="eb5ed-138">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="eb5ed-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="eb5ed-139">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="eb5ed-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="eb5ed-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="eb5ed-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="eb5ed-p109">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="eb5ed-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb5ed-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb5ed-143">See also</span></span>

[<span data-ttu-id="eb5ed-144">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="eb5ed-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
