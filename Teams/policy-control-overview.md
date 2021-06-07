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
ms.openlocfilehash: 1a4b0dcc52b5c497d594a26fda09f3f48b1c563a
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777903"
---
# <a name="policy-control-overview-for-microsoft-teams"></a><span data-ttu-id="d1150-103">Panoramica sui controlli dei criteri di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1150-103">Policy control overview for Microsoft Teams</span></span>

<span data-ttu-id="d1150-104">Microsoft si impegna a fornire le informazioni e i controlli necessari per scegliere le modalità di raccolta e utilizzo dei dati quando si usa Microsoft Teams, incluso in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1150-104">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Teams, a part of Microsoft 365.</span></span>

<span data-ttu-id="d1150-105">Questo articolo ha lo scopo di fornire informazioni sui controlli per la privacy per le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1150-105">This article is intended to provide you with information about privacy controls for the following areas:</span></span>

- <span data-ttu-id="d1150-106">**Dati di diagnostica** che vengono raccolti e inviati a Microsoft sul software client di Office in uso nei computer che eseguono Teams e Office all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1150-106">**Diagnostic data** that is collected and sent to Microsoft about Teams and Office software being used on computers running Windows in your organization.</span></span>
- <span data-ttu-id="d1150-107">**Esperienze connesse** che usano funzionalità basate sul cloud per offrire funzionalità avanzate di Teams e Office agli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1150-107">**Connected experiences** that use cloud-based functionality to provide enhanced Teams and Office features to you and your users.</span></span>

<span data-ttu-id="d1150-108">Nell'ambito di queste modifiche, nell'interfaccia utente vengono introdotti nuovi elementi e nuove impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d1150-108">As part of these changes, there are new and updated user interface (UI) elements and policy settings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1150-109">Per altre informazioni, vedere la sezione della [Panoramica sui controlli dei criteri](/deployoffice/privacy/overview-privacy-controls) relativa a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1150-109">For further reading, please review the [Policy Control Overview](/deployoffice/privacy/overview-privacy-controls) content for Microsoft 365.</span></span>

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a><span data-ttu-id="d1150-110">Dati di diagnostica inviati da Microsoft 365 Apps for enterprise a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d1150-110">Diagnostic data sent from Microsoft 365 Apps for enterprise to Microsoft</span></span>

<span data-ttu-id="d1150-111">I dati di diagnostica sono usati per:</span><span class="sxs-lookup"><span data-stu-id="d1150-111">Diagnostic data is used to:</span></span>

- <span data-ttu-id="d1150-112">Mantenere Teams sicuro e aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d1150-112">Keep Teams secure and up-to-date.</span></span>
- <span data-ttu-id="d1150-113">Individuare, diagnosticare e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="d1150-113">Detect, diagnose, and remediate problems.</span></span>
- <span data-ttu-id="d1150-114">Migliorare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="d1150-114">Make product improvements.</span></span>

<span data-ttu-id="d1150-115">Alcuni esempi dei dati raccolti includono:</span><span class="sxs-lookup"><span data-stu-id="d1150-115">An example of some of the collected data includes:</span></span>

- <span data-ttu-id="d1150-116">Lingua dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d1150-116">Application language</span></span>
- <span data-ttu-id="d1150-117">Tipo di utente</span><span class="sxs-lookup"><span data-stu-id="d1150-117">User type</span></span>
- <span data-ttu-id="d1150-118">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d1150-118">Build version of the OS</span></span>

## <a name="clients-that-adhere-to-diagnostic-controls"></a><span data-ttu-id="d1150-119">Client che aderiscono ai controlli diagnostici</span><span class="sxs-lookup"><span data-stu-id="d1150-119">Clients that adhere to diagnostic controls</span></span>

<span data-ttu-id="d1150-120">I client seguenti sono sottoposti ai controlli diagnostici e inviano dati:</span><span class="sxs-lookup"><span data-stu-id="d1150-120">The following clients adhere to diagnostic controls and will submit data:</span></span>

