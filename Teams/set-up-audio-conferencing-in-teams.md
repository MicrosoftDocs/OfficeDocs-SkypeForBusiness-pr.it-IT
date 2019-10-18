---
title: Configurare servizi di audioconferenza per Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come configurare le conferenze telefoniche con accesso esterno o audio per gli utenti dell'azienda che hanno bisogno di usare un telefono per partecipare alle conferenze telefoniche. "
ms.openlocfilehash: 3b9b0b3f7a684c8db5b7b3d8a326750ed12f2bff
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571261"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="e51db-103">Configurare servizi di audioconferenza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e51db-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="e51db-104">A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="e51db-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="e51db-105">Microsoft teams include la funzionalità di conferenza audio per questa situazione.</span><span class="sxs-lookup"><span data-stu-id="e51db-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="e51db-106">Gli utenti possono chiamare riunioni di teams usando un telefono, invece di usare l'app teams in un dispositivo mobile o un PC.</span><span class="sxs-lookup"><span data-stu-id="e51db-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="e51db-107">È necessario configurare solo i servizi di audioconferenza per gli utenti che intendono pianificare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="e51db-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="e51db-108">Le persone che partecipano alla riunione tramite telefono non hanno bisogno di altre impostazioni o che venga loro assegnata alcuna licenza.</span><span class="sxs-lookup"><span data-stu-id="e51db-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="e51db-109">Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="e51db-110">Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica</span><span class="sxs-lookup"><span data-stu-id="e51db-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="e51db-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e51db-111"></span></span>

