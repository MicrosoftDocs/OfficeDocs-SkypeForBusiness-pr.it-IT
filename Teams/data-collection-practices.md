---
title: Pratiche di raccolta dati
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft raccoglie i dati di censimento, utilizzo e errore per capire in che modo viene usato Skype for business e dove gli utenti incontrano problemi. I dati vengono usati per pianificare i miglioramenti del prodotto.
ms.openlocfilehash: 532cfe380a9f61043e38768c4c5d7d9c9fa8e9a6
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183691"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="7889b-104">Procedure per la raccolta di dati in Skype for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7889b-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="7889b-105">Skype for Business Server e Skype for business online, insieme alle app Skype for business e Microsoft teams, raccolgono dati per aiutare Microsoft a capire come vengono usati questi prodotti e quali tipi di errori, ad esempio gli errori di accesso, si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="7889b-105">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="7889b-106">Queste informazioni consentono di comprendere i modelli di utilizzo, pianificare le nuove funzionalità e risolvere i problemi e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="7889b-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="7889b-107">Mentre alcuni dati di utilizzo vengono raccolti automaticamente, gli altri dati possono essere raccolti solo quando l'amministratore e/o l'utente sceglie di consentirlo.</span><span class="sxs-lookup"><span data-stu-id="7889b-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="7889b-108">La raccolta dei dati rientra in queste tre categorie:</span><span class="sxs-lookup"><span data-stu-id="7889b-108">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="7889b-109">Dati del censimento</span><span class="sxs-lookup"><span data-stu-id="7889b-109">Census data</span></span>

- <span data-ttu-id="7889b-110">Dati sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="7889b-110">Usage data</span></span>

- <span data-ttu-id="7889b-111">Dati della segnalazione degli errori</span><span class="sxs-lookup"><span data-stu-id="7889b-111">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="7889b-112">Dati del censimento</span><span class="sxs-lookup"><span data-stu-id="7889b-112">Census data</span></span>

<span data-ttu-id="7889b-113">I dati del censimento vengono acquisiti solo per consentire, supportare e migliorare Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7889b-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="7889b-114">Microsoft teams e Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="7889b-114">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="7889b-115">Include informazioni ambientali come le versioni del dispositivo e del sistema operativo e le impostazioni internazionali e della lingua.</span><span class="sxs-lookup"><span data-stu-id="7889b-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="7889b-116">Include anche contatori per tentativi di accesso e errori.</span><span class="sxs-lookup"><span data-stu-id="7889b-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="7889b-117">Ecco alcuni esempi specifici dei dati del censimento raccolti:</span><span class="sxs-lookup"><span data-stu-id="7889b-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="7889b-118">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="7889b-118">**Data type**</span></span>|<span data-ttu-id="7889b-119">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="7889b-119">**Example**</span></span>|<span data-ttu-id="7889b-120">**Note**</span><span class="sxs-lookup"><span data-stu-id="7889b-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7889b-121">NomeApp</span><span class="sxs-lookup"><span data-stu-id="7889b-121">AppName</span></span>  <br/> |<span data-ttu-id="7889b-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="7889b-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="7889b-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="7889b-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="7889b-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="7889b-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="7889b-125">OSName</span><span class="sxs-lookup"><span data-stu-id="7889b-125">OSName</span></span>  <br/> |<span data-ttu-id="7889b-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="7889b-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="7889b-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="7889b-127">OSVersion</span></span>  <br/> |<span data-ttu-id="7889b-128">8,3</span><span class="sxs-lookup"><span data-stu-id="7889b-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="7889b-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="7889b-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="7889b-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="7889b-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="7889b-131">UserID</span><span class="sxs-lookup"><span data-stu-id="7889b-131">UserID</span></span>  <br/> |<span data-ttu-id="7889b-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="7889b-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="7889b-133">L'ID viene hashato due volte: una volta sul client e di nuovo sul servizio di telemetria.</span><span class="sxs-lookup"><span data-stu-id="7889b-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="7889b-134">L'hashing garantisce che l'ID non possa essere collegato a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="7889b-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="7889b-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="7889b-135">DeviceID</span></span>  <br/> |<span data-ttu-id="7889b-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="7889b-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="7889b-137">L'ID dispositivo è un GUID generato in modo casuale una volta sul dispositivo e inviato al servizio di telemetria.</span><span class="sxs-lookup"><span data-stu-id="7889b-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="7889b-138">I dati del censimento non contengono informazioni che identifichino l'organizzazione o gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7889b-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="7889b-139">Per altre informazioni, vedere l'informativa [sulla privacy di Skype for business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7889b-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="7889b-140">I dati del censimento sono attivati per impostazione predefinita e non possono essere disattivati da amministratori o utenti finali.</span><span class="sxs-lookup"><span data-stu-id="7889b-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="7889b-141">Dati sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="7889b-141">Usage data</span></span>

