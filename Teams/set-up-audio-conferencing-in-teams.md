---
title: Configurare Audioconferenza per Microsoft Teams
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
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni sulla configurazione del servizio di conferenza telefonica con accesso esterno o del servizio Audioconferenza per gli utenti dell'organizzazione che devono usare il telefono per partecipare alle conferenze telefoniche. "
ms.openlocfilehash: d1596a650507938e8dc3e87fb02dec68e415f6d6
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031422"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="6c1a7-103">Configurare Audioconferenza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c1a7-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="6c1a7-104">A volte le persone all'interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="6c1a7-105">Microsoft Teams offre la funzionalità di audioconferenza proprio per queste evenienze.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="6c1a7-106">È possibile accedere alle riunioni di Teams utilizzando un telefono anziché l'app Teams su un dispositivo mobile o un PC.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="6c1a7-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="6c1a7-109">Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="6c1a7-110">Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica</span><span class="sxs-lookup"><span data-stu-id="6c1a7-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="6c1a7-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1a7-111"><a name="__top"> </a></span></span>

<span data-ttu-id="6c1a7-112">Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="6c1a7-113">Passo 2: Ottenere e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="6c1a7-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="6c1a7-114">Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="6c1a7-115">Per informazioni su quali licenze è necessario acquistare per Audioconferenza e i relativi costi, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="6c1a7-116">Il servizio Audioconferenza è incluso nelle licenze Office 365 Enterprise E5 e come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="6c1a7-117">Dopo aver acquistato le licenze per Audioconferenza, è necessario assegnarle agli utenti dell'organizzazione che intendono pianificare o coordinare riunioni.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="6c1a7-118">Vedere Assegnare licenze agli utenti [in Microsoft 365 o Office 365 per](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) le aziende acquistati agli utenti dell'organizzazione che inducono a pianificare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-118">See [Assign licenses to users in Microsoft 365 or Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="6c1a7-119">È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="6c1a7-120">Per altre informazioni sulla configurazione di Credito per la comunicazione, vedere [Configurare Credito per la comunicazione per l'organizzazione](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c1a7-121">È inoltre possibile configurare il servizio [Audioconferenza con tariffa al minuto](audio-conferencing-pay-per-minute.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="6c1a7-122">Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="6c1a7-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="6c1a7-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1a7-123"><a name="__top"> </a></span></span>

<span data-ttu-id="6c1a7-124">Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="6c1a7-125">Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="6c1a7-126">Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi:</span><span class="sxs-lookup"><span data-stu-id="6c1a7-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="6c1a7-127">**Usare l'interfaccia di amministrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="6c1a7-128">In alcuni paesi/aree geografiche è possibile ottenere i numeri di servizio per i bridge di conferenza tramite l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="6c1a7-129">Vedere [Recupero dei numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="6c1a7-130">**Trasferire i numeri del servizio esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="6c1a7-131">Per trasferire i numeri esistenti dal gestore o provider di servizi corrente a Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6c1a7-132">Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="6c1a7-133">**Usare un modulo di richiesta per nuovi numeri**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="6c1a7-134">A seconda del paese/area geografica, talvolta non è possibile ottenere nuovi numeri di servizio tramite l'interfaccia di amministrazione di Microsoft Teams oppure sono necessari numeri di telefono o prefissi specifici.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="6c1a7-135">In questo caso è necessario scaricare un modulo di richiesta, compilarlo e inviarlo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="6c1a7-136">Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="6c1a7-137">Passo 4: Assegnare un numero di servizio al ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="6c1a7-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="6c1a7-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1a7-138"><a name="__top"> </a></span></span>

<span data-ttu-id="6c1a7-139">Dopo aver ottenuto i numeri a pagamento e i numeri verdi per il bridge di conferenza, è necessario assegnarli per consentirne l'uso negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="6c1a7-140">Seguire i passaggi seguenti per assegnare un nuovo numero di telefono al bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="6c1a7-141">![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="6c1a7-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="6c1a7-142">Passare all'**interfaccia di amministrazione di Microsoft 365** > **Interfacce di amministrazione** > **Teams** > **Portale legacy**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="6c1a7-143">Selezionare **Vocale** > **Numeri telefonici**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="6c1a7-144">Selezionare il numero di telefono e fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="6c1a7-145">Per altri dettagli, vedere [Cambiare i numeri di telefono del bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="6c1a7-146">Passaggio 5: impostare le lingue predefinite e alternative per un bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="6c1a7-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="6c1a7-147"><a name="__top"> </a> A questo punto, è necessario [impostare in Microsoft Teams le lingue dell'operatore automatico per Audioconferenza](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) che verranno usate dall'operatore automatico dell'audioconferenza per salutare gli utenti che chiamano un numero di telefono per accedere ad Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="6c1a7-148">![Icona che mostra il logo di Skype for Business](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="6c1a7-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6c1a7-149">Nella dashboard passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="6c1a7-150">Selezionare il numero di telefono del bridge di conferenza, fare clic su **Modifica** e quindi fare clic sulla lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="6c1a7-151">Passo 6: Configurare le impostazioni del ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="6c1a7-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="6c1a7-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1a7-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="6c1a7-153">Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="6c1a7-154">![Icona che mostra il logo di Skype for Business](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="6c1a7-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6c1a7-155">Nella dashboard passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="6c1a7-156">Selezionare **Impostazioni del bridge**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-156">Select **Bridge settings**.</span></span> <span data-ttu-id="6c1a7-157">Verrà visualizzato il riquadro **Impostazioni ponte**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="6c1a7-158">Per altri dettagli, vedere [Modificare le impostazioni per un bridge del servizio Audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="6c1a7-159">Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="6c1a7-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="6c1a7-160">Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="6c1a7-161">È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="6c1a7-162">![Icona che mostra il logo di Skype for Business](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="6c1a7-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6c1a7-163">Nella dashboard fare clic su **Utenti**, selezionare l'utente nell'elenco e quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="6c1a7-164">Selezionare **Modifica** accanto ad **Audioconferenza** e quindi nel riquadro **Audioconferenza** scegliere un numero negli elenchi **Numero a pagamento** e **Numero verde**.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="6c1a7-165">Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="6c1a7-166">Passo 8: Configurare gli inviti alla riunione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="6c1a7-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="6c1a7-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1a7-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="6c1a7-168">I numeri telefonici di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alle riunioni inviati ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="6c1a7-169">Se però si preferisce, è possibile aggiungere una guida e collegamenti alle note legali, un messaggio di testo e un piccolo logo aziendale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6c1a7-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="6c1a7-170">Vedere [Personalizzare gli inviti alle riunioni](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="6c1a7-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="6c1a7-171">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c1a7-171">Related topics</span></span>

[<span data-ttu-id="6c1a7-172">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="6c1a7-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="6c1a7-173">Numeri di telefono per Audioconferenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c1a7-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="6c1a7-174">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="6c1a7-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
