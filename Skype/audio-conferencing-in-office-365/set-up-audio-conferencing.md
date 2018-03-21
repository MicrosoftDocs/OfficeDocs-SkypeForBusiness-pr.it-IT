---
title: Configurare le audioconferenze per Skype for Business e Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: 'Informazioni su come configurare servizi di conferenza telefonica o audio per le persone nell''azienda che desiderano partecipare a conferenze telefoniche mediante un telefono. '
ms.openlocfilehash: fd427abf14d3d705bc9f846f32a27d9be62967e8
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="19066-103">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19066-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="19066-104">A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="19066-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="19066-105">Skype per le aziende e Teams Microsoft includono la funzionalità di audioconferenza per solo questa situazione!</span><span class="sxs-lookup"><span data-stu-id="19066-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="19066-106">Le persone possono chiamare Skype per le riunioni aziendali o Microsoft Teams mediante un telefono, anziché utilizzare il Skype per applicazioni aziendali o Microsoft Teams su un dispositivo mobile o PC.</span><span class="sxs-lookup"><span data-stu-id="19066-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="19066-107">È sufficiente configurare conferenze Audio per gli utenti che prevedono di programmare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="19066-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="19066-108">I partecipanti alla riunione che effettua la chiamata non è necessario alcun licenze assegnate loro o altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="19066-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="19066-109">Per le domande frequenti sui servizi di conferenza Audio, vedere [domande frequenti di conferenze Audio](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="19066-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="19066-110">Passaggio 1: acquisto e assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="19066-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="19066-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="19066-111"></span></span>

