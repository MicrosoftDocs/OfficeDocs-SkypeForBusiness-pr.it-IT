---
title: Cambiare i numeri di telefono del bridge per i servizi di audioconferenza
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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: When you buy Audio Conferencing licenses, Microsoft is hosting your audio conferencing bridge for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.
ms.openlocfilehash: 60095ff820c6aeb13745f5195a6274fa90f5eec0
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184357"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="d3c06-104">Cambiare i numeri di telefono del bridge per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3c06-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="d3c06-105">Quando si acquistano le licenze per i servizi di audioconferenza, Microsoft ospita il Bridge per audioconferenza per l'organizzazione. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d3c06-105">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="d3c06-106">Il Bridge per i servizi di audioconferenza offre numeri di telefono con accesso esterno provenienti da posizioni diverse in modo che gli organizzatori e i partecipanti possano usarli per partecipare alle riunioni di Skype for business o Microsoft teams con un telefono.</span><span class="sxs-lookup"><span data-stu-id="d3c06-106">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="d3c06-107">Oltre ai numeri di telefono già assegnati al Bridge per i servizi di conferenza, è possibile [ottenere i numeri di servizio aggiuntivi](/microsoftteams/getting-service-phone-numbers) (numero verde e numeri verdi usati per le conferenze audio) da altre posizioni e quindi assegnarli al Bridge di conferenza in modo da poter espandere la copertura per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d3c06-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3c06-108">Per poter assegnare o annullare l'assegnazione di un numero di telefono per un Bridge per i servizi di conferenza, il numero di telefono deve essere un numero di*servizio*.</span><span class="sxs-lookup"><span data-stu-id="d3c06-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="d3c06-109">Per visualizzare il tipo di numero, è possibile spostarsi in numeri di \*\*\*\* > **telefono** vocale nel portale legacy e cercare nella colonna tipo di **numero** .</span><span class="sxs-lookup"><span data-stu-id="d3c06-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the legacy portal and looking in the **Number Type** column.</span></span> <span data-ttu-id="d3c06-110">Bisogna prima impostare il Credito per la comunicazione di Office 365 per consentire agli utenti di accedere al ponte per audioconferenze su un numero verde.</span><span class="sxs-lookup"><span data-stu-id="d3c06-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="d3c06-111">Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza</span><span class="sxs-lookup"><span data-stu-id="d3c06-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="d3c06-112">Passaggio 1-assegnare il nuovo numero di telefono al Bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3c06-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="d3c06-113">Accedi a Office 365 con l'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="d3c06-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="d3c06-114">Accedere a teams di interfaccia di amministrazione di interfaccia di amministrazione di **Microsoft 365** > \*\*\*\* > **&** > **numeri di telefono\*\*\*\*vocali** > del**portale** > legacy Skype.</span><span class="sxs-lookup"><span data-stu-id="d3c06-114">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="d3c06-115">Selezionare il numero di telefono nell'elenco, quindi fare clic su **assegna**nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d3c06-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="d3c06-116">Sulla pagina **Assegna**, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-116">On the **Assign** page, click **Save**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="d3c06-117">Passaggio 2: cambiare il numero di telefono predefinito del Bridge di conferenza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d3c06-117">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="d3c06-118">Il numero di telefono predefinito del Bridge conferenza definisce l'ID chiamante che verrà usato quando una chiamata in uscita viene inserita da un partecipante o dall'organizzatore all'interno di una riunione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-118">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="d3c06-119">Solo un numero a pagamento del servizio può essere impostato come numero predefinito per il Bridge per i servizi di conferenza; **i numeri verdi del servizio non possono essere impostati come numero predefinito del Bridge per i servizi di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-119">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="d3c06-120">Se si sta assegnando un numero di servizio a pagamento e si vuole impostarlo come nuovo numero predefinito per il Bridge di audioconferenza, eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="d3c06-120">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

1. <span data-ttu-id="d3c06-121">Accedi a Office 365 con l'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="d3c06-121">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="d3c06-122">Vai all'interfaccia di amministrazione di interfaccia di amministrazione di **Microsoft 365** > \*\*\*\* > **&** > \*\*\*\* > **ponti conferenza**riunioni Skype.</span><span class="sxs-lookup"><span data-stu-id="d3c06-122">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="d3c06-123">Evidenziare il numero a pagamento del servizio che si vuole configurare come predefinito.</span><span class="sxs-lookup"><span data-stu-id="d3c06-123">Highlight the service toll number that you want to configure as the default.</span></span>

4. <span data-ttu-id="d3c06-124">Selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-124">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="d3c06-125">Passaggio 3-modificare i numeri di telefono predefiniti inclusi negli inviti alla riunione degli utenti (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d3c06-125">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="d3c06-126">I numeri di telefono predefiniti di un utente sono quelli inclusi negli inviti alla riunione quando pianificano una riunione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-126">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="d3c06-127">Per altre informazioni, incluso il modo in cui vengono assegnati i numeri di telefono di defaul per i nuovi utenti, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [impostare i numeri di telefono inclusi negli inviti in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="d3c06-127">For more information, including how the defaul phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="d3c06-128">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-128">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d3c06-129">Accedere ai team di**Amministrazione** > dell'interfaccia di amministrazione di **Microsoft 365** > &**agli utenti**di servizi di**audioconferenza** > di**Skype** > **legacy Portal** > e selezionare gli utenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d3c06-129">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users**, and select the users on the list.</span></span>

