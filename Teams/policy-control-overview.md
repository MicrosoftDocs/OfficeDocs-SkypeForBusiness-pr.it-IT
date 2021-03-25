---
title: Panoramica sui controlli dei criteri di Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Panoramica dei controlli dei criteri per Microsoft teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4e87103a5325e231bb07ca56ee5c14b8f48294a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117784"
---
# <a name="policy-control-overview-for-microsoft-teams"></a><span data-ttu-id="6fef9-103">Panoramica sui controlli dei criteri di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fef9-103">Policy control overview for Microsoft Teams</span></span>

<span data-ttu-id="6fef9-104">Microsoft si impegna a fornire le informazioni e i controlli necessari per scegliere le modalità di raccolta e utilizzo dei dati quando si usa Microsoft Teams, incluso in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6fef9-104">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Teams, a part of Microsoft 365.</span></span>

<span data-ttu-id="6fef9-105">Questo articolo ha lo scopo di fornire informazioni sui controlli per la privacy per le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fef9-105">This article is intended to provide you with information about privacy controls for the following areas:</span></span>

- <span data-ttu-id="6fef9-106">**Dati di diagnostica** che vengono raccolti e inviati a Microsoft sul software client di Office in uso nei computer che eseguono Teams e Office all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6fef9-106">**Diagnostic data** that is collected and sent to Microsoft about Teams and Office software being used on computers running Windows in your organization.</span></span>
- <span data-ttu-id="6fef9-107">**Esperienze connesse** che usano funzionalità basate sul cloud per offrire funzionalità avanzate di Teams e Office agli utenti.</span><span class="sxs-lookup"><span data-stu-id="6fef9-107">**Connected experiences** that use cloud-based functionality to provide enhanced Teams and Office features to you and your users.</span></span>

<span data-ttu-id="6fef9-108">Nell'ambito di queste modifiche, nell'interfaccia utente vengono introdotti nuovi elementi e nuove impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="6fef9-108">As part of these changes, there are new and updated user interface (UI) elements and policy settings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fef9-109">Per altre informazioni, vedere la sezione della [Panoramica sui controlli dei criteri](/deployoffice/privacy/overview-privacy-controls) relativa a M365.</span><span class="sxs-lookup"><span data-stu-id="6fef9-109">For further reading, please review the [Policy Control Overview](/deployoffice/privacy/overview-privacy-controls) content for M365.</span></span>

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a><span data-ttu-id="6fef9-110">Dati di diagnostica inviati da Microsoft 365 Apps for enterprise a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fef9-110">Diagnostic data sent from Microsoft 365 Apps for enterprise to Microsoft</span></span>

<span data-ttu-id="6fef9-111">I dati di diagnostica sono usati per:</span><span class="sxs-lookup"><span data-stu-id="6fef9-111">Diagnostic data is used to:</span></span>

- <span data-ttu-id="6fef9-112">Mantenere Teams sicuro e aggiornato.</span><span class="sxs-lookup"><span data-stu-id="6fef9-112">Keep Teams secure and up-to-date.</span></span>
- <span data-ttu-id="6fef9-113">Individuare, diagnosticare e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="6fef9-113">Detect, diagnose and remediate problems.</span></span>
- <span data-ttu-id="6fef9-114">Migliorare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="6fef9-114">Make product improvements.</span></span>

<span data-ttu-id="6fef9-115">Alcuni esempi dei dati raccolti includono:</span><span class="sxs-lookup"><span data-stu-id="6fef9-115">An example of some of the collected data includes:</span></span>

- <span data-ttu-id="6fef9-116">Lingua dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6fef9-116">Application language</span></span>
- <span data-ttu-id="6fef9-117">Tipo di utente</span><span class="sxs-lookup"><span data-stu-id="6fef9-117">User type</span></span>
- <span data-ttu-id="6fef9-118">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6fef9-118">Build version of the OS</span></span>

