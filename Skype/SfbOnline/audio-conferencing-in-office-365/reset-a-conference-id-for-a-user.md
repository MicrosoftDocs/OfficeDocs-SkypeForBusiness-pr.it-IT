---
title: Reimpostare un ID conferenza per un utente su Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Informazioni sui passaggi per reimpostare l'ID conferenza di un utente su Skype for Business online e ottenere collegamenti di aggiornamento e migrazione della riunione. "
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850062"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="5b110-103">Reimpostare un ID conferenza per un utente su Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="5b110-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="5b110-104">Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="5b110-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="5b110-105">Un ID conferenza dinamico è incluso nella parte inferiore dell'invito alla riunione insieme ai numeri di telefono di accesso esterno che possono essere utilizzati dai chiamanti per partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="5b110-105">This conference ID is included at the bottom of Skype for Business Online meeting invitations along with the dial-in phone numbers that can be used by callers to call into a meeting.</span></span> <span data-ttu-id="5b110-106">Quando l'utente compone il numero di telefono, l'operatore automatico della riunione richiede di inserire l'ID conferenza per poter partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="5b110-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to input this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b110-107">Se il provider di servizi di conferenza è Microsoft, l'ID conferenza degli utenti è impostato su Solo dinamico per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5b110-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="5b110-108">Purtroppo, non è possibile modificarlo in statico nell'Interfaccia di amministrazione di Skype for Business o utilizzando Windows Powershell, dato che questa opzione non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="5b110-108">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="5b110-109">Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for Business abilitati per Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="5b110-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="5b110-110">Reimpostazione dell'ID conferenza di una riunione per un utente</span><span class="sxs-lookup"><span data-stu-id="5b110-110">Resetting the meeting conference ID for a user</span></span>
   
1. <span data-ttu-id="5b110-111">Nell'**Interfaccia di amministrazione di Skype for Business**, clicca su **Audioconferenza** > **Utenti**, seleziona un utente, e poi nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="5b110-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
2. <span data-ttu-id="5b110-112">Nella finestra **Reimpostare ID conferenza?**, fai clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5b110-112">In the \*\* Reset conference ID?\*\* window, click **Yes**.</span></span> <span data-ttu-id="5b110-113">Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="5b110-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="5b110-114">Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma questa impostazione può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="5b110-114">By default, emails are sent to users, but it can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b110-p104">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="5b110-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="5b110-118">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="5b110-118">What else should I know?</span></span>

- <span data-ttu-id="5b110-119">Facendo clic su **Invia informazioni conferenza tramite posta elettronica**, puoi inviare all'utente tutte le informazioni relative alla conferenza in un messaggio di posta elettronica che contiene l'ID conferenza e i numeri di telefono per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5b110-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="5b110-120">Il PIN non è incluso.</span><span class="sxs-lookup"><span data-stu-id="5b110-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="5b110-121">Un ID conferenza conterrà 7 cifre e tale lunghezza non può essere modificata nell'Interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b110-121">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="5b110-122">Dopo la reimpostazione, il nuovo ID conferenza viene mostrato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5b110-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="5b110-123">Per visualizzare l'ID conferenza di un utente per un'audioconferenza, osserva la parte inferiore del riquadro Azioni alla voce **Audioconferenza** dopo aver selezionato l'utente nella pagina **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="5b110-123">The conference ID for a user for dial-in conferencing can be viewed at the bottom of the Action pane under **Dial-in conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="5b110-124">Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="5b110-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5b110-125">È necessario informare gli utenti di pianificare di nuovo gli inviti alle riunioni esistenti per assicurarsi che il nuovo ID conferenza venga aggiunto agli inviti.</span><span class="sxs-lookup"><span data-stu-id="5b110-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="5b110-126">Gli utenti possono utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="5b110-126">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="5b110-127">Per scoprire come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni di Skype for Business, consulta:</span><span class="sxs-lookup"><span data-stu-id="5b110-127">To see how to download, install and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="5b110-128">Strumento di aggiornamento delle riunioni di Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="5b110-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="5b110-129">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5b110-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="5b110-130">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="5b110-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5b110-131">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5b110-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5b110-p107">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="5b110-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5b110-135">Introduzione a Windows PowerShell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="5b110-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5b110-136">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="5b110-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5b110-p108">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b110-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5b110-139">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="5b110-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5b110-140">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5b110-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5b110-141">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5b110-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5b110-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5b110-142">Related topics</span></span>

[<span data-ttu-id="5b110-143">Reimpostare il PIN di Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5b110-143">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin.md)
