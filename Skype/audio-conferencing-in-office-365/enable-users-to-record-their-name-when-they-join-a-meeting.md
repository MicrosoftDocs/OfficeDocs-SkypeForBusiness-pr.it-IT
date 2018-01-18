---
title: Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Informazioni su come abilitare o disabilitare se gli utenti possono registrare i nomi quando partecipano a una riunione '
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="d1f4f-103">Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione</span><span class="sxs-lookup"><span data-stu-id="d1f4f-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="d1f4f-104">Quando impostano audioconferenze con accesso esterno in Office 365, si riceverà i numeri di telefono e il processo definito un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="d1f4f-105">Un ponte per conferenze può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicate o condivise.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="d1f4f-106">Bridge conferenza risponde a una chiamata di un utente che si collegano a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d1f4f-107">Bridge conferenza risponde al chiamante di istruzioni vocali da un operatore automatico e quindi, a seconda delle loro impostazioni consentono di riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e impostato la protezione PIN per gli organizzatori delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="d1f4f-108">PIN assegnate agli organizzatori delle riunioni per consentire loro di avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="d1f4f-109">Tuttavia, è possibile impostare tale in modo che non è richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="d1f4f-110">Specificare se i chiamanti devono registrare il proprio nome</span><span class="sxs-lookup"><span data-stu-id="d1f4f-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="d1f4f-111">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d1f4f-112">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d1f4f-113">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="d1f4f-114">In **esperienza di partecipazione alle riunioni**, vedere la casella di controllo **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="d1f4f-115">**Selezionata** I chiamanti verranno richiesto di registrare il proprio nome prima di immettere la riunione.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-115">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="d1f4f-116">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-116">This is selected by default.</span></span>
    
  - <span data-ttu-id="d1f4f-117">**Deselezionata** I chiamanti non verranno richiesto di registrare il proprio nome prima di immettere la riunione.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="d1f4f-118">Dopo aver apportato le modifiche desiderate, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d1f4f-119">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d1f4f-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d1f4f-120">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="d1f4f-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="d1f4f-121">Windows PowerShell è incentrato sulla gestione degli utenti e quali gli utenti possono eseguire.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-121">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="d1f4f-122">Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d1f4f-123">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d1f4f-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d1f4f-124">Perché è necessario utilizzare Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1f4f-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d1f4f-125">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1f4f-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="d1f4f-126">Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d1f4f-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d1f4f-127">Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1f4f-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d1f4f-128">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d1f4f-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d1f4f-129">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d1f4f-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d1f4f-130">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d1f4f-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="d1f4f-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="d1f4f-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d1f4f-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d1f4f-133">Related topics</span></span>

[<span data-ttu-id="d1f4f-134">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1f4f-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

