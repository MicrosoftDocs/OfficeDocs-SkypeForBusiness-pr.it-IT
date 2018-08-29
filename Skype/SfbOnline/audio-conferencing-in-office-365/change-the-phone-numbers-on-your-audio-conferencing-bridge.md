---
title: Cambiare i numeri di telefono del ponte per audioconferenze
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Quando si acquistano le licenze di Audioconferenza, Microsoft ospita il ponte per audioconferenze per la propria organizzazione. Il ponte per audioconferenze assegna numeri di telefono per accesso esterno da diverse località per consentire ad organizzatori di riunioni e partecipanti di usarli per partecipare alle riunioni usando un telefono.
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255712"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="59019-104">Cambiare i numeri di telefono del ponte per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="59019-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="59019-105">Quando si acquistano le licenze di **Audioconferenza**, Microsoft ospita il *ponte per audioconferenze* per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="59019-105">When you buy **Skype for Business PSTN Conferencing** licenses, Microsoft is hosting a *conferencing bridge*  for your organization.</span></span> <span data-ttu-id="59019-106">Il ponte per audioconferenze assegna numeri di telefono per accesso esterno da diverse località per consentire ad organizzatori di riunioni e partecipanti di usarli per partecipare alle riunioni usando un telefono.</span><span class="sxs-lookup"><span data-stu-id="59019-106">The conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join meetings using a phone.</span></span>