3. <span data-ttu-id="d3c06-130">Nel riquadro Azione, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-130">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="d3c06-131">In numero a **pagamento predefinito** o **numero verde predefinito**Selezionare il numero nell'elenco e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-131">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="d3c06-132">Dopo aver salvato le modifiche, i nuovi numeri di telefono predefiniti verranno inclusi nella riunione invita gli organizzatori la volta successiva che pianificano una nuova riunione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-132">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="d3c06-133">Passaggio 4-aggiornare gli inviti alle riunioni esistenti degli utenti che usano il servizio di migrazione delle riunioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d3c06-133">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="d3c06-134">Per i due passaggi successivi sarà necessario avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3c06-134">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="d3c06-135">Se sono stati aggiornati i numeri di telefono predefiniti inlcuded nella riunione invita per alcuni o tutti gli utenti, è possibile facoltativamente aggiornare gli inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i numeri di telefono predefiniti vengano modificati usando il Servizio di migrazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3c06-135">If you updated the default phone numbers that are inlcuded in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="d3c06-136">Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="d3c06-136">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="d3c06-137">Eseguire il servizio di migrazione delle riunioni (MMS) per gli utenti che avevano i numeri di telefono predefiniti modificati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d3c06-137">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="d3c06-138">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d3c06-138">To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="d3c06-139">È inoltre possibile visualizzare lo stato della migrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-139">You can also view the meeting migration status.</span></span> <span data-ttu-id="d3c06-140">Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .</span><span class="sxs-lookup"><span data-stu-id="d3c06-140">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="d3c06-141">Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza</span><span class="sxs-lookup"><span data-stu-id="d3c06-141">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="d3c06-142">Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="d3c06-142">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="d3c06-143">Poiché il numero di telefono cambia, è importante aggiornare tutti gli utenti che potrebbero avere un numero di telefono come numero predefinito (se disponibile) e aggiornare gli inviti alle riunioni esistenti prima che il numero di telefono venga assegnato dal Bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="d3c06-143">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="d3c06-144">Se il numero di telefono viene rimosso senza aggiornare gli utenti e le relative riunioni, gli inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3c06-144">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="d3c06-145">Per i tre passi successivi, è necessario avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3c06-145">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="d3c06-146">Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="d3c06-146">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="d3c06-147">Passaggio 1-aggiornare gli utenti che hanno il numero di telefono per non essere assegnati come uno dei numeri predefiniti</span><span class="sxs-lookup"><span data-stu-id="d3c06-147">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="d3c06-148">Sostituire il numero verde o a pagamento predefinito per tutti gli utenti che hanno il numero da non assegnare come numero predefinito e avviare il processo di ripianificazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3c06-148">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="d3c06-149">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d3c06-149">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="d3c06-150">È anche possibile modificare il numero verde o il pedaggio predefinito degli utenti nell'interfaccia di amministrazione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="d3c06-150">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="d3c06-151">Tuttavia, questa azione non riprogrammerà automaticamente le riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3c06-151">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="d3c06-152">Per altre informazioni, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [impostare i numeri di telefono inclusi negli inviti in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="d3c06-152">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d3c06-153">A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="d3c06-153">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="d3c06-154">Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3c06-154">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="d3c06-155">Tutte le riunioni verranno ripianificate quando non ci sono operazioni in stato in *sospeso* o *in corso* .</span><span class="sxs-lookup"><span data-stu-id="d3c06-155">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="d3c06-156">Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="d3c06-156">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="d3c06-157">Passaggio 3-annullare l'assegnazione del vecchio numero di telefono dal Bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3c06-157">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="d3c06-158">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-158">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d3c06-159">Accedere ai team di interfaccia\*\*\*\* > di amministrazione di interfaccia di amministrazione di **Microsoft 365** > & i**numeri di telefono\*\*\*\*vocali** > del**portale** > legacy**Skype** > .</span><span class="sxs-lookup"><span data-stu-id="d3c06-159">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="d3c06-160">Se il numero di telefono è un numero verde, selezionare il numero di telefono nell'elenco e quindi fare clic su **Annulla assegnazione**nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d3c06-160">If the phone number is a toll-free number, select the phone number from the list, and in the Action pane, click **Unassign**.</span></span> <span data-ttu-id="d3c06-161">Se il numero di telefono è un numero a pagamento, contattare il [supporto Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) per ottenere il numero di telefono non assegnato.</span><span class="sxs-lookup"><span data-stu-id="d3c06-161">If the phone number is a toll-number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

4. <span data-ttu-id="d3c06-162">Se il numero di telefono è un numero a pagamento, fare clic su **Sì** nella finestra di conferma.</span><span class="sxs-lookup"><span data-stu-id="d3c06-162">If the phone number is a toll-fre number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d3c06-163">Dopo che un numero di telefono non è stato assegnato da un Bridge per i servizi di audioconferenza, il numero di telefono non sarà più disponibile per consentire agli utenti di partecipare a riunioni nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="d3c06-163">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d3c06-164">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d3c06-164">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="d3c06-165"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="d3c06-165"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="d3c06-166">Per verificare se Windows PowerShell è pronto</span><span class="sxs-lookup"><span data-stu-id="d3c06-166">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="d3c06-167">Questa procedura consente di verificare che sia in esecuzione Windows PowerShell versione 3,0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="d3c06-167">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="d3c06-168">Digita **Menu di avvio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-168">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="d3c06-169">Digita _Get-Host_ nella finestra di **Windows PowerShell** per verificare la versione.</span><span class="sxs-lookup"><span data-stu-id="d3c06-169">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="d3c06-170">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3c06-170">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="d3c06-171">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="d3c06-171">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="d3c06-172">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d3c06-172">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="d3c06-173">È inoltre necessario installare il modulo Windows PowerShell per Skype for business online che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="d3c06-173">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="d3c06-174">Questo modulo è supportato solo in computer a 64 bit e può essere scaricato dall'area download Microsoft nel [modulo di Windows PowerShell per Skype for business online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="d3c06-174">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="d3c06-175">Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d3c06-175">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="d3c06-176">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="d3c06-176">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="d3c06-177">Per avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3c06-177">To start Windows PowerShell</span></span>

 <span data-ttu-id="d3c06-178">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d3c06-178">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="d3c06-179">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-179">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="d3c06-180">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="d3c06-180">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="d3c06-181">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="d3c06-181">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="d3c06-182">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o connettersi [a Skype for business online tramite Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d3c06-182">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="d3c06-183">Risparmiare tempo e automatizzare</span><span class="sxs-lookup"><span data-stu-id="d3c06-183">Save time and automate</span></span>

<span data-ttu-id="d3c06-184">Per risparmiare tempo automatizzando questo processo, è possibile usare i cmdlet [set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **set-CsOnlineDialInConferencingUserDefaultNumber** .</span><span class="sxs-lookup"><span data-stu-id="d3c06-184">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="d3c06-185">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="d3c06-185">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="d3c06-186">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="d3c06-186">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="d3c06-187">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="d3c06-187">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3c06-188">Per trovare il BridgeID, usa il **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="d3c06-188">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="d3c06-189">Per modificare il numero verde predefinito di tutti gli utenti a cui ne manca uno in 8005551234, esegui:</span><span class="sxs-lookup"><span data-stu-id="d3c06-189">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="d3c06-190">Per modificare il numero verde predefinito di tutti gli utenti che hanno 8005551234 come numero verde predefinito in 8005551239 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="d3c06-190">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="d3c06-191">Per modificare il numero verde predefinito di tutti gli utenti con sede negli USA in 8005551234 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="d3c06-191">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="d3c06-192">La posizione usata sopra deve corrispondere alle informazioni di contatto degli utenti impostati nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3c06-192">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d3c06-193">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d3c06-193">Troubleshooting</span></span>

<span data-ttu-id="d3c06-194">**Pulsante Annulla assegnazione in grigio**</span><span class="sxs-lookup"><span data-stu-id="d3c06-194">**Unassign button is greyed-out**</span></span>

<span data-ttu-id="d3c06-195">Si vuole annullare l'assegnazione di un numero ma il pulsante è in grigio e se durante l'aspirapolvere viene reindirizzato al supporto per il contatto con il messaggio seguente _"i numeri predefiniti o condivisi possono ´ non essere assegnati dal Bridge. Per annullare l'assegnazione di numeri a pedaggio dedicati, contattare il supporto tecnico._".</span><span class="sxs-lookup"><span data-stu-id="d3c06-195">You want to Unassign a number but the button is greyed-out and if while hoovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="d3c06-196">Per ottenere altre informazioni sui Bridge, eseguire la seguente PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d3c06-196">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="d3c06-197">Il risultato, oltre ad altre informazioni come l'identità, il nome e l'area geografica, dovrebbe contenere anche il DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="d3c06-197">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="d3c06-198">Ad **esempio**, per annullare l'assegnazione, DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="d3c06-198">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="d3c06-199">Informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3c06-199">About Windows PowerShell</span></span>

<span data-ttu-id="d3c06-200">Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no.</span><span class="sxs-lookup"><span data-stu-id="d3c06-200">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="d3c06-201">Windows PowerShell consente di gestire Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, in particolare quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d3c06-201">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="d3c06-202">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="d3c06-202">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d3c06-203">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d3c06-203">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="d3c06-204">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="d3c06-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="d3c06-205">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d3c06-205">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d3c06-206">Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3c06-206">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d3c06-207">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="d3c06-207">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="d3c06-208">Usare Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d3c06-208">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="d3c06-209">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d3c06-209">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="d3c06-210">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d3c06-210">Related topics</span></span>
[<span data-ttu-id="d3c06-211">Modificare le impostazioni per un bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3c06-211">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
