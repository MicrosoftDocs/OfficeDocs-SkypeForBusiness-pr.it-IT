---
title: Modificare le impostazioni per un bridge per audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Ecco i passaggi necessari per modificare le impostazioni per un Bridge di conferenza usato per richiedere ai chiamanti e raccogliere nomi e pin per gli organizzatori della riunione quando non usano le app Skype for business o Microsoft teams. '
ms.openlocfilehash: 97c1439325e5a9a00cacfa26e97078d2c2a91014
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "36183793"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="34705-103">Modificare le impostazioni per un bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="34705-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="34705-104">Quando si configurano i servizi di audioconferenza in Office 365, si riceveranno i numeri di telefono per gli utenti provenienti da un Bridge per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="34705-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="34705-105">Un Bridge per i servizi di conferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="34705-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="34705-106">Questi numeri di telefono vengono usati quando i chiamanti accedono a una riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="34705-107">Il numero di telefono è incluso nella parte inferiore dell'invito alla riunione di Skype for business o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="34705-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="34705-108">Il Bridge per i servizi di conferenza risponde a una chiamata e chiede al chiamante di ricevere le istruzioni vocali usando un operatore automatico della riunione e quindi, a seconda delle impostazioni, può riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN.</span><span class="sxs-lookup"><span data-stu-id="34705-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="34705-109">I PIN vengono assegnati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un'app Skype for business o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="34705-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="34705-110">Un PIN è necessario solo per l'organizzatore della riunione quando un utente dell'app Skype for business o Microsoft teams non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="34705-111">Se tutti gli utenti effettuano la chiamata alla riunione, è necessario che l'organizzatore della riunione avvii la riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="34705-113">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34705-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="34705-114">Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="34705-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="34705-115">Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="34705-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="34705-116">Nel riquadro **Impostazioni Bridge** selezionare:</span><span class="sxs-lookup"><span data-stu-id="34705-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="34705-117">**Notifiche di entrata e di uscita della riunione** Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione non verranno informati quando qualcuno entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="34705-118">Quando si attivano le **notifiche di entrata e di uscita della riunione**, è possibile selezionare queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="34705-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="34705-119">**Nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il loro numero di telefono viene riprodotto quando partecipano.</span><span class="sxs-lookup"><span data-stu-id="34705-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="34705-120">**Toni** Quando gli utenti accedono a una riunione, viene riprodotto un tono audio quando partecipano.</span><span class="sxs-lookup"><span data-stu-id="34705-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="34705-121">**Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il nome prima di partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="34705-122">Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre desiderato per il PIN nell'elenco **lunghezza PIN** .</span><span class="sxs-lookup"><span data-stu-id="34705-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="34705-123">Per specificare se inviare messaggi di posta elettronica agli utenti, abilitare o disabilitare automaticamente l'invio di posta elettronica agli **utenti in caso di modifica della configurazione dei**servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="34705-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="34705-124">Vedere i [messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni dei servizi di audioconferenza cambiano in Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o i [messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="34705-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="34705-125">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="34705-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![Icona che mostra il logo di Skype for business](media/sfb-logo-30x30.png)  <span data-ttu-id="34705-127">Utilizzo dell'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="34705-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="34705-128">**Impostare l'esperienza della riunione quando i chiamanti partecipano a una riunione**</span><span class="sxs-lookup"><span data-stu-id="34705-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="34705-129">Nell'interfaccia **di amministrazione di Skype for business**, nella barra di spostamento sinistra \*\*\*\* > , vai a**impostazioni di Microsoft Bridge**per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="34705-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="34705-130">Nella pagina **Impostazioni Bridge Microsoft** , in **esperienza di partecipazione a una riunione**, selezionare:</span><span class="sxs-lookup"><span data-stu-id="34705-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="34705-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="34705-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="34705-132">Se si deseleziona la casella di controllo, gli utenti che hanno già partecipato alla riunione non verranno informati quando qualcuno entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="34705-133">Quando si seleziona **Abilita l'attivazione delle notifiche di entrata e uscita della riunione**, è possibile selezionare queste opzioni nell'elenco **tipo di annuncio di entrata/uscita** :</span><span class="sxs-lookup"><span data-stu-id="34705-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="34705-134">**Nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il loro numero di telefono viene riprodotto quando partecipano.</span><span class="sxs-lookup"><span data-stu-id="34705-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="34705-135">**Toni** Quando gli utenti accedono a una riunione, viene riprodotto un tono audio quando partecipano.</span><span class="sxs-lookup"><span data-stu-id="34705-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="34705-136">**Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="34705-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="34705-137">Se si deseleziona la casella di controllo, ai chiamanti non verrà chiesto di registrare il nome prima di partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="34705-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="34705-138">Vedi **Modificare le impostazioni per un bridge per audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="34705-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="34705-139">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="34705-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="34705-140">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="34705-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="34705-141">Accedere all'interfaccia di **Amministrazione** > di Microsoft 365**Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="34705-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="34705-142">Nell'interfaccia **di amministrazione di Skype for business**, nella barra di spostamento sinistra, \*\*\*\* > Vai a**impostazioni di Microsoft Bridge**per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="34705-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="34705-143">Nella pagina **Impostazioni Bridge Microsoft** , in **sicurezza**, immettere il numero di cifre desiderato per il PIN nell'elenco **lunghezza PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="34705-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="34705-144">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="34705-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="34705-145">**Selezionare se inviare messaggi di posta elettronica agli utenti**</span><span class="sxs-lookup"><span data-stu-id="34705-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="34705-146">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="34705-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="34705-147">Accedere all'interfaccia di **Amministrazione** > di Microsoft 365**Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="34705-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="34705-148">Nell'interfaccia **di amministrazione di Skype for business**, nella barra di spostamento sinistra, \*\*\*\* > Vai a**impostazioni di Microsoft Bridge**per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="34705-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="34705-149">Nella pagina **Impostazioni Bridge Microsoft** selezionare o deselezionare **Invia automaticamente i messaggi di posta elettronica agli utenti se le informazioni di accesso esterno vengono modificate**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="34705-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="34705-150">Vedere i [messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni dei servizi di audioconferenza cambiano in Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o i [messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="34705-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="34705-151">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="34705-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="34705-152">Per risparmiare tempo o automatizzare questo processo, puoi usare il cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .</span><span class="sxs-lookup"><span data-stu-id="34705-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="34705-p107">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="34705-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="34705-156">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="34705-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="34705-157">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34705-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="34705-158">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="34705-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="34705-159">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="34705-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="34705-160">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="34705-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="34705-161">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="34705-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="34705-162">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="34705-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="34705-p109">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="34705-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="34705-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="34705-165">Related topics</span></span>

[<span data-ttu-id="34705-166">Configurare servizi di audioconferenza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34705-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="34705-167">Configurare servizi di audioconferenza per Skype for business online</span><span class="sxs-lookup"><span data-stu-id="34705-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
