---
title: Servizi di conferenza audio con routing diretto per GCCH e DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come usare i servizi di conferenza audio con routing diretto in ambienti GCCH e DoD.
ms.openlocfilehash: 8304d18777739b4667c0f47b9dee3e9f8f6dcc38
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825654"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="3912d-103">Audioconferenza con Instradamento diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="3912d-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="3912d-104">I servizi di audioconferenza con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare a riunioni di teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="3912d-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="3912d-105">I partecipanti alla riunione possono preferire l'uso di un dispositivo telefonico per partecipare a riunioni di team in scenari come la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso ai team.</span><span class="sxs-lookup"><span data-stu-id="3912d-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don’t have access to Teams.</span></span> <span data-ttu-id="3912d-106">I partecipanti possono scegliere di partecipare alle riunioni effettuando la chiamata in un numero di telefono di accesso esterno per l'organizzazione oppure effettuando la chiamata della riunione al dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="3912d-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="3912d-107">Con i servizi di audioconferenza con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono di accesso esterno e tutti i dial-out per le riunioni vengono instradati tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="3912d-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="3912d-108">Per abilitare il servizio, le organizzazioni devono impostare il routing diretto e configurare i numeri di telefono che possono essere usati come numeri di telefono di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3912d-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="3912d-109">Il requisito di usare il routing diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non-GCC High e non-DoD in cui i numeri di telefono di accesso esterno sono forniti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3912d-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="3912d-110">Distribuire servizi di audioconferenza con routing diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="3912d-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="3912d-111">Passaggio 1: ottenere servizi di audioconferenza con routing diretto per le licenze GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="3912d-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="3912d-112">Per usare le conferenze audio in GCC High o DoD, l'organizzazione e gli utenti dell'organizzazione devono avere un servizio di audioconferenza con licenza di routing diretta assegnata.</span><span class="sxs-lookup"><span data-stu-id="3912d-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="3912d-113">Ecco le licenze necessarie per abilitare i servizi di audioconferenza con routing diretto per GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="3912d-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="3912d-114">GCC High: una licenza per i servizi di audioconferenza per l'organizzazione e l'audioconferenza-licenze GCC High per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3912d-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="3912d-115">DoD: una licenza per i servizi di audioconferenza-DoD tenant per l'organizzazione e le licenze per i servizi di audioconferenza per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3912d-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="3912d-116">Per abilitare il servizio, è necessaria una licenza tenant e almeno una licenza per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3912d-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="3912d-117">Non è possibile abilitare il servizio con solo la licenza tenant o solo con le licenze utente.</span><span class="sxs-lookup"><span data-stu-id="3912d-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="3912d-118">Per ottenere le licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.</span><span class="sxs-lookup"><span data-stu-id="3912d-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3912d-119">Gli utenti non possono essere abilitati per i servizi di audioconferenza con routing diretto fino alla configurazione dei numeri di telefono di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3912d-119">Users can’t be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="3912d-120">È consigliabile non assegnare servizi di audioconferenza con routing diretto per le licenze GCC High o DoD agli utenti fino a quando non si configurano i numeri di telefono con accesso esterno come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3912d-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="3912d-121">Passaggio 2: configurare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="3912d-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="3912d-122">Per configurare il routing diretto, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3912d-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="3912d-123">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="3912d-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="3912d-124">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="3912d-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="3912d-125">Quando configuri il routing diretto, ricordati di usare gli FQDN e le porte di dominio elevato o specifico del DoD che sono descritti in questi due articoli.</span><span class="sxs-lookup"><span data-stu-id="3912d-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="3912d-126">Passaggio 3: configurare i numeri di telefono con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3912d-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="3912d-127">I numeri di telefono di accesso esterno sono i numeri di telefono associati al Bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3912d-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="3912d-128">Questi numeri vengono usati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3912d-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="3912d-129">Questi numeri sono inclusi anche negli inviti alla riunione degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "trova un numero locale".</span><span class="sxs-lookup"><span data-stu-id="3912d-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the “Find a local number” page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="3912d-130">Definire i numeri di telefono del servizio nel tenant</span><span class="sxs-lookup"><span data-stu-id="3912d-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="3912d-131">Puoi usare il cmdlet di PowerShell New-csHybridTelephoneNumber per definire i numeri di telefono del servizio nel tenant che possono essere usati per instradare le chiamate al servizio di audioconferenza tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="3912d-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="3912d-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3912d-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="3912d-133">Assegnare i numeri di telefono del servizio al Bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3912d-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="3912d-134">È possibile assegnare numeri di telefono del servizio al Bridge di audioconferenza dell'organizzazione usando il cmdlet Register-csOnlineDialInConferencingServiceNumber di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3912d-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="3912d-135">Puoi vedere l'ID del Bridge di audioconferenza usando Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="3912d-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="3912d-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3912d-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="3912d-137">Passaggio 4: assegnare servizi di audioconferenza con routing diretto per le licenze GCC High o DoD agli utenti</span><span class="sxs-lookup"><span data-stu-id="3912d-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="3912d-138">Per assegnare i servizi di audioconferenza con routing diretto per le licenze GCC High o DoD all'utente, vedere [assegnare licenze agli utenti in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="3912d-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="3912d-139">Passaggio 5: (facoltativo) visualizzare un elenco di numeri di conferenza audio in teams</span><span class="sxs-lookup"><span data-stu-id="3912d-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="3912d-140">Per visualizzare l'elenco dei numeri di servizi di audioconferenza della propria organizzazione, [vedere un elenco di numeri di conferenza audio in Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3912d-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="3912d-141">Passaggio 6: (facoltativo) impostare le lingue per gli operatori automatici per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3912d-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="3912d-142">Per modificare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, vedere [impostare le lingue per l'operatore automatico per i servizi di audioconferenza in Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3912d-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="3912d-143">Passaggio 7: (facoltativo) modificare le impostazioni del Bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3912d-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="3912d-144">Per modificare le impostazioni del Bridge di audioconferenza dell'organizzazione, vedere [modificare le impostazioni per un Bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="3912d-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="3912d-145">Passaggio 8: (facoltativo) impostare i numeri di telefono inclusi negli inviti alla riunione degli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3912d-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="3912d-146">Per modificare il set di numeri di telefono inclusi negli inviti alla riunione degli utenti è la propria organizzazione, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3912d-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="3912d-147">Funzionalità di conferenza audio non supportate in servizi di audioconferenza con routing diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="3912d-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="3912d-148">Di seguito sono riportate funzionalità di conferenza audio non supportate in servizi di audioconferenza con routing diretto per GCC High e DoD:</span><span class="sxs-lookup"><span data-stu-id="3912d-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="3912d-149">Notifiche di entrata e uscita tramite registrazione nomi.</span><span class="sxs-lookup"><span data-stu-id="3912d-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="3912d-150">Per i servizi di audioconferenza con routing diretto, le notifiche di entrata e uscita vengono riprodotte nella riunione come toni.</span><span class="sxs-lookup"><span data-stu-id="3912d-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="3912d-151">Criteri di restrizione delle chiamate in uscita per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3912d-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="3912d-152">I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate di chiamata in uscita per le riunioni instradate tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="3912d-152">User-level controls to restrict outbound calls aren’t applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="3912d-153">Disabilitare l'uso di numeri verdi per l'organizzatore di riunioni specifico.</span><span class="sxs-lookup"><span data-stu-id="3912d-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="3912d-154">I controlli a livello di utente per limitare l'uso di numeri verdi per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradate tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="3912d-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren’t applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="3912d-155">Invio di messaggi di notifica agli utenti quando cambiano le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3912d-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="3912d-156">I messaggi di notifica per i servizi di audioconferenza non sono supportati per le conferenze audio con routing diretto per GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="3912d-156">Audio Conferencing notification emails aren’t supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
