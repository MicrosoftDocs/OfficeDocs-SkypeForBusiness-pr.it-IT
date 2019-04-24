---
title: Configurazione di conferenze Audio per Skype per le aziende
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come impostare dial-in o conferenze Audio per le persone in un'azienda che devono utilizzare un telefono per partecipare a conferenze telefoniche. "
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229312"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="855e1-103">Configurazione di conferenze Audio per Skype per le aziende</span><span class="sxs-lookup"><span data-stu-id="855e1-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="855e1-104">A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="855e1-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="855e1-105">Skype per le aziende include la funzionalità di audioconferenza per solo questa situazione!</span><span class="sxs-lookup"><span data-stu-id="855e1-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="855e1-106">Le persone possono chiamare Skype per le riunioni aziendali mediante un telefono, anziché utilizzare il Skype per applicazioni aziendali in un dispositivo mobile o un PC.</span><span class="sxs-lookup"><span data-stu-id="855e1-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="855e1-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="855e1-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="855e1-109">Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="855e1-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="855e1-110">Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica</span><span class="sxs-lookup"><span data-stu-id="855e1-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="855e1-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="855e1-111"><a name="__top"> </a></span></span>

<span data-ttu-id="855e1-112">Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="855e1-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="855e1-113">Passo 2: Ottenere e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="855e1-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="855e1-114">Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="855e1-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="855e1-115">Per ulteriori le licenze che è necessario acquistare per le conferenze Audio e il relativo verrà costo, vedere [Skype per la gestione delle licenze di componente aggiuntivo Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="855e1-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="855e1-116">Audioconferenze con accesso esterno è inclusa in Office 365 Enterprise E5 licenze e come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="855e1-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="855e1-117">Dopo che acquistare le licenze di conferenze Audio, è necessario assegnarli a tali persone all'interno dell'organizzazione che desiderano programmare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="855e1-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="855e1-118">Vedere [assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) è stato acquistato per gli utenti dell'organizzazione che intende pianificazione o lead riunioni.</span><span class="sxs-lookup"><span data-stu-id="855e1-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="855e1-119">È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente.</span><span class="sxs-lookup"><span data-stu-id="855e1-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="855e1-120">Per informazioni su come impostare i titoli di coda di comunicazioni, vedere [impostare i titoli di coda di comunicazione per l'organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="855e1-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="855e1-121">È inoltre possibile impostare [Conferenze Audio retribuzione al minuto](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="855e1-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="855e1-122">Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="855e1-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="855e1-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="855e1-123"></span></span>

<span data-ttu-id="855e1-124">Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="855e1-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="855e1-125">Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="855e1-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="855e1-126">Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi:</span><span class="sxs-lookup"><span data-stu-id="855e1-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="855e1-127">**Utilizzare Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="855e1-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="855e1-128">Per alcuni paesi, è possibile ottenere i numeri di servizio per i ponti di audioconferenze con il Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="855e1-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="855e1-129">Vedere [i numeri di telefono del servizio di Guida](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="855e1-129">See [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="855e1-130">**Porta i numeri di servizio esistente**.</span><span class="sxs-lookup"><span data-stu-id="855e1-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="855e1-131">In porta o trasferimento esistenti numeri dal provider di servizi corrente o gestore telefonico per Office 365.</span><span class="sxs-lookup"><span data-stu-id="855e1-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="855e1-132">Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="855e1-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="855e1-133">**Utilizzare un modulo di richiesta per nuovi numeri**.</span><span class="sxs-lookup"><span data-stu-id="855e1-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="855e1-134">In alcuni casi (a seconda del paese/area geografica) non sarà in grado di ottenere i nuovi numeri servizio con il Skype per interfaccia di amministrazione di Business o sarà necessario area codici o i numeri di telefono specifico.</span><span class="sxs-lookup"><span data-stu-id="855e1-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="855e1-135">In questo caso, dovrai scaricare un modulo e inviarcelo.</span><span class="sxs-lookup"><span data-stu-id="855e1-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="855e1-136">Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="855e1-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="855e1-137">Passo 4: Assegnare un numero di servizio al ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="855e1-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="855e1-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="855e1-138"></span></span>

<span data-ttu-id="855e1-139">Una volta che viene visualizzato il numero a tariffa e/o numeri verdi per i bridge conferenza, è necessario assegnare i numeri in modo che possono essere utilizzati negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="855e1-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="855e1-140">Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="855e1-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="855e1-141">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="855e1-141">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="855e1-142">Vai al **Centro di amministrazione di Microsoft 365** > **Admin Center** > **Team** > **portale Legacy**.</span><span class="sxs-lookup"><span data-stu-id="855e1-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="855e1-143">Selezionare **segreteria** > **i numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="855e1-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="855e1-144">Selezionare il numero di telefono e fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="855e1-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="855e1-145">Per ulteriori informazioni, vedere [modificare i numeri di telefono del ponte per conferenze audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="855e1-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="855e1-146">Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="855e1-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="855e1-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="855e1-147"></span></span>