<span data-ttu-id="7889b-142">I dati sull'utilizzo includono informazioni come il numero di chiamate effettuate, il numero di messaggi istantanei inviati o ricevuti, il numero di riunioni Unite, la frequenza delle caratteristiche usate e i problemi di stabilità.</span><span class="sxs-lookup"><span data-stu-id="7889b-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="7889b-143">I dati di utilizzo possono contenere informazioni che identificano l'organizzazione, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7889b-143">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="7889b-144">Ecco alcuni esempi specifici dei dati di utilizzo raccolti:</span><span class="sxs-lookup"><span data-stu-id="7889b-144">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="7889b-145">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="7889b-145">**Data type**</span></span>|<span data-ttu-id="7889b-146">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="7889b-146">**Example**</span></span>|<span data-ttu-id="7889b-147">**Note**</span><span class="sxs-lookup"><span data-stu-id="7889b-147">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7889b-148">Messaggio istantaneo inviato</span><span class="sxs-lookup"><span data-stu-id="7889b-148">IM Sent</span></span>  <br/> |<span data-ttu-id="7889b-149">12</span><span class="sxs-lookup"><span data-stu-id="7889b-149">12</span></span>  <br/> ||
|<span data-ttu-id="7889b-150">Messaggi istantanei ricevuti</span><span class="sxs-lookup"><span data-stu-id="7889b-150">IM Received</span></span>  <br/> |<span data-ttu-id="7889b-151">5</span><span class="sxs-lookup"><span data-stu-id="7889b-151">5</span></span>  <br/> ||
|<span data-ttu-id="7889b-152">Partecipare a una riunione (tentativi)</span><span class="sxs-lookup"><span data-stu-id="7889b-152">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="7889b-153">5</span><span class="sxs-lookup"><span data-stu-id="7889b-153">5</span></span>  <br/> ||
|<span data-ttu-id="7889b-154">Partecipare a una riunione (esito positivo)</span><span class="sxs-lookup"><span data-stu-id="7889b-154">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="7889b-155">4</span><span class="sxs-lookup"><span data-stu-id="7889b-155">4</span></span>  <br/> ||
|<span data-ttu-id="7889b-156">Minuti di chiamata/riunione</span><span class="sxs-lookup"><span data-stu-id="7889b-156">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="7889b-157">30 minuti</span><span class="sxs-lookup"><span data-stu-id="7889b-157">30 mins</span></span>  <br/> ||
|<span data-ttu-id="7889b-158">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="7889b-158">FederationPartner</span></span>  <br/> |<span data-ttu-id="7889b-159">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7889b-159">Microsoft.com</span></span>  <br/> |<span data-ttu-id="7889b-160">Questo è il nome dell'organizzazione registrata in Office 365 e viene trasmessa in testo non crittografato, quindi non è offuscata.</span><span class="sxs-lookup"><span data-stu-id="7889b-160">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="7889b-161">I dati di utilizzo non contengono informazioni che identifichino gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7889b-161">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="7889b-162">La raccolta dei dati di utilizzo è attiva per impostazione predefinita, ma gli amministratori locali possono disattivarla usando l'impostazione dei criteri di gruppo di DisableAutomaticSendTracing in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7889b-162">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="7889b-163">La disattivazione di questa impostazione interessa tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7889b-163">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="7889b-164">Per altre informazioni, vedere [configurare i criteri di avvio del client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .</span><span class="sxs-lookup"><span data-stu-id="7889b-164">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="7889b-165">Gli utenti finali non possono attivare o disattivare la raccolta dati sull'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="7889b-165">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="7889b-166">Per le app riunioni Skype e le pagine Web di avvio join, il modo per controllare la telemetria è attraverso questo criterio:</span><span class="sxs-lookup"><span data-stu-id="7889b-166">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="7889b-167">Questo criterio viene impostato su false, quindi la raccolta di telemetria è disinserita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7889b-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="7889b-168">Questa impostazione è per pool e controlla tutti gli utenti che si connettono con l'app riunioni Skype a una riunione ospitata nel server.</span><span class="sxs-lookup"><span data-stu-id="7889b-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="7889b-169">Dati della segnalazione degli errori</span><span class="sxs-lookup"><span data-stu-id="7889b-169">Error reporting data</span></span>

