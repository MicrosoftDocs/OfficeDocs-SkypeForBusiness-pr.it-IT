---
title: Consentire agli utenti di registrare il proprio nome quando accedono a una riunione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: f01d9457fee181615b8a30467ec558eb36a32e7a
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="89944-103">Consentire agli utenti di registrare il proprio nome quando accedono a una riunione</span><span class="sxs-lookup"><span data-stu-id="89944-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="89944-p101">[] Quando configuri i servizi di conferenza telefonica con accesso esterno in Skype for Business online, ricevi numeri di telefono e un bridge per audioconferenze o con accesso esterno. Un bridge di conferenza può contenere uno o più numeri di telefono, dedicati o condivisi.</span><span class="sxs-lookup"><span data-stu-id="89944-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="89944-p102">Il bridge di conferenza risponde alla chiamata di un utente che sta eseguendo l'accesso a una riunione con il telefono. Il bridge risponde con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e configurare le opzioni di sicurezza del PIN per gli organizzatori della riunione. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa. Puoi comunque configurarla in modo tale che non sia richiesto il PIN per l'avvio.</span><span class="sxs-lookup"><span data-stu-id="89944-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="89944-110">Impostare l'opzione che prevede se i chiamanti devono registrare il proprio nome</span><span class="sxs-lookup"><span data-stu-id="89944-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="89944-111">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="89944-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="89944-112">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="89944-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="89944-113">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="89944-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="89944-114">In **esperienza di partecipazione alle riunioni**, vedere la casella di controllo **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**.</span><span class="sxs-lookup"><span data-stu-id="89944-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="89944-p103">Ai chiamanti **selezionati** viene chiesto di registrare il proprio nome prima di accedere alla riunione. Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="89944-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
  - <span data-ttu-id="89944-117">Ai chiamanti **deselezionati** non viene chiesto di registrare il proprio nome prima di accedere alla riunione.</span><span class="sxs-lookup"><span data-stu-id="89944-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="89944-118">Dopo aver apportato le modifiche, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="89944-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="89944-119">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="89944-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="89944-120">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="89944-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="89944-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="89944-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="89944-124">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="89944-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="89944-125">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89944-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="89944-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="89944-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="89944-128">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="89944-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="89944-129">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="89944-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="89944-130">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="89944-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="89944-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="89944-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="89944-133">See also</span><span class="sxs-lookup"><span data-stu-id="89944-133">Related topics</span></span>

[<span data-ttu-id="89944-134">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="89944-134">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