<span data-ttu-id="59019-107">Oltre ai numeri di telefono già assegnati al ponte per conferenze audio, è possibile [ottenere i numeri di servizio aggiuntivi](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (numeri a pagamento e numeri verdi utilizzati per le audioconferenze) da altri percorsi e di assegnarli al ponte per audioconferenza in modo da poter estendere la copertura per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="59019-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [Getting Skype for Business service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (toll and toll-free numbers used for dial-in conferencing) from other locations and then assign them to the conferencing bridge so you can expand the area/country/region coverage for your users.</span></span>

> [!NOTE]
> <span data-ttu-id="59019-108">Per potere assegnare/annullare l'assegnazione di un numero di telefono per un ponte per audioconferenze, il numero di telefono deve essere un numero di "*servizio*".</span><span class="sxs-lookup"><span data-stu-id="59019-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a 'service' number.</span></span> <span data-ttu-id="59019-109">È possibile visualizzare il tipo di numero navigando su **Voce** > **Numeri di telefono** e guardando nella colonna **Tipo di numero**.</span><span class="sxs-lookup"><span data-stu-id="59019-109">You can see the type of number it is by using the **Voice** > **Phone numbers** tab and look under the **Number Type** column.</span></span> <span data-ttu-id="59019-110">Bisogna prima impostare il Credito per la comunicazione di Office 365 per consentire agli utenti di accedere al ponte per audioconferenze su un numero verde.</span><span class="sxs-lookup"><span data-stu-id="59019-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="59019-111">Istruzioni per assegnare un numero telefonico di servizio al tuo ponte per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="59019-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="59019-112">Passo 1 - Assegnare il nuovo numero di telefono al ponte per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="59019-112">Step 1 - Assign the new phone number to your conferencing bridge</span></span>

1. <span data-ttu-id="59019-113">Accedi a Office 365 con l'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="59019-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="59019-114">Vai all' **interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Voce** > **Numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="59019-114">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="59019-115">Seleziona il numero di telefono dall'elenco, e nel riquadro Azioni, fai clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="59019-115">Select the phone number from the list and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="59019-116">Sulla pagina **Assegna**, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="59019-116">On the **Assign** page, click **Save**.</span></span>

    <span data-ttu-id="59019-117">Solo un numero di servizio a pagamento può essere impostato come numero predefinito per il ponte per audioconferenze; **i numeri di servizio gratuiti non possono essere impostati come numero predefinito del ponte per audioconferenze**.</span><span class="sxs-lookup"><span data-stu-id="59019-117">Only a service toll number can be set as the default number for your conferencing bridge, **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="59019-118">Se assegni un numero di servizio a pagamento e desideri impostarlo come nuovo numero predefinito per il ponte per audioconferenze, seleziona **Utilizza questo numero come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="59019-118">If you are assigning a service toll number and you would like to set it as the new default number for your conferencing bridge, check **Use this number as the default**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59019-119">Una volta assegnato un nuovo numero di telefono, anche se il numero è diventato il nuovo numero predefinito, il numero predefinito per gli utenti esistenti non cambierà.</span><span class="sxs-lookup"><span data-stu-id="59019-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="59019-120">Per impostare il numero a pagamento o verde predefinito che viene aggiunto agli inviti alla riunione di un organizzatore, consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="59019-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="59019-121">Passo 2 - Cambiare i numeri di telefono predefiniti inclusi negli inviti alle riunioni degli utenti (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="59019-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="59019-122">I numeri di telefono predefiniti per gli utenti sono quelli inclusi nell'invito alla riunione quando essi pianificano una riunione.</span><span class="sxs-lookup"><span data-stu-id="59019-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="59019-123">Per ulteriori informazioni, consulta[Impostare i numeri di telefono numeri inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="59019-123">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

1. <span data-ttu-id="59019-124">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="59019-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="59019-125">Vai all'**interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Audioconferenza** > **Utenti** e seleziona gli utenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="59019-125">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Dial-in conferencing** > **Dial-in users** and find the users in the list.</span></span>

3. <span data-ttu-id="59019-126">Nel riquadro Azione, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="59019-126">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="59019-127">Alla voce**Numero a pagamento predefinito** o **Numero verde predefinito**, seleziona il numero nella lista e fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="59019-127">Under ** Default toll number** or Default toll-free number, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="59019-128">Una volta salvate le modifiche, i nuovi numeri di telefono predefiniti saranno inclusi negli inviti alle riunioni degli organizzatori la prossima volta che pianificheranno una nuova riunione.</span><span class="sxs-lookup"><span data-stu-id="59019-128">Once the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="59019-129">Passo 3 - Aggiornare gli inviti alle riunioni esistenti degli utenti che utilizzano il servizio MMS (Meeting Migration Service) (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="59019-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="59019-130">Per i due passaggi successivi, è necessario avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59019-130">For the first three steps, you will need to start Windows PowerShell.</span></span>

<span data-ttu-id="59019-131">Utilizzando il servizio MMS (Meeting Migration Service), puoi aggiornare gli inviti alle riunioni che sono stati già inviati agli utenti della tua organizzazione prima che i loro numeri di telefono predefiniti venissero cambiati.</span><span class="sxs-lookup"><span data-stu-id="59019-131">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers had been changed.</span></span> <span data-ttu-id="59019-132">Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="59019-132">For additional information, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

- <span data-ttu-id="59019-133">Esegui il servizio MMS (Meeting Migration Service) per gli utenti i cui numeri di telefono predefiniti sono stati cambiati nel Passo 2.</span><span class="sxs-lookup"><span data-stu-id="59019-133">Run the Meeting Migration Service for the users that had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="59019-134">Per farlo, esegui il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="59019-134">To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="59019-p109">È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*.</span><span class="sxs-lookup"><span data-stu-id="59019-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="59019-137">Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un ponte per conferenze audio</span><span class="sxs-lookup"><span data-stu-id="59019-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="59019-138">Quando si annulla l'assegnazione di un numero di telefono da un ponte per audioconferenze, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="59019-138">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="59019-139">Dato che il numero di telefono è stato cambiato, è importante aggiornare tutti gli utenti che potrebbero avere quel numero di telefono come numero predefinito (se presente) e aggiornare i loro inviti alle riunioni esistenti prima che l'assegnazione del numero di telefono al ponte per audioconferenze venga annullata.</span><span class="sxs-lookup"><span data-stu-id="59019-139">Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the bridge.</span></span>

<span data-ttu-id="59019-140">Se il numero di telefono viene rimosso senza aggiornare gli utenti e le loro riunioni, i loro inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona più per partecipare.</span><span class="sxs-lookup"><span data-stu-id="59019-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>

<span data-ttu-id="59019-141">Per i primi tre passi, è necessario avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59019-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="59019-142">Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="59019-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="59019-143">Passo 1 - Aggiornare gli utenti che hanno il numero di telefono da cui rimuovere l'assegnazione tra i loro numeri predefiniti</span><span class="sxs-lookup"><span data-stu-id="59019-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="59019-p112">Sostituire numero a tariffa o numero verde predefinito per tutti gli utenti che hanno come numero predefinito il numero di cui annullare l'assegnazione e avviare il processo di ripianificazione delle loro riunioni. Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="59019-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 ><span data-ttu-id="59019-146">È inoltre possibile modificare il numero a pagamento o il numero verde predefinito degli utenti nell'interfaccia di amministrazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="59019-146">You can also change the default toll or toll-free number of users in the Skype for Business admin center, however, this won't automatically reschedule their meetings.</span></span> <span data-ttu-id="59019-147">Tuttavia, questa azione non riprogrammerà automaticamente le riunioni.</span><span class="sxs-lookup"><span data-stu-id="59019-147">However, this won't automatically reschedule their meetings.</span></span>

 <span data-ttu-id="59019-148">Per ulteriori informazioni, consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="59019-148">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="59019-149">A seconda della grandezza della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="59019-149">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="59019-150">Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59019-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="59019-151">Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato *In attesa* o *In corso*.</span><span class="sxs-lookup"><span data-stu-id="59019-151">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="59019-152">Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="59019-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="59019-153">Passo 3 - Annullare l'assegnazione del vecchio numero di telefono dal ponte per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="59019-153">Step 3 - Unassign the old phone number from the dial-in conferencing bridge</span></span>

1. <span data-ttu-id="59019-154">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="59019-154">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="59019-155">Vai all' **interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Voce** > **Numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="59019-155">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="59019-156">Seleziona il numero di telefono dall'elenco, e nel riquadro Azioni fai clic su **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="59019-156">Select the phone number from the list and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="59019-157">Nella finestra di conferma, fai clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="59019-157">In the ** Reset conference ID?** window, click **Yes**.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="59019-158">Una volta annullata l'assegnazione di un numero di telefono da un ponte per audioconferenze, il numero di telefono non sarà più utilizzabile dagli utenti per partecipare a riunioni nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="59019-158">Once a phone number is unassigned from a conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="59019-159">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="59019-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="59019-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="59019-160"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="59019-161">Come verificare se Windows PowerShell è pronto</span><span class="sxs-lookup"><span data-stu-id="59019-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="59019-162">Questi passi verificano che sia in esecuzione Windows PowerShell 3.0 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="59019-162">Check that you are running Windows PowerShell version 3.0 or higher</span></span>

1. <span data-ttu-id="59019-163">Digita **Menu di avvio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="59019-163">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="59019-164">Digita _Get-Host_ nella finestra di **Windows PowerShell** per verificare la versione.</span><span class="sxs-lookup"><span data-stu-id="59019-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="59019-p114">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="59019-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="59019-168">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="59019-168">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="59019-169">Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="59019-169">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="59019-170">Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="59019-170">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="59019-171">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="59019-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="59019-172">Per avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59019-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="59019-173">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="59019-173">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="59019-174">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="59019-174">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="59019-175">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="59019-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="59019-176">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="59019-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="59019-177">Per altre informazioni sull'avvio di Windows PowerShell, consulta [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="59019-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="59019-178">Risparmiare tempo e automatizzare</span><span class="sxs-lookup"><span data-stu-id="59019-178">Save time or automate</span></span>

<span data-ttu-id="59019-179">Per risparmiare tempo automatizzare il processo, è possibile utilizzare [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber**.</span><span class="sxs-lookup"><span data-stu-id="59019-179">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="59019-180">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="59019-180">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="59019-181">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="59019-181">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="59019-182">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="59019-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59019-183">Per trovare il BridgeID, usa il **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="59019-183">Note:To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="59019-184">Per impostare il numero verde predefinito per tutti gli utenti senza uno a 8005551234, esegui:</span><span class="sxs-lookup"><span data-stu-id="59019-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="59019-185">Per modificare il numero verde predefinito di tutti gli utenti che hanno 8005551234 come numero verde predefinito in 8005551239 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="59019-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="59019-186">Per modificare il numero verde predefinito di tutti gli utenti con sede negli USA in 8005551234 e ripianificare automaticamente le loro riunioni, esegui:</span><span class="sxs-lookup"><span data-stu-id="59019-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="59019-187">La posizione che viene utilizzata sopra deve corrispondere alle informazioni sul contatto dell'utente/degli utenti impostate nell'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="59019-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="59019-188">Informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59019-188">About Windows PowerShell</span></span>

<span data-ttu-id="59019-189">Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no.</span><span class="sxs-lookup"><span data-stu-id="59019-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="59019-190">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="59019-190">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="59019-191">Per iniziare a usare Windows PowerShell, consulta questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="59019-191">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="59019-192">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="59019-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="59019-193">Perché devi utilizzare Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="59019-193">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="59019-p117">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="59019-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="59019-196">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="59019-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="59019-197">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="59019-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="59019-198">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="59019-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="59019-199">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="59019-199">Related topics</span></span>
[<span data-ttu-id="59019-200">Modificare le impostazioni per un ponte per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="59019-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
