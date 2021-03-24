---
title: Modificare i numeri di telefono nel bridge di audioconferenza
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
description: Informazioni sui passaggi necessari per assegnare un nuovo numero di telefono del servizio al bridge di conferenza per espandere la copertura per gli utenti.
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102662"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="142f8-103">Cambiare i numeri di telefono del bridge per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="142f8-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="142f8-104">Quando si acquistano licenze **di audioconferenza,** Microsoft ospita il bridge di audioconferenza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="142f8-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="142f8-105">Il bridge di audioconferenza fornisce numeri di telefono con accesso esterno da posizioni diverse, in modo che gli organizzatori e i partecipanti possano usarli per partecipare alle riunioni Skype for Business o Microsoft Teams con un telefono.</span><span class="sxs-lookup"><span data-stu-id="142f8-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="142f8-106">Oltre ai numeri di telefono già assegnati al bridge di conferenza, è possibile ottenere altri numeri di servizio [(numeri](./getting-service-phone-numbers.md) a numero verde e a numero verde usati per le audioconferenze) da altre posizioni e quindi assegnarli al bridge di conferenza in modo da espandere la copertura per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="142f8-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](./getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="142f8-107">Per poter assegnare/annullare l'assegnazione di un numero di telefono per un bridge di conferenza, il numero di telefono deve essere un *numero* di servizio.</span><span class="sxs-lookup"><span data-stu-id="142f8-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="142f8-108">Per visualizzare il tipo di numero, passare a Numeri di telefono vocale nell'interfaccia di amministrazione di Microsoft Teams e cercare  >   nella colonna **Tipo di** numero.</span><span class="sxs-lookup"><span data-stu-id="142f8-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="142f8-109">I crediti per le comunicazioni di Microsoft 365 o Office 365 devono essere impostati per primi per consentire agli utenti di accedere al bridge su un numero verde.</span><span class="sxs-lookup"><span data-stu-id="142f8-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="142f8-110">Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza</span><span class="sxs-lookup"><span data-stu-id="142f8-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="142f8-111">Passaggio 1 - Assegnare il nuovo numero di telefono al bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="142f8-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="142f8-112">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="142f8-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="142f8-113">Nel riquadro di spostamento sinistro passare a **Numeri di telefono**  >  **vocale.**</span><span class="sxs-lookup"><span data-stu-id="142f8-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="142f8-114">Selezionare il numero di telefono nell'elenco e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="142f8-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="142f8-115">Nella pagina **Modifica,** in **Assegnato a,** espandere l'elenco a discesa e quindi selezionare **Bridge di**  >  **conferenza Applica.**</span><span class="sxs-lookup"><span data-stu-id="142f8-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="142f8-116">Passaggio 2 - Modificare il numero di telefono predefinito del bridge di conferenza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="142f8-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="142f8-117">Il numero di telefono predefinito del bridge di conferenza definisce l'ID chiamante che verrà usato quando un partecipante o l'organizzatore esegue una chiamata in uscita all'interno di una riunione.</span><span class="sxs-lookup"><span data-stu-id="142f8-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="142f8-118">È possibile impostare come numero predefinito per il bridge di conferenza solo un numero a pedaggio del servizio. I numeri verde del servizio non possono essere impostati **come numero predefinito del bridge di conferenza.**</span><span class="sxs-lookup"><span data-stu-id="142f8-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="142f8-119">Se si sta assegnando un numero a pedaggio del servizio e si vuole impostarlo come nuovo numero predefinito per il bridge di audioconferenza, eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="142f8-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="142f8-120">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="142f8-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="142f8-121">Nel riquadro di spostamento sinistro passare a **Ponti**  >  **conferenza riunioni**.</span><span class="sxs-lookup"><span data-stu-id="142f8-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="142f8-122">Evidenziare il numero a pedaggio del servizio che si vuole configurare come predefinito.</span><span class="sxs-lookup"><span data-stu-id="142f8-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="142f8-123">Selezionare **Imposta come predefinito.**</span><span class="sxs-lookup"><span data-stu-id="142f8-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="142f8-124">Passaggio 3 - Modificare i numeri di telefono predefiniti inclusi negli inviti alla riunione degli utenti (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="142f8-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="142f8-125">I numeri di telefono predefiniti di un utente sono quelli inclusi nelle convocazioni di riunione quando pianificano una riunione.</span><span class="sxs-lookup"><span data-stu-id="142f8-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="142f8-126">Per altre informazioni, inclusa la modalità di assegnazione dei numeri di telefono predefiniti per i nuovi utenti, vedere Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in Skype for Business [online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="142f8-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="142f8-127">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="142f8-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="142f8-128">Nel riquadro di spostamento sinistro passare a **Utenti** e fare clic sul nome visualizzato dell'utente desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="142f8-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="142f8-129">Accanto a **Audioconferenza** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="142f8-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="142f8-130">In **Numero verde o** **Numero** verde selezionare il numero nell'elenco a discesa e fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="142f8-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="142f8-131">Dopo l'applicazione delle modifiche, i nuovi numeri di telefono predefiniti verranno inclusi nelle convocazioni di riunione degli organizzatori alla successiva pianificazione di una nuova riunione.</span><span class="sxs-lookup"><span data-stu-id="142f8-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="142f8-132">Passaggio 4 - Aggiornare gli inviti a riunioni esistenti degli utenti usando il servizio di migrazione delle riunioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="142f8-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="142f8-133">Per i due passaggi successivi, è necessario iniziare a Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="142f8-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="142f8-134">Se sono stati aggiornati i numeri di telefono predefiniti inclusi negli inviti alla riunione per alcuni o tutti gli utenti, è possibile aggiornare facoltativamente gli inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i numeri di telefono predefiniti siano stati modificati con il servizio di migrazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="142f8-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="142f8-135">Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="142f8-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="142f8-136">Eseguire il servizio di migrazione delle riunioni (MMS) per gli utenti che hanno modificato i numeri di telefono predefiniti nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="142f8-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="142f8-137">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="142f8-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="142f8-138">È inoltre possibile visualizzare lo stato della migrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="142f8-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="142f8-139">Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .</span><span class="sxs-lookup"><span data-stu-id="142f8-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="142f8-140">Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza</span><span class="sxs-lookup"><span data-stu-id="142f8-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="142f8-141">Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="142f8-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="142f8-142">Poiché il numero di telefono cambia, è importante aggiornare tutti gli utenti che potrebbero avere un numero di telefono come numero predefinito (se presente) e aggiornare gli inviti alle riunioni esistenti prima che il numero di telefono non sia assegnato dal bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="142f8-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="142f8-143">Se il numero di telefono viene rimosso senza aggiornare gli utenti e le riunioni, gli inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="142f8-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="142f8-144">Per i tre passi successivi, è necessario avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="142f8-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="142f8-145">Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="142f8-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="142f8-146">Passaggio 1 - Aggiornare gli utenti che hanno il numero di telefono da annullare l'assegnazione come uno dei numeri predefiniti</span><span class="sxs-lookup"><span data-stu-id="142f8-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="142f8-147">Sostituire il numero verde o a pedaggio predefinito per tutti gli utenti che hanno il numero da annullare l'assegnazione come numero predefinito e avviare il processo di riprogrammazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="142f8-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="142f8-148">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="142f8-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="142f8-149">È anche possibile modificare il numero verde o a numero verde predefinito di utenti nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="142f8-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="142f8-150">Tuttavia, questa azione non riprogrammerà automaticamente le riunioni.</span><span class="sxs-lookup"><span data-stu-id="142f8-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="142f8-151">Per altre informazioni, vedere Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in Skype for Business [online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="142f8-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="142f8-152">A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="142f8-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="142f8-153">Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="142f8-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="142f8-154">Tutte le riunioni verranno riprogrammate quando non sono presenti operazioni *in* stato In sospeso *o In* corso.</span><span class="sxs-lookup"><span data-stu-id="142f8-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="142f8-155">Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="142f8-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="142f8-156">Passaggio 3 - Annullare l'assegnazione del vecchio numero di telefono dal bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="142f8-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="142f8-157">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="142f8-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="142f8-158">Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="142f8-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="142f8-159">Se il numero di telefono è un numero verde, selezionare il numero nell'elenco e fare clic su **Rilascia**.</span><span class="sxs-lookup"><span data-stu-id="142f8-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="142f8-160">Se il numero di telefono è a numero verde, contattare il [supporto tecnico Microsoft](/microsoft-365/admin/contact-support-for-business-products) per avere il numero di telefono non assegnato.</span><span class="sxs-lookup"><span data-stu-id="142f8-160">If the phone number is a toll number, please contact [Microsoft support](/microsoft-365/admin/contact-support-for-business-products) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="142f8-161">Se il numero di telefono è un numero verde, fare clic su **Sì** nella finestra di conferma.</span><span class="sxs-lookup"><span data-stu-id="142f8-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="142f8-162">Dopo che un numero di telefono non è stato assegnato da un bridge di audioconferenza, il numero di telefono non sarà più disponibile per gli utenti per partecipare a riunioni nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="142f8-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="142f8-163">Risparmiare tempo e automatizzare</span><span class="sxs-lookup"><span data-stu-id="142f8-163">Save time and automate</span></span>

<span data-ttu-id="142f8-164">Per risparmiare tempo automatizzando questo processo, è possibile usare i cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="142f8-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="142f8-165">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="142f8-165">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="142f8-166">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="142f8-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="142f8-167">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="142f8-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="142f8-168">Per trovare bridgeID, usare **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="142f8-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="142f8-169">Per modificare il numero verde predefinito di tutti gli utenti a cui ne manca uno in 8005551234, esegui:</span><span class="sxs-lookup"><span data-stu-id="142f8-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="142f8-170">Per modificare il numero verde predefinito di tutti gli utenti che hanno 8005551234 come numero verde predefinito in 8005551239 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="142f8-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="142f8-171">Per modificare il numero verde predefinito di tutti gli utenti con sede negli USA in 8005551234 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="142f8-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="142f8-172">La posizione usata sopra deve corrispondere alle informazioni di contatto degli utenti impostate nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="142f8-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="142f8-173">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="142f8-173">Troubleshooting</span></span>

<span data-ttu-id="142f8-174">**Il pulsante Annulla assegnazione non è disponibile**</span><span class="sxs-lookup"><span data-stu-id="142f8-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="142f8-175">Si vuole annullare l'assegnazione di un numero ma il pulsante non è disponibile e, se si passa il puntatore del mouse su di esso, si viene reindirizzati a contattare il supporto con il messaggio seguente: "I numeri predefiniti o condivisi non possono essere non assegnati dal _bridge. Per annullare l'assegnazione di numeri a pedaggio dedicati, contattare il supporto._".</span><span class="sxs-lookup"><span data-stu-id="142f8-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="142f8-176">Per ottenere altre informazioni sui bridge, eseguire powershell seguente:</span><span class="sxs-lookup"><span data-stu-id="142f8-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="142f8-177">Il risultato, oltre ad altre informazioni come Identity, Name e Region, deve contenere anche DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="142f8-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="142f8-178">**Esempio,** per annullare l'assegnazione, defaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="142f8-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="142f8-179">Informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="142f8-179">About Windows PowerShell</span></span>

<span data-ttu-id="142f8-180">Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no.</span><span class="sxs-lookup"><span data-stu-id="142f8-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="142f8-181">Windows PowerShell può aiutarti a gestire Microsoft 365 o Office 365 e Skype for Business online usando un unico punto di amministrazione che può semplificare il lavoro quotidiano, soprattutto quando hai più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="142f8-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="142f8-182">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="142f8-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="142f8-183">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="142f8-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="142f8-184">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="142f8-184">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

<span data-ttu-id="142f8-185">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="142f8-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="142f8-186">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="142f8-186">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="142f8-187">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="142f8-187">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="142f8-188">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="142f8-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="142f8-189">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="142f8-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="142f8-190">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="142f8-190">Related topics</span></span>
[<span data-ttu-id="142f8-191">Modificare le impostazioni per un bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="142f8-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)