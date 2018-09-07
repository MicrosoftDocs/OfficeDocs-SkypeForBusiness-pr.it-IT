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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN, e su come impostare la lunghezza delle riunioni in Skype for Business.
ms.openlocfilehash: 0714a55add1d3a4840d5868d0e09f0a3dc4b8561
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861724"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="86006-103">Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="86006-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="86006-104">Per informazioni su come impostare la lunghezza del PIN in Microsoft Teams, consulta [Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="86006-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="86006-105">Quando imposti un'audioconferenza per Skype for Business, ottieni un ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="86006-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="86006-106">Un ponte per audioconferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="86006-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> <span data-ttu-id="86006-107">Il numero di telefono impostato verrà incluso negli inviti alla riunione per l'app Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="86006-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="86006-108">Il ponte per audioconferenza risponde alla chiamata degli utenti che si collegano a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="86006-108">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="86006-109">Risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche e chiedere ai chiamanti di registrare il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="86006-109">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="86006-110">**Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="86006-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="86006-111">Gli organizzatori della riunione utilizzano i PIN per avviare le riunioni quando non riescono a partecipare utilizzando l'app Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="86006-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="86006-112">Impostazione della lunghezza del PIN</span><span class="sxs-lookup"><span data-stu-id="86006-112">Setting the PIN length The default is 5.</span></span>
 
1. <span data-ttu-id="86006-113">Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, vai su **Audioconferenza** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="86006-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="86006-114">All voce **Sicurezza** > **Lunghezza del PIN**, seleziona il numero di cifre che desideri utilizzare per il PIN, quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="86006-114">Under **Security** > **PIN length** > enter the number of digits you want for the PIN and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="86006-115">Un PIN è diverso da un ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="86006-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="86006-116">Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione.</span><span class="sxs-lookup"><span data-stu-id="86006-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="86006-117">Vengono utilizzati per identificare la riunione.</span><span class="sxs-lookup"><span data-stu-id="86006-117">They are used to identify the meeting.</span></span> <span data-ttu-id="86006-118">Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="86006-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="86006-119">Vuoi saperne di più sulle impostazioni del PIN?</span><span class="sxs-lookup"><span data-stu-id="86006-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="86006-120">I PIN possono essere composti da 4 fino a 12 cifre; il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="86006-120">The PIN can only be from 4 to 12 digits. The default is 5.</span></span> <span data-ttu-id="86006-121">Solo i numeri vengono utilizati quando si creano dei PIN.</span><span class="sxs-lookup"><span data-stu-id="86006-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="86006-122">Lettere e caratteri speciali non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="86006-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="86006-123">L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="86006-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="86006-124">L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="86006-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="86006-125">Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86006-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="86006-126">Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato.</span><span class="sxs-lookup"><span data-stu-id="86006-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="86006-127">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="86006-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="86006-128">Per informazioni su come impostare la lunghezza del PIN in Microsoft Teams, consulta monad startTag">[Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Microsoft Teams](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="86006-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="86006-129">Per impostare a 8 il numero di cifre del PIN:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="86006-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="86006-p107">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="86006-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="86006-133">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="86006-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="86006-134">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="86006-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="86006-p108">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="86006-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="86006-137">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86006-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="86006-138">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="86006-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="86006-139">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="86006-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="86006-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86006-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="86006-p109">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="86006-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86006-143">Consulta anche</span><span class="sxs-lookup"><span data-stu-id="86006-143">See also</span></span>

[<span data-ttu-id="86006-144">Provare o acquistare Audioconferenza in Office 365</span><span class="sxs-lookup"><span data-stu-id="86006-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