<span data-ttu-id="19066-112">È necessario essere un [ruoli di amministratore su Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="19066-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="19066-113">Scoprire se audioconferenza in Office 365 è disponibile nel paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="19066-113">Find out if Audio Conferencing in Office 365 is available in your country/region.</span></span> <span data-ttu-id="19066-114">[Disponibilità paese e alle aree per le conferenze Audio e la chiamata Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="19066-114">[Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="19066-115">Scopri le licenze che è necessario acquistare per conferenze Audio e il relativo verrà costo.</span><span class="sxs-lookup"><span data-stu-id="19066-115">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost.</span></span> <span data-ttu-id="19066-116">Vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)e acquistare le licenze.</span><span class="sxs-lookup"><span data-stu-id="19066-116">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="19066-117">[Assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) è stato acquistato per gli utenti dell'organizzazione che intende pianificazione o lead riunioni.</span><span class="sxs-lookup"><span data-stu-id="19066-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="19066-118">Se è stato acquistato Communications crediti licenze e le licenze di componente aggiuntivo **Per conferenze Audio** , assegnarli troppo.</span><span class="sxs-lookup"><span data-stu-id="19066-118">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="19066-119">Per ulteriori informazioni, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="19066-119">For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="19066-120">Passaggio 2: Scegliere il provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="19066-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="19066-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="19066-121"></span></span>

<span data-ttu-id="19066-122">Un provider di servizi di conferenza audio fornisce un *ponte per conferenze audio*.</span><span class="sxs-lookup"><span data-stu-id="19066-122">An audio conferencing provider supplies an *audio conferencing bridge*.</span></span> <span data-ttu-id="19066-123">Bridge conferenza imposta i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni.</span><span class="sxs-lookup"><span data-stu-id="19066-123">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="19066-124">Decidere se utilizzare Microsoft o un provider di servizi di conferenza audio di terze parti:</span><span class="sxs-lookup"><span data-stu-id="19066-124">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="19066-125">Gli utenti di Microsoft Teams non utente un provider di servizi di conferenza audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="19066-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="19066-126">**Microsoft come provider di servizi di conferenza audio**: se si desidera che la soluzione più semplice per le conferenze audio, scegliere Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="19066-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="19066-127">**Terze parti come provider di servizi di conferenza audio**: se si partecipa a un paese dove audioconferenze con accesso esterno in Office 365 non è disponibile, la qualità del servizio non è grande a causa della posizione o si dispone di un contratto esistente, scegliere un audio di terze parti provider di servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="19066-127">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="19066-128">Per trovare un provider, andare a [Individuare Microsoft](http://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="19066-128">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="19066-129">All'interno dell'organizzazione, è possibile avere alcune persone che utilizzano Microsoft come i provider di servizi di conferenza audio gli utenti che utilizzano un provider di terze parti.</span><span class="sxs-lookup"><span data-stu-id="19066-129">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="19066-130">Ma sarà più complicato consente di impostare e gestire.</span><span class="sxs-lookup"><span data-stu-id="19066-130">But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="19066-131">Per un confronto dettagliato tra Microsoft come provider di audio e un provider di terze parti, vedere [confronto tra i provider di servizi di conferenza audio](compare-audio-conferencing-providers.md).</span><span class="sxs-lookup"><span data-stu-id="19066-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="19066-132">Passaggio 3: Assegnare il provider di servizi di conferenza audio agli utenti di condurre o pianificare riunioni</span><span class="sxs-lookup"><span data-stu-id="19066-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="19066-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="19066-133"></span></span>

<span data-ttu-id="19066-134">Ora che si è deciso per il provider di servizi di conferenza audio, è necessario assegnare il provider alle persone all'interno dell'organizzazione condurre o pianificare riunioni.</span><span class="sxs-lookup"><span data-stu-id="19066-134">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="19066-135">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19066-135">Do one of the following:</span></span> 
  
- <span data-ttu-id="19066-136">[Assegnare Microsoft come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="19066-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="19066-137">[Assegnare una terza parte come provider di servizi di conferenza audio](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="19066-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="19066-138">Passaggio 4: Impostare le convocazioni di riunione</span><span class="sxs-lookup"><span data-stu-id="19066-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="19066-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="19066-139"></span></span>

<span data-ttu-id="19066-140">La procedura seguente è **facoltativo**, ma una quantità elevata di admins like eseguirle:</span><span class="sxs-lookup"><span data-stu-id="19066-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="19066-141">[Personalizza convocazioni di riunione](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="19066-141">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span> <span data-ttu-id="19066-142">I numeri di accesso impostate per l'utente verranno aggiunta automaticamente per gli inviti alle riunioni inviati ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="19066-142">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="19066-143">Tuttavia, è possibile aggiungere Guida personalizzata e collegamenti legali, un messaggio di testo e immagine piccola società.</span><span class="sxs-lookup"><span data-stu-id="19066-143">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="19066-144">[Set di numeri di telefono per conferenze Audio per inclusi in inviti agli organizzatori della riunione](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="19066-144">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> <span data-ttu-id="19066-145">Questo è il numero di telefono che verrà visualizzata in alle riunioni pianificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="19066-145">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="19066-146">[Impostare le lingue di operatore automatico per le conferenze Audio](set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di audioconferenza per saluti salutare un chiamante quando si effettua la chiamata a un numero di telefono di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="19066-146">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="19066-147">Questo passaggio si applica solo se si utilizza Microsoft come provider di audio.</span><span class="sxs-lookup"><span data-stu-id="19066-147">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="19066-148">[Impostare la lunghezza del PIN per le riunioni di conferenze Audio](set-the-pin-length-for-audio-conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="19066-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="19066-149">Questa funzionalità non è ancora disponibile per i clienti con Office 365 gestito dal 21Vianet in Cina.</span><span class="sxs-lookup"><span data-stu-id="19066-149">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="19066-150">Per ulteriori informazioni, vedere [informazioni su Office 365 gestito dal 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span><span class="sxs-lookup"><span data-stu-id="19066-150">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="19066-151">See also</span><span class="sxs-lookup"><span data-stu-id="19066-151">Related topics</span></span>

[<span data-ttu-id="19066-152">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="19066-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="19066-153">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="19066-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="19066-154">Numeri di telefono per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="19066-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="19066-155">Impostare le opzioni per riunioni online e conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="19066-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

