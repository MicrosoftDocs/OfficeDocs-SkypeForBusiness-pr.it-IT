---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Informazioni su come attivare la voce e uscire da attivare o disattivare gli annunci in Skype per riunioni Online Business con i Skype per interfaccia di amministrazione di Business. '
ms.openlocfilehash: ca109a1e6a1538c6561e8f5a6e29bd0f70cf5efe
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="6b205-103">Attivare o disattivare gli annunci di entrata e uscita per le riunioni</span><span class="sxs-lookup"><span data-stu-id="6b205-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="6b205-104">Quando impostano audioconferenze con accesso esterno in Office 365, si otterrà un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="6b205-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="6b205-105">Un ponte per conferenze può contenere uno o più numeri di telefono utilizzato per chiamare un Skype per riunione Business o Microsoft Teams persone.</span><span class="sxs-lookup"><span data-stu-id="6b205-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="6b205-106">Bridge conferenza risponde a una chiamata di un utente che si collegano a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="6b205-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6b205-107">Bridge conferenza risponde al chiamante di istruzioni vocali da un operatore automatico conferenza e quindi, a seconda delle impostazioni consentono di riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e impostato la protezione PIN.</span><span class="sxs-lookup"><span data-stu-id="6b205-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="6b205-108">Un PIN viene assegnato a un Skype per Business o Microsoft Teams organizzatore della riunione e ha la possibilità di avviare una riunione, se non possono avviare una riunione utilizzando un Skype per applicazioni aziendali o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b205-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="6b205-109">È possibile impostarla, tuttavia, in modo che non è richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="6b205-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="6b205-110">Impostazione di opzioni di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="6b205-110">Setting meeting join options</span></span>

1. <span data-ttu-id="6b205-111">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="6b205-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="6b205-112">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6b205-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="6b205-113">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6b205-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="6b205-114">In **esperienza di partecipazione alle riunioni**, selezionare o deselezionare **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**.</span><span class="sxs-lookup"><span data-stu-id="6b205-114">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="6b205-115">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6b205-115">This is selected by default.</span></span> <span data-ttu-id="6b205-116">Se si deselezionare l'opzione, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="6b205-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="6b205-117">In **tipo di annunci di entrata/uscita**, selezionare **i nomi o numeri di telefono** o **toni**.</span><span class="sxs-lookup"><span data-stu-id="6b205-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
6. <span data-ttu-id="6b205-118">Selezionare o deselezionare **Ask ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="6b205-118">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="6b205-119">Dopo aver apportato le modifiche, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b205-119">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6b205-120">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6b205-120">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6b205-121">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="6b205-121">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="6b205-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6b205-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6b205-125">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="6b205-125">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6b205-126">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b205-126">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="6b205-127">Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6b205-127">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="6b205-128">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6b205-128">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6b205-129">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b205-129">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6b205-130">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b205-130">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6b205-131">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b205-131">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="6b205-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="6b205-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6b205-134">See also</span><span class="sxs-lookup"><span data-stu-id="6b205-134">Related topics</span></span>

[<span data-ttu-id="6b205-135">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="6b205-135">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
