---
title: Configurare le audioconferenze per Skype for Business e Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come configurare servizi di conferenza telefonica o audio per le persone nell'azienda che desiderano partecipare a conferenze telefoniche mediante un telefono. "
ms.openlocfilehash: 5d069822bf818db63ed35545a34a0bfa2eeee672
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562669"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="4502f-103">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4502f-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="4502f-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span><span class="sxs-lookup"><span data-stu-id="4502f-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="4502f-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="4502f-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="4502f-109">Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="4502f-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="4502f-110">Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica</span><span class="sxs-lookup"><span data-stu-id="4502f-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="4502f-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="4502f-111"><a name="__top"> </a></span></span>


<span data-ttu-id="4502f-112">Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="4502f-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="4502f-113">Passo 2: Ottenere e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="4502f-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="4502f-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4502f-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
        
2. <span data-ttu-id="4502f-p104">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span><span class="sxs-lookup"><span data-stu-id="4502f-p104">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="4502f-p105">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="4502f-p105">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4502f-p106">You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.</span><span class="sxs-lookup"><span data-stu-id="4502f-p106">You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="4502f-122">Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4502f-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="4502f-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="4502f-123"><a name="__top"> </a></span></span>

<span data-ttu-id="4502f-p107">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers:</span><span class="sxs-lookup"><span data-stu-id="4502f-p107">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="4502f-p108">**Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="4502f-p108">**Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="4502f-p109">**Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span><span class="sxs-lookup"><span data-stu-id="4502f-p109">**Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="4502f-p110">**Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span><span class="sxs-lookup"><span data-stu-id="4502f-p110">**Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="4502f-136">Passo 4: Assegnare un numero di servizio al ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4502f-136">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="4502f-137"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="4502f-137"><a name="__top"> </a></span></span>

<span data-ttu-id="4502f-138">Una volta ottenuti i numeri a pagamento e i numeri verdi per il ponte per audioconferenza, è necessario assegnarli in modo che possano essere utilizzati per gli inviti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="4502f-138">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invites.</span></span>  

<span data-ttu-id="4502f-139">Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="4502f-139">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="4502f-140">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="4502f-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 <span data-ttu-id="4502f-141">Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **vocale** > **i numeri di telefono**, selezionare il numero di telefono e fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="4502f-141">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**, select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="4502f-142">Per ulteriori informazioni, vedere [modificare i numeri di telefono del ponte per conferenze audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="4502f-142">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="4502f-143">Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4502f-143">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="4502f-144"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="4502f-144"><a name="__top"> </a></span></span>

<span data-ttu-id="4502f-145">Si desidera [impostare le lingue di operatore automatico per le conferenze Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di servizi di conferenza per saluti salutare un chiamante quando si effettua la chiamata a un numero di telefono per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4502f-145">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet a caller when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="4502f-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="4502f-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="4502f-147">Dal Dashboard, vai su **Riunioni** > **Ponti per audioconferenza**, seleziona il numero di telefono del ponte per audiconferenza, fai clic su **Modifica**, quindi fai clic sulla lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="4502f-147">From the Dashboard, go to **Meetings** > **Conference bridges**, select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="4502f-148">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="4502f-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="4502f-149">Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **audioconferenze** > **bridging Microsoft**, selezionare il numero di telefono di ponte conferenza e quindi fare clic su \*\* Impostare lingue\*\*.</span><span class="sxs-lookup"><span data-stu-id="4502f-149">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge**,  select the conferencing bridge phone number, and then click **Set languages**.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="4502f-150">Passo 6: Configurare le impostazioni del ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4502f-150">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="4502f-151"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="4502f-151"><a name="__top"> </a></span></span>
    
<span data-ttu-id="4502f-152">Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="4502f-152">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="4502f-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="4502f-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="4502f-p111">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="4502f-p111">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="4502f-157">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="4502f-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="4502f-p112">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="4502f-p112">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="4502f-161">Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="4502f-161">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="4502f-162">Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4502f-162">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="4502f-p113">You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:</span><span class="sxs-lookup"><span data-stu-id="4502f-p113">You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:</span></span>

<span data-ttu-id="4502f-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**</span><span class="sxs-lookup"><span data-stu-id="4502f-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="4502f-166">Dal Dashboard, fai clic su **Utenti**, seleziona l'utente dall'elenco, fai clic su **Modifica**, fai clic su **Modifica** accanto a **Audioconferenza**, quindi nel riquadro **Audioconferenza**, seleziona un numero nelle liste **Numero a pagamento** e **Numero verde**.</span><span class="sxs-lookup"><span data-stu-id="4502f-166">From the Dashboard, click **Users**, select the user from the list, click **Edit**, click **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="4502f-167">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**</span><span class="sxs-lookup"><span data-stu-id="4502f-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="4502f-p114">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4502f-p114">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="4502f-170">Passo 8: Configurare gli inviti alla riunione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="4502f-170">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="4502f-171"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="4502f-171"><a name="__top"> </a></span></span>
 
<span data-ttu-id="4502f-p115">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="4502f-p115">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="4502f-175">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4502f-175">Related topics</span></span>

[<span data-ttu-id="4502f-176">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="4502f-176">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="4502f-177">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4502f-177">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="4502f-178">Numeri di telefono per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4502f-178">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="4502f-179">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="4502f-179">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