<span data-ttu-id="7889b-170">I dati di segnalazione degli errori possono includere informazioni su prestazioni e affidabilità, configurazione dei dispositivi, qualità della connessione di rete, codici di errore, registri degli errori ed eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7889b-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="7889b-171">Ecco alcuni esempi specifici di dati di segnalazione degli errori raccolti:</span><span class="sxs-lookup"><span data-stu-id="7889b-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="7889b-172">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="7889b-172">**Data type**</span></span>|<span data-ttu-id="7889b-173">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="7889b-173">**Example**</span></span>|<span data-ttu-id="7889b-174">**Note**</span><span class="sxs-lookup"><span data-stu-id="7889b-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7889b-175">Direzione del messaggio</span><span class="sxs-lookup"><span data-stu-id="7889b-175">Message direction</span></span>  <br/> |<span data-ttu-id="7889b-176">In arrivo</span><span class="sxs-lookup"><span data-stu-id="7889b-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="7889b-177">Stato conversazione</span><span class="sxs-lookup"><span data-stu-id="7889b-177">Conversation state</span></span>  <br/> |<span data-ttu-id="7889b-178">Inattivo</span><span class="sxs-lookup"><span data-stu-id="7889b-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="7889b-179">ID thread di conversazione</span><span class="sxs-lookup"><span data-stu-id="7889b-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="7889b-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="7889b-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="7889b-181">UserID</span><span class="sxs-lookup"><span data-stu-id="7889b-181">UserID</span></span>  <br/> |<span data-ttu-id="7889b-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="7889b-182">amosmarble</span></span> <br/> |<span data-ttu-id="7889b-183">L'ID viene inviato in testo non crittografato, a cui il servizio di telemetria viene hashato prima di archiviarlo</span><span class="sxs-lookup"><span data-stu-id="7889b-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="7889b-184">I dati di segnalazione degli errori possono contenere anche informazioni personali, ad esempio l'indirizzo IP dell'utente e l'URI SIP (Uniform Resource Identifier) del protocollo di avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="7889b-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="7889b-185">Vedere l' [informativa sulla privacy di Skype for business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) per una spiegazione dettagliata delle raccolte.</span><span class="sxs-lookup"><span data-stu-id="7889b-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="7889b-186">La segnalazione degli errori richiede due elementi:</span><span class="sxs-lookup"><span data-stu-id="7889b-186">Error reporting requires two things:</span></span>

- <span data-ttu-id="7889b-187">L'impostazione di criteri di gruppo di DisableAutomaticSendTracing è impostata su false nel server o nell'interfaccia di amministrazione del tenant (questo è lo stato predefinito).</span><span class="sxs-lookup"><span data-stu-id="7889b-187">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="7889b-188">Per altre informazioni, vedere [configurare i criteri di avvio del client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .</span><span class="sxs-lookup"><span data-stu-id="7889b-188">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="7889b-189">Gli utenti finali scelgono individualmente l'opt-in dalla scheda generale ![(fare clic sull'icona a ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) ingranaggio un'icona che rappresenta un ingranaggio e quindi la finestra di dialogo **Opzioni** si apre con la scheda **generale** visualizzata) nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7889b-189">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Screenshot della casella di controllo raccolta dati nella finestra di dialogo Opzioni](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="7889b-191">Per l'app riunioni Skype, MeetingUxEnableTelemetry controlla anche la segnalazione degli errori, anche se per gli arresti anomali in Windows, il controllo delle impostazioni di Watson carica le informazioni sull'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="7889b-191">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="7889b-192">Non sono disponibili impostazioni utente per l'app riunioni Skype, come nella finestra di dialogo client desktop.</span><span class="sxs-lookup"><span data-stu-id="7889b-192">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="7889b-193">Per altre informazioni, vedere [impostare le opzioni generali in Skype for business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .</span><span class="sxs-lookup"><span data-stu-id="7889b-193">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="7889b-194">Per configurare la rete, è possibile vedere [configurare la rete per Skype for business online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) .</span><span class="sxs-lookup"><span data-stu-id="7889b-194">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="7889b-195">Se si usa Office 365 gestito da 21Vianet in Cina, vedere [configurare la rete per Skype for business online gestito da 21ViaNet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="7889b-195">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7889b-196">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7889b-196">Related topics</span></span>
[<span data-ttu-id="7889b-197">Programma Analisi utilizzo software</span><span class="sxs-lookup"><span data-stu-id="7889b-197">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/default.mspx)

[<span data-ttu-id="7889b-198">Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="7889b-198">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