<span data-ttu-id="855e1-148">Si desidera [impostare le lingue di operatore automatico per le conferenze Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di servizi di conferenza per saluti salutare i chiamanti quando si effettua la chiamata a un numero di telefono per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="855e1-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="855e1-149">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team Microsoft che**:</span><span class="sxs-lookup"><span data-stu-id="855e1-149">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="855e1-150">Nel Dashboard di accedere alle **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="855e1-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="855e1-151">Selezionare il numero di telefono di ponte conferenza, fare clic su **Modifica**e quindi fare clic sulla lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="855e1-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="855e1-152">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per Business admin center**:</span><span class="sxs-lookup"><span data-stu-id="855e1-152">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="855e1-153">Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Team** > **portale Legacy**.</span><span class="sxs-lookup"><span data-stu-id="855e1-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="855e1-154">Selezionare **audioconferenze** > **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="855e1-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="855e1-155">Selezionare il numero di telefono di ponte conferenza, selezionare **Set di lingue**e quindi fare clic sulla lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="855e1-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="855e1-156">Passo 6: Configurare le impostazioni del ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="855e1-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="855e1-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="855e1-157"></span></span>
    
<span data-ttu-id="855e1-158">Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="855e1-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="855e1-159">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team Microsoft che**:</span><span class="sxs-lookup"><span data-stu-id="855e1-159">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="855e1-160">Nel Dashboard di accedere alle **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="855e1-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="855e1-161">Selezionare **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="855e1-161">Select **Bridge settings**.</span></span> <span data-ttu-id="855e1-162">Verrà visualizzato il riquadro **Impostazioni ponte**.</span><span class="sxs-lookup"><span data-stu-id="855e1-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="855e1-163">Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="855e1-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="855e1-164">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="855e1-164">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="855e1-165">Vai al **Centro di amministrazione di Microsoft 365** > **Admin Center** > **Team** > **portale Legacy**.</span><span class="sxs-lookup"><span data-stu-id="855e1-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="855e1-166">Selezionare **audioconferenze** > **Impostazioni bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="855e1-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="855e1-167">Verrà visualizzata la pagina **Impostazioni ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="855e1-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="855e1-168">Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="855e1-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="855e1-169">Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="855e1-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="855e1-170">Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="855e1-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="855e1-171">È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni.</span><span class="sxs-lookup"><span data-stu-id="855e1-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="855e1-172">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team Microsoft che**:</span><span class="sxs-lookup"><span data-stu-id="855e1-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="855e1-173">Nel dashboard, fare clic su **utenti**, selezionare l'utente dall'elenco e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="855e1-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="855e1-174">Selezionare **Modifica** accanto a **Servizi di conferenza Audio**e quindi nel riquadro di **Conferenze Audio** , selezionare un numero negli elenchi numeri **numero a pagamento** e il **numero verde** .</span><span class="sxs-lookup"><span data-stu-id="855e1-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="855e1-175">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="855e1-175">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="855e1-176">Vai al **Centro di amministrazione di Microsoft 365** > **Team** > **portale Legacy**.</span><span class="sxs-lookup"><span data-stu-id="855e1-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="855e1-177">Selezionare **audioconferenze** > **gli utenti**, quindi selezionare l'utente dall'elenco e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="855e1-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="855e1-178">Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="855e1-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="855e1-179">Passo 8: Configurare gli inviti alla riunione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="855e1-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="855e1-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="855e1-180"></span></span>
 
<span data-ttu-id="855e1-181">I numeri di accesso impostate per l'utente verranno aggiunta automaticamente per gli inviti alle riunioni inviati ai partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="855e1-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="855e1-182">Tuttavia, è possibile aggiungere Guida personalizzata e collegamenti legali, un messaggio di testo e immagine piccola società se si desidera.</span><span class="sxs-lookup"><span data-stu-id="855e1-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="855e1-183">Vedere [Personalizza convocazioni di riunione](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="855e1-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="855e1-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="855e1-184">Related topics</span></span>

[<span data-ttu-id="855e1-185">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="855e1-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="855e1-186">Configurare Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="855e1-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="855e1-187">Numeri di telefono per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="855e1-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="855e1-188">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="855e1-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
