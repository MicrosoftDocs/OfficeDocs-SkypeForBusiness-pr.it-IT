---
title: Modificare le impostazioni per un ponte per conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "È possibile ottenere la procedura che è necessario modificare le impostazioni per un bridge di componente aggiuntivo per conferenze Microsoft che consente di richiedere i chiamanti e raccogliere i nomi e i pin per gli organizzatori delle riunioni quando non sono in uso Skype per i client aziendali. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="1a8b3-103">Modificare le impostazioni per un ponte per conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="1a8b3-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="1a8b3-104">Quando impostano audioconferenze con accesso esterno in Office 365, si riceverà i numeri di telefono per gli utenti da quello che viene definito un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="1a8b3-105">Un ponte per conferenze può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="1a8b3-106">Questi numeri di telefono vengono utilizzati quando i chiamanti effettua la chiamata a una riunione.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="1a8b3-107">Il numero di telefono è incluso nella parte inferiore della Skype di invito alla riunione Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="1a8b3-108">Bridging risponde a una chiamata e viene richiesto il chiamante con istruzioni vocali utilizzando un automatico riunione attendant e quindi, a seconda delle impostazioni riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="1a8b3-109">PIN assegnate agli organizzatori della riunione per consentire il per avviare una riunione quando si trovano non sono tramite un Skype per applicazioni aziendali o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="1a8b3-110">Modificare le impostazioni per un ponte per conferenze audio</span><span class="sxs-lookup"><span data-stu-id="1a8b3-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="1a8b3-111">**Configurare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**</span><span class="sxs-lookup"><span data-stu-id="1a8b3-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="1a8b3-112">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a8b3-113">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1a8b3-114">In **Skype per interfaccia di amministrazione di Business**, nel riquadro sinistro passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1a8b3-115">Nella pagina **impostazioni di bridge di Microsoft** , in **esperienza di partecipazione alle riunioni**, selezionare:</span><span class="sxs-lookup"><span data-stu-id="1a8b3-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="1a8b3-116">**Abilitare questa impostazione voce relativa alla riunione e chiudere le notifiche per essere attivata** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="1a8b3-117">Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="1a8b3-118">Quando si seleziona **Abilita voce relativa alla riunione e uscire da attivare le notifiche**, è possibile selezionare le opzioni nell'elenco **tipo di annunci di entrata/uscita** :</span><span class="sxs-lookup"><span data-stu-id="1a8b3-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="1a8b3-119">**I nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il numero di telefono verrà riprodotto quando partecipano a.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="1a8b3-120">**Toni** Quando gli utenti accedono a una riunione, un tono di audio da riprodurre quando partecipano a.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1a8b3-121">Utilizzo **Tone** come tipo di annuncio è attualmente disponibile per tutti i clienti come una caratteristica di anteprima.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="1a8b3-122">**Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="1a8b3-123">Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="1a8b3-124">Dopo aver apportato le modifiche desiderate, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="1a8b3-125">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="1a8b3-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="1a8b3-126">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a8b3-127">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1a8b3-128">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1a8b3-129">Nella sezione **protezione**della pagina **impostazioni di ponte Microsoft** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1a8b3-130">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="1a8b3-131">**Selezionare questa opzione per inviare la posta elettronica per gli utenti**</span><span class="sxs-lookup"><span data-stu-id="1a8b3-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="1a8b3-132">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a8b3-133">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1a8b3-134">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1a8b3-135">Nella pagina **impostazioni di ponte Microsoft** selezionare o deselezionare **automaticamente invia messaggi di posta elettronica agli utenti se viene modificata la relativa configurazione di conferenze audio**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="1a8b3-136">Per ulteriori informazioni, vedere [messaggi di posta elettronica inviato automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="1a8b3-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1a8b3-137">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1a8b3-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1a8b3-138">Per risparmiare tempo o automatizzare il processo, è possibile utilizzare il cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="1a8b3-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="1a8b3-139">Windows PowerShell è incentrato sulla gestione degli utenti e quali utenti sono consentiti o non è autorizzati a eseguire.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1a8b3-140">Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1a8b3-141">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="1a8b3-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1a8b3-142">Perché è necessario utilizzare Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a8b3-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1a8b3-143">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a8b3-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1a8b3-144">Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1a8b3-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1a8b3-145">Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a8b3-145">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1a8b3-146">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a8b3-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1a8b3-147">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a8b3-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1a8b3-148">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a8b3-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1a8b3-p107">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1a8b3-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1a8b3-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1a8b3-151">Related topics</span></span>

[<span data-ttu-id="1a8b3-152">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a8b3-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

