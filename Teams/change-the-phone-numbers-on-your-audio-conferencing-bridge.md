---
title: Modificare i numeri di telefono nel bridge per audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sui passaggi necessari per assegnare un nuovo numero di telefono di servizio al bridge di conferenza per espandere la copertura per gli utenti.
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569188"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="b0dd6-103">Cambiare i numeri di telefono del bridge per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b0dd6-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="b0dd6-104">Quando acquisti licenze **per i servizi di audioconferenza,** Microsoft ospita il bridge di audioconferenza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="b0dd6-105">Il bridge per i servizi di audioconferenza fornisce numeri di telefono per l'accesso esterno da diverse località, in modo che organizzatori e partecipanti possano usarli per partecipare alle riunioni Skype for Business o Microsoft Teams con un telefono.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="b0dd6-106">Oltre ai numeri di telefono già assegnati al bridge di conferenza, puoi ottenere numeri di servizio aggiuntivi [(numeri](/microsoftteams/getting-service-phone-numbers) a pedaggio e numeri verde utilizzati per le audioconferenze) da altre località e quindi assegnarli al bridge di conferenza per poter espandere la copertura per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0dd6-107">Per poter assegnare/annullare l'assegnazione di un numero di telefono per un bridge di conferenza, il numero di telefono deve essere un *numero* di ' servizio'.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="b0dd6-108">Per vedere il tipo di numero, passare a Numeri di telefono vocali nell'interfaccia di amministrazione di Microsoft Teams e cercare nella  >   colonna **Tipo di** numero.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="b0dd6-109">I Crediti comunicazioni Microsoft 365 o Office 365 devono essere prima impostati per consentire agli utenti di accedere al bridge con un numero verde.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="b0dd6-110">Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza</span><span class="sxs-lookup"><span data-stu-id="b0dd6-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="b0dd6-111">Passaggio 1 - Assegnare il nuovo numero di telefono al bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b0dd6-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="b0dd6-112">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b0dd6-113">Nel riquadro di spostamento sinistro passa a **Numeri**  >  **di telefono vocali.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="b0dd6-114">Selezionare il numero di telefono nell'elenco e fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="b0dd6-115">Nella pagina **Modifica,** in **Assegnata a,** espandere l'elenco a discesa e selezionare **Applica bridge**  >  **conferenza.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="b0dd6-116">Passaggio 2 - Modificare il numero di telefono predefinito del bridge di conferenza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b0dd6-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="b0dd6-117">Il numero di telefono predefinito del bridge di conferenza definisce l'ID chiamante che verrà utilizzato quando una chiamata in uscita viene effettuato da un partecipante o dall'organizzatore all'interno di una riunione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="b0dd6-118">Solo un numero di servizio a numero verde può essere impostato come numero predefinito per il bridge di conferenza; i numeri di servizio gratuiti non possono essere impostati come numero **predefinito del bridge di conferenza.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="b0dd6-119">Se assegni un numero di servizio a numero verde e desideri impostarlo come nuovo numero predefinito per il bridge di audioconferenza, effettua queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="b0dd6-120">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b0dd6-121">Nel riquadro di spostamento sinistro, passare **a Bridge**  >  **conferenza riunioni.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="b0dd6-122">Evidenziare il numero di servizio a numero verde da configurare come predefinito.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="b0dd6-123">Selezionare **Imposta come predefinito.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="b0dd6-124">Passaggio 3 - Modificare i numeri di telefono predefiniti inclusi negli inviti alle riunioni degli utenti (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b0dd6-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="b0dd6-125">I numeri di telefono predefiniti di un utente sono quelli inclusi nella convocazione di riunione quando pianificano una riunione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="b0dd6-126">Per ulteriori informazioni, tra cui l'assegnazione dei numeri di telefono predefiniti per i nuovi utenti, consulta Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in Skype for Business [online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="b0dd6-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="b0dd6-127">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b0dd6-128">Nel riquadro di spostamento sinistro passare a **Utenti e** fare clic sul nome visualizzato dell'utente desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="b0dd6-129">Accanto a **Audioconferenza,** fai clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="b0dd6-130">In **Numero a verde o** **Numero** verde seleziona il numero nell'elenco a discesa e fai clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="b0dd6-131">Dopo l'applicazione delle modifiche, i nuovi numeri di telefono predefiniti verranno inclusi nelle convocazioni di riunione degli organizzatori la volta successiva che pianificano una nuova riunione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="b0dd6-132">Passaggio 4 - Aggiornare gli inviti alle riunioni esistenti degli utenti che usano il servizio Meeting Migration Service (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b0dd6-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="b0dd6-133">Per i due passaggi successivi, è necessario iniziare a Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="b0dd6-134">Se sono stati aggiornati i numeri di telefono predefiniti inclusi negli inviti alle riunioni per alcuni o tutti gli utenti, è possibile aggiornare gli inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i loro numeri di telefono predefiniti siano stati modificati mediante il servizio Meeting Migration Service.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="b0dd6-135">Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="b0dd6-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="b0dd6-136">Eseguire il servizio MMS (Meeting Migration Service) per gli utenti che hanno modificato i numeri di telefono predefiniti nel Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="b0dd6-137">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="b0dd6-138">È inoltre possibile visualizzare lo stato della migrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="b0dd6-139">Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .</span><span class="sxs-lookup"><span data-stu-id="b0dd6-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="b0dd6-140">Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza</span><span class="sxs-lookup"><span data-stu-id="b0dd6-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="b0dd6-141">Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="b0dd6-142">Dato che il numero di telefono cambia, è importante aggiornare tutti gli utenti che potrebbero avere un numero di telefono come numero predefinito (se presente) e aggiornare gli inviti alle riunioni esistenti prima che l'assegnazione del numero di telefono al bridge di audioconferenza abbia un'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="b0dd6-143">Se il numero di telefono viene rimosso senza aggiornare gli utenti e le loro riunioni, gli inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="b0dd6-144">Per i tre passi successivi, è necessario avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="b0dd6-145">Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="b0dd6-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="b0dd6-146">Passo 1 - Aggiornare gli utenti che hanno il numero di telefono da annullare l'assegnazione come uno dei loro numeri predefiniti</span><span class="sxs-lookup"><span data-stu-id="b0dd6-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="b0dd6-147">Sostituire il numero a numero verde o a numero verde predefinito per tutti gli utenti che hanno come numero predefinito il numero da annullare e avviare il processo di ripianificazione delle loro riunioni.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="b0dd6-148">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="b0dd6-149">Puoi anche modificare il numero a numero verde o a numero verde predefinito di utenti nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b0dd6-150">Tuttavia, questa azione non riprogrammerà automaticamente le riunioni.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="b0dd6-151">Per ulteriori informazioni, consulta Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in Skype for Business [online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="b0dd6-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0dd6-152">A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="b0dd6-153">Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0dd6-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="b0dd6-154">Tutte le riunioni verranno ripianificate una volta che non ci saranno operazioni in *sospeso* o *in* corso.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="b0dd6-155">Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="b0dd6-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="b0dd6-156">Passo 3 - Annullare l'assegnazione del vecchio numero di telefono dal bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b0dd6-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="b0dd6-157">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b0dd6-158">Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="b0dd6-159">Se il numero di telefono è un numero verde, seleziona il numero di telefono nell'elenco e fai clic su **Rilascia.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="b0dd6-160">Se il numero di telefono è a numero verde, contatta il [supporto Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) per ottenere l'annullamento dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="b0dd6-161">Se il numero di telefono è un numero verde, fai clic su **Sì** nella finestra di conferma.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b0dd6-162">Dopo l'annullamento dell'assegnazione di un numero di telefono da un bridge per audioconferenza, il numero di telefono non sarà più disponibile per gli utenti per partecipare a riunioni nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="b0dd6-163">Risparmiare tempo e automatizzare</span><span class="sxs-lookup"><span data-stu-id="b0dd6-163">Save time and automate</span></span>

<span data-ttu-id="b0dd6-164">Per risparmiare tempo automatizzando questo processo, puoi utilizzare i cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="b0dd6-165">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-165">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="b0dd6-166">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="b0dd6-167">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0dd6-168">Per trovare il BridgeID, usa **Il Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="b0dd6-169">Per modificare il numero verde predefinito di tutti gli utenti a cui ne manca uno in 8005551234, esegui:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="b0dd6-170">Per modificare il numero verde predefinito di tutti gli utenti che hanno 8005551234 come numero verde predefinito in 8005551239 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="b0dd6-171">Per modificare il numero verde predefinito di tutti gli utenti con sede negli USA in 8005551234 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="b0dd6-172">La posizione usata sopra deve corrispondere alle informazioni di contatto degli utenti impostate nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b0dd6-173">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b0dd6-173">Troubleshooting</span></span>

<span data-ttu-id="b0dd6-174">**Il pulsante Annulla assegnazione non è disponibile**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="b0dd6-175">Si vuole annullare l'assegnazione di un numero, ma il pulsante non è disponibile e, se si passa il mouse su di esso, si viene reindirizzati a contattare il supporto con il messaggio seguente "Non è possibile annullare l'assegnazione di numeri predefiniti o condivisi dal _bridge. Per annullare l'assegnazione dei numeri a verde dedicati, contatta il supporto._".</span><span class="sxs-lookup"><span data-stu-id="b0dd6-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="b0dd6-176">Per ottenere altre informazioni sui bridge, eseguire powershell seguente:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="b0dd6-177">Il risultato, oltre ad altre informazioni come Identity, Name e Region, deve contenere anche DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="b0dd6-178">**Ad** esempio, per annullare l'assegnazione, defaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="b0dd6-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="b0dd6-179">Informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0dd6-179">About Windows PowerShell</span></span>

<span data-ttu-id="b0dd6-180">Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="b0dd6-181">Windows PowerShell consente di gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano, soprattutto quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="b0dd6-182">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b0dd6-183">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b0dd6-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="b0dd6-184">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="b0dd6-184">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="b0dd6-185">Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b0dd6-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b0dd6-186">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b0dd6-186">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b0dd6-187">Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="b0dd6-187">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="b0dd6-188">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b0dd6-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="b0dd6-189">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b0dd6-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="b0dd6-190">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b0dd6-190">Related topics</span></span>
[<span data-ttu-id="b0dd6-191">Modificare le impostazioni per un bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b0dd6-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
