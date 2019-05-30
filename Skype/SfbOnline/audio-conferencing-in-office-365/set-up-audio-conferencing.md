---
title: Configurare i servizi di audioconferenza per Skype for business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come configurare le conferenze telefoniche con accesso esterno o audio per gli utenti dell'azienda che hanno bisogno di usare un telefono per partecipare alle conferenze telefoniche. "
ms.openlocfilehash: 9406c0ba680dd7eb6be52e2055041677913c3315
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494197"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="d3941-103">Configurare i servizi di audioconferenza per Skype for business</span><span class="sxs-lookup"><span data-stu-id="d3941-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="d3941-104">A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="d3941-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="d3941-105">Skype for business include la funzionalità per i servizi di audioconferenza solo per questa situazione.</span><span class="sxs-lookup"><span data-stu-id="d3941-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="d3941-106">Gli utenti possono chiamare riunioni Skype for business usando un telefono, invece di usare l'app Skype for business in un dispositivo mobile o un PC.</span><span class="sxs-lookup"><span data-stu-id="d3941-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="d3941-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="d3941-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="d3941-109">Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="d3941-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="d3941-110">Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica</span><span class="sxs-lookup"><span data-stu-id="d3941-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="d3941-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d3941-111"><a name="__top"> </a></span></span>

<span data-ttu-id="d3941-112">Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="d3941-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="d3941-113">Passo 2: Ottenere e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="d3941-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="d3941-114">Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d3941-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="d3941-115">Per informazioni sulle licenze che è necessario acquistare per i servizi di audioconferenza e sul costo, vedere licenze per i [componenti aggiuntivi Skype for business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="d3941-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="d3941-116">I servizi di audioconferenza sono inclusi nelle licenze di Office 365 Enterprise E5 e come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="d3941-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="d3941-117">Dopo aver acquistato le licenze per i servizi di audioconferenza, è necessario assegnarle alle persone dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3941-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="d3941-118">Vedere [assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) acquistate agli utenti dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3941-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="d3941-119">È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente.</span><span class="sxs-lookup"><span data-stu-id="d3941-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="d3941-120">Per informazioni su come configurare i crediti per le comunicazioni, vedere [configurare i crediti per le comunicazioni per l'organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d3941-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3941-121">È anche possibile configurare servizi [di audioconferenza pay-per-minute](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="d3941-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="d3941-122">Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3941-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="d3941-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d3941-123"></span></span>

<span data-ttu-id="d3941-124">Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="d3941-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="d3941-125">Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="d3941-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="d3941-126">Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi:</span><span class="sxs-lookup"><span data-stu-id="d3941-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="d3941-127">**Usare l'interfaccia di amministrazione di Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="d3941-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="d3941-128">Per alcuni paesi/aree geografiche è possibile ottenere i numeri di servizio per i ponti di conferenza usando l'interfaccia di amministrazione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="d3941-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="d3941-129">Vedere [recupero di numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="d3941-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="d3941-130">**Trasferire i numeri di servizio esistenti**.</span><span class="sxs-lookup"><span data-stu-id="d3941-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="d3941-131">Per convertire o trasferire i numeri esistenti dal provider di servizi o dal gestore di telefonia corrente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3941-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="d3941-132">Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d3941-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="d3941-133">**Usare un modulo di richiesta per i nuovi numeri**.</span><span class="sxs-lookup"><span data-stu-id="d3941-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="d3941-134">A volte, a seconda del paese o dell'area geografica, non potrai ottenere i nuovi numeri di servizio usando l'interfaccia di amministrazione di Skype for business oppure avrai bisogno di numeri di telefono o codici di area specifici.</span><span class="sxs-lookup"><span data-stu-id="d3941-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="d3941-135">In questo caso, dovrai scaricare un modulo e inviarcelo.</span><span class="sxs-lookup"><span data-stu-id="d3941-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="d3941-136">Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d3941-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="d3941-137">Passo 4: Assegnare un numero di servizio al ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3941-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="d3941-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d3941-138"></span></span>

<span data-ttu-id="d3941-139">Dopo aver ottenuto i numeri di telefono a pagamento e/o il numero verde per il Bridge di conferenza, è necessario assegnare i numeri in modo che possano essere usati per gli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3941-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="d3941-140">Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="d3941-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="d3941-141">![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business:**</span><span class="sxs-lookup"><span data-stu-id="d3941-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="d3941-142">\*\*\*\* > Accedere al**portale legacy**di interfaccia di amministrazione di **Microsoft 365 Admin Center** > **Teams** > .</span><span class="sxs-lookup"><span data-stu-id="d3941-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="d3941-143">Selezionare \*\*\*\* > **numeri di telefono**vocali.</span><span class="sxs-lookup"><span data-stu-id="d3941-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="d3941-144">Selezionare il numero di telefono e fare clic su **assegna**.</span><span class="sxs-lookup"><span data-stu-id="d3941-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="d3941-145">Per altre informazioni, vedere [modificare i numeri di telefono nel Bridge di audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="d3941-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="d3941-146">Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3941-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="d3941-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d3941-147"></span></span>

<span data-ttu-id="d3941-148">Si vogliono quindi impostare le [lingue dell'operatore automatico per](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) i servizi di audioconferenza che l'operatore automatico di conferenza USA per salutare i chiamanti quando effettuano la chiamata a un numero di telefono per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="d3941-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="d3941-149">![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="d3941-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d3941-150">Nel dashboard accedere a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="d3941-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d3941-151">Selezionare il numero di telefono del Bridge di conferenza, fare clic su **modifica**e quindi scegliere la lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="d3941-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="d3941-152">![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**:</span><span class="sxs-lookup"><span data-stu-id="d3941-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="d3941-153">\*\*\*\* > Accedere al**portale legacy**di interfaccia di amministrazione di **Office 365 Admin Center** > **Teams** > .</span><span class="sxs-lookup"><span data-stu-id="d3941-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d3941-154">Selezionare **audioconferenza** > **Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="d3941-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="d3941-155">Selezionare il numero di telefono del Bridge di conferenza, selezionare **imposta lingue**e quindi scegliere la lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="d3941-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="d3941-156">Passo 6: Configurare le impostazioni del ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3941-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="d3941-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d3941-157"></span></span>
    
<span data-ttu-id="d3941-158">Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="d3941-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="d3941-159">![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="d3941-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d3941-160">Nel dashboard accedere a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="d3941-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d3941-161">Selezionare **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="d3941-161">Select **Bridge settings**.</span></span> <span data-ttu-id="d3941-162">Verrà visualizzato il riquadro **Impostazioni ponte**.</span><span class="sxs-lookup"><span data-stu-id="d3941-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="d3941-163">Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="d3941-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="d3941-164">![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business:**</span><span class="sxs-lookup"><span data-stu-id="d3941-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="d3941-165">\*\*\*\* > Accedere al**portale legacy**di interfaccia di amministrazione di **Microsoft 365 Admin Center** > **Teams** > .</span><span class="sxs-lookup"><span data-stu-id="d3941-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d3941-166">Selezionare \*\*\*\* > **impostazioni di Microsoft Bridge**per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="d3941-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="d3941-167">Verrà visualizzata la pagina **Impostazioni ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d3941-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="d3941-168">Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="d3941-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="d3941-169">Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="d3941-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="d3941-170">Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d3941-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="d3941-171">È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3941-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="d3941-172">![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="d3941-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d3941-173">Nel dashboard fare clic su **utenti**, selezionare l'utente nell'elenco e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="d3941-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="d3941-174">Selezionare **modifica** accanto a servizi di **audioconferenza**e quindi nel riquadro **audioconferenza** scegliere un numero nell'elenco a **pagamento** e numero **verde** .</span><span class="sxs-lookup"><span data-stu-id="d3941-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="d3941-175">![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business:**</span><span class="sxs-lookup"><span data-stu-id="d3941-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="d3941-176">Accedere al**portale legacy**di **Microsoft 365 Admin Center** > **Teams** > .</span><span class="sxs-lookup"><span data-stu-id="d3941-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d3941-177">Selezionare \*\*\*\* > **utenti**di servizi di audioconferenza e quindi selezionare l'utente nell'elenco e fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="d3941-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="d3941-178">Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d3941-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="d3941-179">Passo 8: Configurare gli inviti alla riunione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d3941-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="d3941-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d3941-180"></span></span>
 
<span data-ttu-id="d3941-181">I numeri di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alla riunione inviati ai partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="d3941-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="d3941-182">È tuttavia possibile aggiungere una guida e collegamenti legali personalizzati, un messaggio di testo e un elemento grafico aziendale di piccole dimensioni, se si vuole.</span><span class="sxs-lookup"><span data-stu-id="d3941-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="d3941-183">Vedere [personalizzare](../set-up-skype-for-business-online/customize-meeting-invitations.md)gli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d3941-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="d3941-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d3941-184">Related topics</span></span>

[<span data-ttu-id="d3941-185">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="d3941-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="d3941-186">Configurare Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d3941-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="d3941-187">Numeri di telefono per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d3941-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="d3941-188">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="d3941-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