## <a name="clients-that-adhere-to-diagnostic-controls"></a><span data-ttu-id="6fef9-119">Client che aderiscono ai controlli diagnostici</span><span class="sxs-lookup"><span data-stu-id="6fef9-119">Clients that adhere to diagnostic controls</span></span>

<span data-ttu-id="6fef9-120">I client seguenti sono sottoposti ai controlli diagnostici e inviano dati:</span><span class="sxs-lookup"><span data-stu-id="6fef9-120">The following clients adhere to diagnostic controls and will submit data:</span></span>

- <span data-ttu-id="6fef9-121">iOS</span><span class="sxs-lookup"><span data-stu-id="6fef9-121">iOS</span></span>
- <span data-ttu-id="6fef9-122">Android</span><span class="sxs-lookup"><span data-stu-id="6fef9-122">Android</span></span>
- <span data-ttu-id="6fef9-123">Desktop (solo il componente che usa l'API win32)</span><span class="sxs-lookup"><span data-stu-id="6fef9-123">Desktop (only the component that is using the win32 API)</span></span>

<span data-ttu-id="6fef9-124">Per i dati diagnostica per dispositivi mobili necessari, vedere [Controlli dei criteri dei dati di diagnostica per dispositivi mobili](policy-control-diagnostic-data-mobile.md).</span><span class="sxs-lookup"><span data-stu-id="6fef9-124">For required mobile data diagnostics, see [Policy control diagnostic data for mobile](policy-control-diagnostic-data-mobile.md).</span></span>

<span data-ttu-id="6fef9-125">Per i dati diagnostica desktop necessari, vedere [Controlli dei criteri dei dati di diagnostica desktop](policy-control-diagnostic-data-desktop.md).</span><span class="sxs-lookup"><span data-stu-id="6fef9-125">For required desktop data diagnostics, see [Policy control diagnostic data for desktop](policy-control-diagnostic-data-desktop.md).</span></span>

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a><span data-ttu-id="6fef9-126">Dati di diagnostica inviati da Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fef9-126">Diagnostic data sent from the Teams app to Microsoft</span></span>

<span data-ttu-id="6fef9-127">Questi dati di diagnostica raccolti e inviati a Microsoft riguardano il software Teams in uso su computer che eseguono Windows all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6fef9-127">This diagnostic data is collected and sent to Microsoft about Teams software being used on computers running Windows in your organization.</span></span>

<span data-ttu-id="6fef9-128">Esistono tre livelli di dati di diagnostica per il software Teams tra cui è possibile scegliere:</span><span class="sxs-lookup"><span data-stu-id="6fef9-128">There are three levels of diagnostic data for Teams software that you can choose from:</span></span>

- <span data-ttu-id="6fef9-129">**Obbligatorio** I dati minimi necessari per mantenere Office sicuro, aggiornato e correttamente funzionante nel dispositivo sono installati. </span><span class="sxs-lookup"><span data-stu-id="6fef9-129">**Required** The minimum data necessary to help keep Office secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>
- <span data-ttu-id="6fef9-130">**Facoltativo** Dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="6fef9-130">**Optional** Additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and remediate issues.</span></span>
- <span data-ttu-id="6fef9-131">**Nessuno** Nessun dato diagnostico sul software Teams in esecuzione nel dispositivo dell’utente viene raccolto o inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fef9-131">**Neither** No diagnostic data about Teams software running on the user’s device is collected and sent to us.</span></span> <span data-ttu-id="6fef9-132">Questa opzione, tuttavia, limita in modo significativo la possibilità di rilevare, diagnosticare e risolvere i problemi che gli utenti potrebbero riscontrare durante l’uso di Teams.</span><span class="sxs-lookup"><span data-stu-id="6fef9-132">This option, however, significantly limits our ability to detect, diagnose, and remediate problems your users may encounter using Teams.</span></span>

<span data-ttu-id="6fef9-133">I dati di diagnostici necessari possono includere, ad esempio, informazioni sulla versione del client di Teams installata nel dispositivo, o informazioni che indicano che Teams si arresta in modo anomalo quando si prova a partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="6fef9-133">Required diagnostic data could include, for example, information about the version of Teams client installed on the device, or include information that indicates that the Teams application is crashing when trying to join a meeting.</span></span> <span data-ttu-id="6fef9-134">I dati di diagnostica facoltativi possono includere informazioni sul tempo necessario per avviare una telefonata, che potrebbero indicare un problema relativo alla connettività o alle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="6fef9-134">Optional diagnostic data could include information about the time it takes to initiate a phone call, which could indicate an issue with connectivity or network performance.</span></span>

<span data-ttu-id="6fef9-135">Se si sceglie di inviare i dati di diagnostica facoltativi, saranno inclusi anche i dati indispensabili.</span><span class="sxs-lookup"><span data-stu-id="6fef9-135">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="6fef9-136">Come amministratori della propria organizzazione, sarà possibile utilizzare un'impostazione di criterio per scegliere il livello di dati di diagnostica da inviare a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fef9-136">As an admin for your organization, you’ll be able to use a policy setting to choose which level of diagnostic data is sent to us.</span></span> <span data-ttu-id="6fef9-137">I dati di diagnostica facoltativi verranno inviati a Microsoft se non si modificano le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6fef9-137">Optional diagnostic data will be sent to Microsoft unless you change the setting.</span></span> <span data-ttu-id="6fef9-138">I dati di diagnostica facoltativi consentono al team di progettazione di Office a Microsoft di rilevare, diagnosticare e ridurre in modo più efficiente i problemi e attenuare il loro impatto sulla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6fef9-138">Providing optional diagnostic data better enables the Office engineering team at Microsoft to detect, diagnose, and mitigate issues to reduce impacts to your organization.</span></span>

<span data-ttu-id="6fef9-139">I propri utenti non saranno in grado di modificare il livello di dati di diagnostica per i dispositivi, se si trovano connessi a Teams con le credenziali dell'organizzazione, a volte definita azienda o istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="6fef9-139">Your users won’t be able to change the diagnostic data level for their devices if they are signed in to Teams with their organizational credentials, which is sometimes referred to as a work or school account.</span></span>

<span data-ttu-id="6fef9-140">Tali dati diagnostici non includono i nomi degli utenti, il proprio indirizzo di posta elettronica o il contenuto dei file di Office.</span><span class="sxs-lookup"><span data-stu-id="6fef9-140">This diagnostic data doesn’t include names of users, their email addresses, or the content of their Office files.</span></span> <span data-ttu-id="6fef9-141">Il sistema crea un ID univoco che si associa ai dati di diagnostica degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6fef9-141">Our system creates a unique ID that it associates with your user’s diagnostic data.</span></span> <span data-ttu-id="6fef9-142">Alla ricezione di dati di diagnostica che mostrano l’arresto anomalo di Teams per 100 volte, questo ID univoco consente di determinare se si tratta di un singolo utente che ha subito l’arresto anomalo dell’app per 100 ore o se si tratta di 100 utenti diversi che hanno subito l’arresto anomalo dell’app una sola volta.</span><span class="sxs-lookup"><span data-stu-id="6fef9-142">When we receive diagnostic data showing that the Teams app crashed 100 times, this unique ID lets us determine if it was a single user who crashed 100 times or if it was 100 different users who each crashed once.</span></span> <span data-ttu-id="6fef9-143">Microsoft non usa l'ID univoco per identificare un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="6fef9-143">We don’t use this unique ID to identify a specific user.</span></span>

## <a name="required-service-data-for-connected-experiences"></a><span data-ttu-id="6fef9-144">Dati di servizio obbligatori per le esperienze connesse</span><span class="sxs-lookup"><span data-stu-id="6fef9-144">Required service data for connected experiences</span></span>

<span data-ttu-id="6fef9-145">I dati di servizio obbligatori sono dati che consentono di fornire queste esperienze connesse basate sul cloud garantendo che siano sicure e correttamente funzionanti.</span><span class="sxs-lookup"><span data-stu-id="6fef9-145">Required service data is data that enables us to deliver these cloud-based connected experiences and help make these experiences secure and perform as expected.</span></span> <span data-ttu-id="6fef9-146">I dati di servizio obbligatori comprendono tre tipi di informazioni.</span><span class="sxs-lookup"><span data-stu-id="6fef9-146">Three types of information make up required service data.</span></span>

- <span data-ttu-id="6fef9-147">**Contenuto dei clienti**, ovvero contenuto creato con Office dagli utenti, ad esempio il testo digitato in un documento di Word.</span><span class="sxs-lookup"><span data-stu-id="6fef9-147">**Customer content**, which is content you create using Office, such as text typed in a Word document.</span></span>
- <span data-ttu-id="6fef9-148">**Dati funzionali**, che includono le informazioni necessarie alle esperienze connesse per eseguire le attività, ad esempio informazioni di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="6fef9-148">**Functional data**, which includes information needed by a connected experience to perform its task, such as configuration information about the app.</span></span>
- <span data-ttu-id="6fef9-149">**Dati di diagnostica del servizio**, ovvero i dati necessari per mantenere il servizio sicuro, aggiornato e garantire le prestazioni ottimali previste.</span><span class="sxs-lookup"><span data-stu-id="6fef9-149">**Service diagnostic data**, which is the data necessary to keep the service secure, up to date, and performing as expected.</span></span> <span data-ttu-id="6fef9-150">Poiché questi dati sono strettamente correlati all'esperienza connessa, sono separati dai livelli di dati di diagnostica indispensabili o facoltativi.</span><span class="sxs-lookup"><span data-stu-id="6fef9-150">Because this data is strictly related to the connected experience, it is separate from required or optional diagnostic data levels.</span></span>

<span data-ttu-id="6fef9-151">È possibile scegliere di non offrire questa funzionalità agli utenti. In questo caso, le informazioni non saranno fornite a Microsoft per supportare la funzionalità delle esperienze connesse.</span><span class="sxs-lookup"><span data-stu-id="6fef9-151">You can choose to not offer this functionality to your users, in which case this information will not be provided to Microsoft to support the functionality of connected experiences.</span></span> <span data-ttu-id="6fef9-152">Sono disponibili altre informazioni sui [dati di servizio necessari](/deployoffice/privacy/required-service-data).</span><span class="sxs-lookup"><span data-stu-id="6fef9-152">You can learn more about [required service data](/deployoffice/privacy/required-service-data).</span></span>

## <a name="essential-services-for-microsoft-teams"></a><span data-ttu-id="6fef9-153">Servizi essenziali per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fef9-153">Essential services for Microsoft Teams</span></span>

<span data-ttu-id="6fef9-154">Esiste anche una serie di servizi che sono essenziali per il funzionamento di Microsoft 365 Apps for enterprise e non possono essere disabilitati.</span><span class="sxs-lookup"><span data-stu-id="6fef9-154">There are also a set of services that are essential to how Microsoft 365 Apps for enterprise functions and cannot be disabled.</span></span> <span data-ttu-id="6fef9-155">Ad esempio, il servizio gestione licenze che conferma che si dispone di una licenza per Microsoft 365 Apps for enterprise.</span><span class="sxs-lookup"><span data-stu-id="6fef9-155">For example, the licensing service that confirms that you are properly licensed to use Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="6fef9-156">I dati di servizio obbligatori su questi servizi vengono raccolti e inviati a Microsoft indipendentemente dalle altre impostazioni dei criteri configurate.</span><span class="sxs-lookup"><span data-stu-id="6fef9-156">Required service data about these services is collected and sent to Microsoft, regardless of any other policy settings that you have configured.</span></span>

<span data-ttu-id="6fef9-157">Per altre informazioni, vedere [Servizi essenziali per Office](/deployoffice/privacy/essential-services).</span><span class="sxs-lookup"><span data-stu-id="6fef9-157">For more information, see [Essential services for Office](/deployoffice/privacy/essential-services).</span></span>