- <span data-ttu-id="d1150-121">iOS</span><span class="sxs-lookup"><span data-stu-id="d1150-121">iOS</span></span>
- <span data-ttu-id="d1150-122">Android</span><span class="sxs-lookup"><span data-stu-id="d1150-122">Android</span></span>
- <span data-ttu-id="d1150-123">Desktop (solo il componente che usa l'API win32)</span><span class="sxs-lookup"><span data-stu-id="d1150-123">Desktop (only the component that is using the win32 API)</span></span>

<span data-ttu-id="d1150-124">Per visualizzare un elenco degli eventi dei dati di diagnostica obbligatori necessari e delle relative proprietà, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1150-124">To see a list of required diagnostic data events and their properties, see the following articles:</span></span>

- [<span data-ttu-id="d1150-125">Dati di diagnostica necessari per dispositivo mobile di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1150-125">Required mobile diagnostic data for Microsoft Teams</span></span>](policy-control-diagnostic-data-mobile.md)
- [<span data-ttu-id="d1150-126">Dati di diagnostica necessari per la versione desktop di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1150-126">Required desktop diagnostic data for Microsoft Teams</span></span>](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a><span data-ttu-id="d1150-127">Dati di diagnostica inviati da Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d1150-127">Diagnostic data sent from the Teams app to Microsoft</span></span>

<span data-ttu-id="d1150-128">Questi dati di diagnostica raccolti e inviati a Microsoft riguardano il software Teams in uso su computer che eseguono Windows all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1150-128">This diagnostic data is collected and sent to Microsoft about Teams software being used on computers running Windows in your organization.</span></span>

<span data-ttu-id="d1150-129">Esistono tre livelli di dati di diagnostica per il software Teams tra cui è possibile scegliere:</span><span class="sxs-lookup"><span data-stu-id="d1150-129">There are three levels of diagnostic data for Teams software that you can choose from:</span></span>

- <span data-ttu-id="d1150-130">**Obbligatorio** I dati minimi necessari per mantenere Office sicuro, aggiornato e correttamente funzionante nel dispositivo sono installati. </span><span class="sxs-lookup"><span data-stu-id="d1150-130">**Required** The minimum data necessary to help keep Office secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>
- <span data-ttu-id="d1150-131">**Facoltativo** Dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="d1150-131">**Optional** Additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and remediate issues.</span></span>
- <span data-ttu-id="d1150-132">**Nessuno** Nessun dato diagnostico sul software Teams in esecuzione nel dispositivo dell’utente viene raccolto o inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1150-132">**Neither** No diagnostic data about Teams software running on the user’s device is collected and sent to us.</span></span> <span data-ttu-id="d1150-133">Questa opzione, tuttavia, limita in modo significativo la possibilità di rilevare, diagnosticare e risolvere i problemi che gli utenti potrebbero riscontrare durante l’uso di Teams.</span><span class="sxs-lookup"><span data-stu-id="d1150-133">This option, however, significantly limits our ability to detect, diagnose, and remediate problems your users may encounter using Teams.</span></span>

<span data-ttu-id="d1150-134">I dati di diagnostici necessari possono includere, ad esempio, informazioni sulla versione del client di Teams installata nel dispositivo, o informazioni che indicano che Teams si arresta in modo anomalo quando si prova a partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d1150-134">Required diagnostic data could include, for example, information about the version of Teams client installed on the device, or include information that indicates that the Teams application is crashing when trying to join a meeting.</span></span> <span data-ttu-id="d1150-135">I dati di diagnostica facoltativi possono includere informazioni sul tempo necessario per avviare una telefonata, che potrebbero indicare un problema relativo alla connettività o alle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="d1150-135">Optional diagnostic data could include information about the time it takes to initiate a phone call, which could indicate an issue with connectivity or network performance.</span></span>

<span data-ttu-id="d1150-136">Se si sceglie di inviare i dati di diagnostica facoltativi, saranno inclusi anche i dati indispensabili.</span><span class="sxs-lookup"><span data-stu-id="d1150-136">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="d1150-137">Come amministratori della propria organizzazione, sarà possibile utilizzare un'impostazione di criterio per scegliere il livello di dati di diagnostica da inviare a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1150-137">As an admin for your organization, you’ll be able to use a policy setting to choose which level of diagnostic data is sent to us.</span></span> <span data-ttu-id="d1150-138">I dati di diagnostica facoltativi verranno inviati a Microsoft se non si modificano le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d1150-138">Optional diagnostic data will be sent to Microsoft unless you change the setting.</span></span> <span data-ttu-id="d1150-139">I dati di diagnostica facoltativi consentono al team di progettazione di Office a Microsoft di rilevare, diagnosticare e ridurre in modo più efficiente i problemi e attenuare il loro impatto sulla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1150-139">Providing optional diagnostic data better enables the Office engineering team at Microsoft to detect, diagnose, and mitigate issues to reduce impacts to your organization.</span></span> 

<span data-ttu-id="d1150-140">Per scegliere il livello di dati di diagnostica che ci viene inviato, utilizzare il [servizio criteri cloud di Office](/deployoffice/overview-office-cloud-policy-service) e configurare l'impostazione dei criteri *Configura il livello dei dati di diagnostica del software client inviati da Office a Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="d1150-140">To choose which level of diagnostic data is sent to us, use the [Office cloud policy service](/deployoffice/overview-office-cloud-policy-service) and configure the *Configure the level of client software diagnostic data sent by Office to Microsoft* policy setting.</span></span> <span data-ttu-id="d1150-141">Si tratta della stessa impostazione dei criteri usata per configurare il livello di dati di diagnostica inviato da altre app di Office (ad esempio Word, Excel e PowerPoint) che sono incluse tra le app di Microsoft 365 Apps for enterprise.</span><span class="sxs-lookup"><span data-stu-id="d1150-141">This is the same policy setting that is used to configure which level of diagnostic data is sent by other Office apps (such as Word, Excel, and PowerPoint) that come with Microsoft 365 Apps for enterprise.</span></span>

<span data-ttu-id="d1150-142">I propri utenti non saranno in grado di modificare il livello di dati di diagnostica per i dispositivi, se si trovano connessi a Teams con le credenziali dell'organizzazione, a volte definita azienda o istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d1150-142">Your users won’t be able to change the diagnostic data level for their devices if they are signed in to Teams with their organizational credentials, which is sometimes referred to as a work or school account.</span></span>

<span data-ttu-id="d1150-143">Tali dati diagnostici non includono i nomi degli utenti, il proprio indirizzo di posta elettronica o il contenuto dei file di Office.</span><span class="sxs-lookup"><span data-stu-id="d1150-143">This diagnostic data doesn’t include names of users, their email addresses, or the content of their Office files.</span></span> <span data-ttu-id="d1150-144">Il sistema crea un ID univoco che si associa ai dati di diagnostica degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1150-144">Our system creates a unique ID that it associates with your user’s diagnostic data.</span></span> <span data-ttu-id="d1150-145">Alla ricezione di dati di diagnostica che mostrano l’arresto anomalo di Teams per 100 volte, questo ID univoco consente di determinare se si tratta di un singolo utente che ha subito l’arresto anomalo dell’app per 100 ore o se si tratta di 100 utenti diversi che hanno subito l’arresto anomalo dell’app una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d1150-145">When we receive diagnostic data showing that the Teams app crashed 100 times, this unique ID lets us determine if it was a single user who crashed 100 times or if it was 100 different users who each crashed once.</span></span> <span data-ttu-id="d1150-146">Microsoft non usa l'ID univoco per identificare un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="d1150-146">We don’t use this unique ID to identify a specific user.</span></span>

<span data-ttu-id="d1150-147">Per visualizzare i dati di diagnostica inviati a Microsoft, è possibile usare il visualizzatore dati di diagnostica che può essere scaricato e installato da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d1150-147">To see what diagnostic data is being sent to Microsoft, you can use the Diagnostic Data Viewer, which you can download and install for free from the Microsoft Store.</span></span> <span data-ttu-id="d1150-148">Per altre informazioni, vedere [Uso di Visualizzatore dati di diagnostica con Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).</span><span class="sxs-lookup"><span data-stu-id="d1150-148">For more information, see [Using the Diagnostic Data Viewer with Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).</span></span>

> [!NOTE]
> <span data-ttu-id="d1150-149">Il supporto per il Visualizzatore dati di diagnostica è disponibile per Teams nei dispositivi che eseguono Android.</span><span class="sxs-lookup"><span data-stu-id="d1150-149">Support for the Diagnostic Data Viewer is available for Teams on devices running Android.</span></span> <span data-ttu-id="d1150-150">Il supporto per Teams nei dispositivi che eseguono Windows, macOS o iOS è in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d1150-150">Support for Teams on devices running Windows, macOS, or iOS is being worked on.</span></span>

## <a name="required-service-data-for-connected-experiences"></a><span data-ttu-id="d1150-151">Dati di servizio obbligatori per le esperienze connesse</span><span class="sxs-lookup"><span data-stu-id="d1150-151">Required service data for connected experiences</span></span>

<span data-ttu-id="d1150-152">I dati di servizio obbligatori sono dati che consentono di fornire queste esperienze connesse basate sul cloud garantendo che siano sicure e correttamente funzionanti.</span><span class="sxs-lookup"><span data-stu-id="d1150-152">Required service data is data that enables us to deliver these cloud-based connected experiences and help make these experiences secure and perform as expected.</span></span> <span data-ttu-id="d1150-153">È possibile scegliere di non offrire questa funzionalità agli utenti. In questo caso, le informazioni non saranno fornite a Microsoft per supportare la funzionalità delle esperienze connesse.</span><span class="sxs-lookup"><span data-stu-id="d1150-153">You can choose to not offer this functionality to your users, in which case this information will not be provided to Microsoft to support the functionality of connected experiences.</span></span> <span data-ttu-id="d1150-154">Sono disponibili altre informazioni sui [dati di servizio necessari](/deployoffice/privacy/required-service-data).</span><span class="sxs-lookup"><span data-stu-id="d1150-154">You can learn more about [required service data](/deployoffice/privacy/required-service-data).</span></span>

## <a name="essential-services-for-microsoft-teams"></a><span data-ttu-id="d1150-155">Servizi essenziali per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1150-155">Essential services for Microsoft Teams</span></span>

<span data-ttu-id="d1150-156">Esiste anche una serie di servizi che sono essenziali per il funzionamento di Microsoft 365 Apps for enterprise e non possono essere disabilitati.</span><span class="sxs-lookup"><span data-stu-id="d1150-156">There is also a set of services that are essential to how Microsoft 365 Apps for enterprise functions and cannot be disabled.</span></span> <span data-ttu-id="d1150-157">Ad esempio, il servizio gestione licenze che conferma che si dispone di una licenza per Microsoft 365 Apps for enterprise.</span><span class="sxs-lookup"><span data-stu-id="d1150-157">For example, the licensing service that confirms that you are properly licensed to use Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="d1150-158">I dati di servizio obbligatori su questi servizi vengono raccolti e inviati a Microsoft indipendentemente dalle altre impostazioni dei criteri configurate.</span><span class="sxs-lookup"><span data-stu-id="d1150-158">Required service data about these services is collected and sent to Microsoft, regardless of any other policy settings that you have configured.</span></span>

<span data-ttu-id="d1150-159">Per altre informazioni, vedere [Servizi essenziali per Office](/deployoffice/privacy/essential-services).</span><span class="sxs-lookup"><span data-stu-id="d1150-159">For more information, see [Essential services for Office](/deployoffice/privacy/essential-services).</span></span>