<span data-ttu-id="e51db-112">Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="e51db-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="e51db-113">Passo 2: Ottenere e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="e51db-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="e51db-114">Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="e51db-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="e51db-115">Per informazioni sulle licenze che è necessario acquistare per i servizi di audioconferenza e sul costo, vedere licenze per i [componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="e51db-116">I servizi di audioconferenza sono inclusi nelle licenze di Office 365 Enterprise E5 e come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e51db-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="e51db-117">Dopo aver acquistato le licenze per i servizi di audioconferenza, è necessario assegnarle alle persone dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="e51db-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="e51db-118">Vedere [assegnare licenze agli utenti in Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) acquistati alle persone dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="e51db-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="e51db-119">È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente.</span><span class="sxs-lookup"><span data-stu-id="e51db-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="e51db-120">Per informazioni su come configurare i crediti per le comunicazioni, vedere [configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e51db-121">È anche possibile configurare servizi [di audioconferenza pay-per-minute](audio-conferencing-pay-per-minute.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="e51db-122">Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e51db-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="e51db-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e51db-123"></span></span>

<span data-ttu-id="e51db-124">Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="e51db-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="e51db-125">Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="e51db-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="e51db-126">Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi:</span><span class="sxs-lookup"><span data-stu-id="e51db-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="e51db-127">**Usare l'interfaccia di amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="e51db-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="e51db-128">Per alcuni paesi/aree geografiche è possibile ottenere i numeri di servizio per i ponti di conferenza usando l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e51db-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="e51db-129">Vedere [recupero di numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="e51db-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="e51db-130">**Trasferire i numeri di servizio esistenti**.</span><span class="sxs-lookup"><span data-stu-id="e51db-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="e51db-131">Per convertire o trasferire i numeri esistenti dal provider di servizi o dal gestore di telefonia corrente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e51db-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="e51db-132">Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md) o [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-132">You can see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="e51db-133">**Usare un modulo di richiesta per i nuovi numeri**.</span><span class="sxs-lookup"><span data-stu-id="e51db-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="e51db-134">A volte, a seconda del paese o dell'area geografica, non sarà possibile ottenere i nuovi numeri di servizio usando l'interfaccia di amministrazione di Microsoft teams oppure saranno necessari numeri di telefono o codici di area specifici.</span><span class="sxs-lookup"><span data-stu-id="e51db-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="e51db-135">In questo caso, dovrai scaricare un modulo e inviarcelo.</span><span class="sxs-lookup"><span data-stu-id="e51db-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="e51db-136">Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="e51db-137">Passo 4: Assegnare un numero di servizio al ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e51db-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="e51db-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e51db-138"></span></span>

<span data-ttu-id="e51db-139">Dopo aver ottenuto i numeri di telefono a pagamento e/o il numero verde per il Bridge di conferenza, è necessario assegnare i numeri in modo che possano essere usati per gli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="e51db-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="e51db-140">Seguire questa procedura per assegnare un nuovo numero di telefono al Bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e51db-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="e51db-141">![Icona che mostra il logo](media/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business:**</span><span class="sxs-lookup"><span data-stu-id="e51db-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="e51db-142">Accedere al**portale legacy**di interfaccia**di amministrazione di** >  **Microsoft 365 Admin Center** > **Teams** > .</span><span class="sxs-lookup"><span data-stu-id="e51db-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="e51db-143">Selezionare \*\*\*\* > **numeri di telefono**vocali.</span><span class="sxs-lookup"><span data-stu-id="e51db-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="e51db-144">Selezionare il numero di telefono e fare clic su **assegna**.</span><span class="sxs-lookup"><span data-stu-id="e51db-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="e51db-145">Per altre informazioni, vedere [modificare i numeri di telefono nel Bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="e51db-146">Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e51db-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="e51db-147"><a name="__top"></a> Si desidera quindi impostare le [lingue per gli operatori automatici per i servizi di audioconferenza in Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) che l'operatore automatico di conferenza USA per salutare i chiamanti quando effettuano la chiamata a un numero di telefono per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e51db-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="e51db-148">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="e51db-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e51db-149">Nel dashboard accedere a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="e51db-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e51db-150">Selezionare il numero di telefono del Bridge di conferenza, fare clic su **modifica**e quindi scegliere la lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="e51db-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="e51db-151">Passo 6: Configurare le impostazioni del ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e51db-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="e51db-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e51db-152"></span></span>
    
<span data-ttu-id="e51db-153">Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="e51db-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="e51db-154">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="e51db-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e51db-155">Nel dashboard accedere a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="e51db-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e51db-156">Selezionare **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="e51db-156">Select **Bridge settings**.</span></span> <span data-ttu-id="e51db-157">Verrà visualizzato il riquadro **Impostazioni ponte**.</span><span class="sxs-lookup"><span data-stu-id="e51db-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="e51db-158">Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="e51db-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="e51db-159">Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="e51db-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="e51db-160">Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e51db-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="e51db-161">È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni.</span><span class="sxs-lookup"><span data-stu-id="e51db-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="e51db-162">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="e51db-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e51db-163">Nel dashboard fare clic su **utenti**, selezionare l'utente nell'elenco e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="e51db-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="e51db-164">Selezionare **modifica** accanto a servizi di **audioconferenza**e quindi nel riquadro **audioconferenza** scegliere un numero nell'elenco a **pagamento** e numero **verde** .</span><span class="sxs-lookup"><span data-stu-id="e51db-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="e51db-165">Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="e51db-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="e51db-166">Passo 8: Configurare gli inviti alla riunione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e51db-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="e51db-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e51db-167"></span></span>
 
<span data-ttu-id="e51db-168">I numeri di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alla riunione inviati ai partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="e51db-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="e51db-169">È tuttavia possibile aggiungere una guida e collegamenti legali personalizzati, un messaggio di testo e un elemento grafico aziendale di piccole dimensioni, se si vuole.</span><span class="sxs-lookup"><span data-stu-id="e51db-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="e51db-170">Vedere [personalizzare gli inviti alle riunioni](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="e51db-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="e51db-171">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e51db-171">Related topics</span></span>

[<span data-ttu-id="e51db-172">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="e51db-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="e51db-173">Numeri di telefono per i servizi di audioconferenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e51db-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="e51db-174">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="e51db-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
