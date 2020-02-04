---
title: Configurare il servizio Audioconferenza per Skype for Business
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: "Informazioni sulla configurazione del servizio di conferenza telefonica con accesso esterno o del servizio Audioconferenza per gli utenti dell'organizzazione che devono usare il telefono per partecipare alle conferenze telefoniche. "
ms.openlocfilehash: ea254da1f742db602d396868aad36a0c20951128
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680363"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="3cc27-103">Configurare il servizio Audioconferenza per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3cc27-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="3cc27-p101">A volte gli utenti di un'organizzazione potrebbero avere la necessità di accedere a una riunione tramite telefono. In questo caso è possibile usare la funzionalità di conferenza telefonica disponibile in Skype for Business, che consente agli utenti di accedere alle riunioni di Skype for Business usando un telefono, invece di usare la app di Skype for Business su un dispositivo mobile o un PC.</span><span class="sxs-lookup"><span data-stu-id="3cc27-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business includes the audio conferencing feature for just this situation! People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="3cc27-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="3cc27-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="3cc27-109">Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="3cc27-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="3cc27-110">Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica</span><span class="sxs-lookup"><span data-stu-id="3cc27-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="3cc27-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc27-111"><a name="__top"> </a></span></span>

<span data-ttu-id="3cc27-112">Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="3cc27-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="3cc27-113">Passo 2: Ottenere e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="3cc27-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="3cc27-p103">Per il servizio Audioconferenza è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno. Per informazioni sulle licenze da acquistare per il servizio Audioconferenza e sui relativi costi, vedere [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="3cc27-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="3cc27-116">Il servizio Audioconferenza è incluso nelle licenze Office 365 Enterprise E5 e come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="3cc27-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="3cc27-117">Dopo aver acquistato le licenze per Audioconferenza, è necessario assegnarle agli utenti dell'organizzazione che intendono pianificare o coordinare riunioni.</span><span class="sxs-lookup"><span data-stu-id="3cc27-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="3cc27-118">Vedere l'articolo su come [assegnare o rimuovere licenze di Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) acquistate per gli utenti dell'organizzazione che intendono pianificare o coordinare riunioni.</span><span class="sxs-lookup"><span data-stu-id="3cc27-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="3cc27-119">È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente.</span><span class="sxs-lookup"><span data-stu-id="3cc27-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="3cc27-120">Per altre informazioni sulla configurazione di Credito per la comunicazione, vedere [Configurare Credito per la comunicazione per l'organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3cc27-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3cc27-121">È inoltre possibile configurare il servizio [Audioconferenza con tariffa al minuto](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="3cc27-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="3cc27-122">Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3cc27-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="3cc27-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc27-123"><a name="__top"> </a></span></span>

<span data-ttu-id="3cc27-124">Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="3cc27-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="3cc27-125">Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="3cc27-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="3cc27-126">Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi:</span><span class="sxs-lookup"><span data-stu-id="3cc27-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="3cc27-127">**Usare l'interfaccia di amministrazione di Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="3cc27-128">In alcuni paesi/aree geografiche è possibile ottenere i numeri del servizio per i bridge di conferenza usando l'interfaccia di amministrazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3cc27-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="3cc27-129">Vedere [Recupero dei numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="3cc27-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="3cc27-130">**Trasferire i numeri del servizio esistenti**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="3cc27-131">È possibile trasferire i numeri di telefono esistenti o eseguirne la portabilità dal provider di servizi o dall'operatore telefonico corrente Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cc27-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="3cc27-132">Per ulteriori informazioni, vedere [trasferire i numeri di telefono in team](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) o [gestire i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="3cc27-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="3cc27-133">**Usare un modulo di richiesta per nuovi numeri**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="3cc27-134">A seconda del paese/area geografica, talvolta non è possibile ottenere nuovi numeri del servizio tramite l'interfaccia di amministrazione Skype for Business oppure sono necessari numeri di telefono o prefissi specifici.</span><span class="sxs-lookup"><span data-stu-id="3cc27-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="3cc27-135">In questo caso è necessario scaricare un modulo di richiesta, compilarlo e inviarlo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3cc27-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="3cc27-136">Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3cc27-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="3cc27-137">Passo 4: Assegnare un numero di servizio al ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3cc27-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="3cc27-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc27-138"><a name="__top"> </a></span></span>

<span data-ttu-id="3cc27-139">Dopo aver ottenuto i numeri a pagamento e i numeri verdi per il bridge di conferenza, è necessario assegnarli per consentirne l'uso negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="3cc27-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="3cc27-140">Per assegnare un nuovo numero di telefono al bridge del servizio di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="3cc27-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="3cc27-141">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="3cc27-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="3cc27-142">Passare all'**interfaccia di amministrazione di Microsoft 365** > **Interfacce di amministrazione** > **Teams** > **Portale legacy**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="3cc27-143">Selezionare **Vocale** > **Numeri telefonici**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="3cc27-144">Selezionare il numero di telefono e fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="3cc27-145">Per altri dettagli, vedere [Cambiare i numeri di telefono del bridge per il servizio di audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3cc27-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="3cc27-146">Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3cc27-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="3cc27-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc27-147"><a name="__top"> </a></span></span>

<span data-ttu-id="3cc27-148">A questo punto, si vogliono [impostare le lingue dell'operatore automatico per Audioconferenza](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che verranno usate dall'operatore automatico di Audioconferenza per salutare gli utenti che chiamano un numero di telefono per accedere al servizio Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3cc27-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="3cc27-149">![Icona che mostra il logo di Skype for Business](../images/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="3cc27-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="3cc27-150">Nella dashboard passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="3cc27-151">Selezionare il numero di telefono del bridge di conferenza, fare clic su **Modifica** e quindi fare clic sulla lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cc27-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="3cc27-152">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**:</span><span class="sxs-lookup"><span data-stu-id="3cc27-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="3cc27-153">Andare all'interfaccia di amministrazione > **Interfacce di amministrazione** > **Teams** > **Portale legacy**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="3cc27-154">Selezionare **Audioconferenza** > **Bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="3cc27-155">Selezionare il numero di telefono del bridge di conferenza, selezionare **Imposta lingue** e quindi fare clic sulla lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cc27-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="3cc27-156">Passo 6: Configurare le impostazioni del ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3cc27-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="3cc27-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc27-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="3cc27-158">Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="3cc27-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="3cc27-159">![Icona che mostra il logo di Skype for Business](../images/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="3cc27-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="3cc27-160">Nella dashboard passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="3cc27-161">Selezionare **Impostazioni del bridge**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-161">Select **Bridge settings**.</span></span> <span data-ttu-id="3cc27-162">Verrà visualizzato il riquadro **Impostazioni ponte**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="3cc27-163">Per altri dettagli, vedere [Modificare le impostazioni per un bridge del servizio Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3cc27-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="3cc27-164">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="3cc27-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="3cc27-165">Passare all'**interfaccia di amministrazione di Microsoft 365** > **Interfacce di amministrazione** > **Teams** > **Portale legacy**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="3cc27-166">Selezionare **Audioconferenza** > **Impostazioni del bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="3cc27-167">Verrà visualizzata la pagina **Impostazioni ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="3cc27-168">Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3cc27-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="3cc27-169">Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="3cc27-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="3cc27-170">Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3cc27-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="3cc27-171">È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni.</span><span class="sxs-lookup"><span data-stu-id="3cc27-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="3cc27-172">![Icona che mostra il logo di Skype for Business](../images/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="3cc27-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="3cc27-173">Nella dashboard fare clic su **Utenti**, selezionare l'utente nell'elenco e quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="3cc27-174">Selezionare **Modifica** accanto ad **Audioconferenza** e quindi nel riquadro **Audioconferenza** scegliere un numero negli elenchi **Numero a pagamento** e **Numero verde**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="3cc27-175">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="3cc27-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="3cc27-176">Passare all'**interfaccia di amministrazione di Microsoft 365** > **Teams** > **Portale legacy**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="3cc27-177">Selezionare **Audioconferenza** > \*\* Utenti\*\*, selezionare l'utente nell'elenco e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3cc27-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="3cc27-178">Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3cc27-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="3cc27-179">Passo 8: Configurare gli inviti alla riunione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="3cc27-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="3cc27-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc27-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="3cc27-181">I numeri telefonici di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alle riunioni inviati ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3cc27-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="3cc27-182">Se però si preferisce, è possibile aggiungere una guida e collegamenti alle note legali, un messaggio di testo e un piccolo logo aziendale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3cc27-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="3cc27-183">Vedere [Personalizzare gli inviti alle riunioni](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="3cc27-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="3cc27-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3cc27-184">Related topics</span></span>

[<span data-ttu-id="3cc27-185">Domande frequenti sul servizio di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3cc27-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="3cc27-186">Configurare Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3cc27-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="3cc27-187">Numeri di telefono per Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3cc27-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="3cc27-188">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="3cc27-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
