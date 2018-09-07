---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: "Informazioni su come attivare gli annunci di entrata e uscita per le riunioni in Skype for Business Online tramite l'interfaccia di amministrazione di Skype for Business. "
ms.openlocfilehash: 8d91db2014439eb2c9e38f65215cf85d6f047157
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863264"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="4a3da-103">Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4a3da-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4a3da-104">Per informazioni sugli annunci di entrata e uscita in Microsof Teamst, consulta [Attivazione o disattivazione degli annunci di entrata e uscita per le riunioni in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4a3da-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="4a3da-105">Quando imposti Audioconferenza in Office 365, ottieni un ponte per audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4a3da-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="4a3da-106">Un ponte per audioconferenze può contenere uno o più numeri di telefono che le persone possono utilizzare per partecipare a una riunione su Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4a3da-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="4a3da-107">Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="4a3da-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="4a3da-108">Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4a3da-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="4a3da-109">Viene assegnato un PIN a un organizzatore della riunione su Skype for Business, il quale permette di avviare la riunione se i partecipanti non sono in grado di farlo tramite l'app di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4a3da-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="4a3da-110">È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="4a3da-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="4a3da-111">Impostazione delle opzioni di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="4a3da-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="4a3da-112">Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Audioconferenza** > **Impostazioni del ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4a3da-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="4a3da-113">Su **Esperienza di partecipazione alle riunioni**, seleziona o deseleziona **Abilita l'attivazione di annunci di entrata e uscita per la riunione**.</span><span class="sxs-lookup"><span data-stu-id="4a3da-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="4a3da-114">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4a3da-114">This is selected by default.</span></span> <span data-ttu-id="4a3da-115">Se si deseleziona la casella, gli utenti che già partecipano alla riunione non verranno informati quando un utente accede alla riunione o quando l'abbandona.</span><span class="sxs-lookup"><span data-stu-id="4a3da-115">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="4a3da-116">Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.</span><span class="sxs-lookup"><span data-stu-id="4a3da-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="4a3da-117">Seleziona o deseleziona **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="4a3da-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="4a3da-118">Dopo aver apportato le modifiche, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4a3da-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4a3da-119">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4a3da-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4a3da-120">Per automatizzarle o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4a3da-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="4a3da-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4a3da-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4a3da-124">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="4a3da-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4a3da-125">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a3da-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4a3da-126">Windows PowerShell offre numerosi vantaggi per quanto riguarda velocità, semplicità e produttività rispetto all'uso della sola Interfaccia di amministrazione di Office 365, ad esempio quando si modificano le impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4a3da-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> <span data-ttu-id="4a3da-127">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4a3da-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4a3da-128">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a3da-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4a3da-129">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a3da-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4a3da-130">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a3da-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4a3da-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="4a3da-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4a3da-133">See also</span><span class="sxs-lookup"><span data-stu-id="4a3da-133">Related topics</span></span>

[<span data-ttu-id="4a3da-134">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="4a3da-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
