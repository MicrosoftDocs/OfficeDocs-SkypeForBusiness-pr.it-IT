---
title: Attivare o disattivare voce e chiudere gli annunci per le riunioni in Skype Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come attivare la voce e uscire da attivare o disattivare gli annunci in Skype per riunioni Online Business con i Skype per interfaccia di amministrazione di Business. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490486"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="87a4c-103">Attivare o disattivare voce e chiudere gli annunci per le riunioni in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="87a4c-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="87a4c-104">Per informazioni sugli annunci di entrata e uscita nel Teams Microsoft, vedere [attivazione o disattivazione di annunci di entrata e uscita per le riunioni nel team di Microsoft](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="87a4c-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="87a4c-105">Quando impostano audioconferenze con accesso esterno in Office 365, si otterrà un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="87a4c-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="87a4c-106">Un ponte per conferenze può contenere uno o più numeri di telefono utilizzato per chiamare un Skype per le riunioni aziendali persone.</span><span class="sxs-lookup"><span data-stu-id="87a4c-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="87a4c-107">Bridge conferenza risponde a una chiamata di un utente che si collegano a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="87a4c-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="87a4c-108">Bridge conferenza risponde al chiamante di istruzioni vocali da un operatore automatico conferenza e quindi, a seconda delle impostazioni consentono di riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e impostato la protezione PIN.</span><span class="sxs-lookup"><span data-stu-id="87a4c-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="87a4c-109">Un PIN viene assegnato a un Skype per l'organizzatore della riunione di Business e ha la possibilità di avviare una riunione, se non possono avviare una riunione utilizzando il Skype per applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="87a4c-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="87a4c-110">È possibile impostarla, tuttavia, in modo che non è richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="87a4c-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="87a4c-111">Impostazione di opzioni di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="87a4c-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="87a4c-112">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="87a4c-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="87a4c-113">In **esperienza di partecipazione alle riunioni**, selezionare o deselezionare **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**.</span><span class="sxs-lookup"><span data-stu-id="87a4c-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="87a4c-114">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="87a4c-114">This is selected by default.</span></span> <span data-ttu-id="87a4c-115">Se si deselezionare l'opzione, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="87a4c-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="87a4c-116">In **tipo di annunci di entrata/uscita**, selezionare **i nomi o numeri di telefono** o **toni**.</span><span class="sxs-lookup"><span data-stu-id="87a4c-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="87a4c-117">Selezionare o deselezionare **Ask ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="87a4c-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="87a4c-118">Dopo aver apportato le modifiche, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="87a4c-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="87a4c-119">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="87a4c-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="87a4c-120">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="87a4c-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="87a4c-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="87a4c-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="87a4c-124">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="87a4c-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="87a4c-125">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87a4c-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="87a4c-126">Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="87a4c-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="87a4c-127">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="87a4c-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="87a4c-128">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="87a4c-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="87a4c-129">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="87a4c-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="87a4c-130">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="87a4c-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="87a4c-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="87a4c-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="87a4c-133">See also</span><span class="sxs-lookup"><span data-stu-id="87a4c-133">Related topics</span></span>

[<span data-ttu-id="87a4c-134">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="87a4c-134">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
