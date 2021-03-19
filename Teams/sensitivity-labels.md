---
title: Etichette di riservatezza per Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare le etichette di riservatezza per proteggere i team in Microsoft Teams.
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875106"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="dbeaf-103">Etichette di riservatezza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbeaf-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="dbeaf-104">[Le etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di Teams di proteggere e regolare l'accesso ai contenuti aziendali riservati creati durante la collaborazione all'interno dei team.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="dbeaf-105">Dopo aver configurato le etichette di riservatezza con i criteri associati nel Centro conformità [Microsoft,](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)queste etichette possono essere applicate ai team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="dbeaf-106">Le etichette di riservatezza non sono attualmente supportate per i clienti che usano SKU di Teams Education.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="dbeaf-107">Per altre informazioni sulle licenze, vedere Descrizione [del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="dbeaf-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="dbeaf-108">Qual è la differenza tra le etichette di riservatezza e le etichette di classificazione di Teams?</span><span class="sxs-lookup"><span data-stu-id="dbeaf-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="dbeaf-109">Le etichette di riservatezza sono diverse dalle etichette di classificazione, note anche come classificazione dei gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="dbeaf-110">Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo di Microsoft 365 ma a cui non sono associati criteri effettivi.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="dbeaf-111">Le etichette di classificazione vengono usate come metadati e quindi è necessario usare altri metodi, ad esempio gli strumenti interni e gli script, per applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="dbeaf-112">Il vantaggio dell'uso delle etichette di riservatezza è che i criteri vengono applicati automaticamente end-to-end tramite una combinazione della piattaforma Gruppi di Microsoft 365, del Centro conformità e dei servizi di Teams.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="dbeaf-113">Le etichette di riservatezza offrono un potente supporto dell'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità ai criteri o alle normative interne.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="dbeaf-114">Se attualmente si usano etichette di classificazione, vedere la documentazione seguente per altre informazioni e istruzioni su come eseguirne la migrazione alle etichette di riservatezza: Classificazione classica dei gruppi [di Azure AD.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="dbeaf-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="dbeaf-115">Scenari di esempio per le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="dbeaf-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="dbeaf-116">Scenari di esempio per l'uso delle etichette di riservatezza con Teams nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="dbeaf-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="dbeaf-117">Impostare il livello di privacy (pubblico o privato) per i team</span><span class="sxs-lookup"><span data-stu-id="dbeaf-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="dbeaf-118">Controllare l'accesso guest ai team</span><span class="sxs-lookup"><span data-stu-id="dbeaf-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="dbeaf-119">Impostare il livello di privacy per i team</span><span class="sxs-lookup"><span data-stu-id="dbeaf-119">Set the privacy level for teams</span></span>

<span data-ttu-id="dbeaf-120">È possibile creare e configurare un'etichetta di riservatezza che, se applicata durante la creazione del team, consente agli utenti di creare team con una specifica impostazione di privacy (pubblica o privata).</span><span class="sxs-lookup"><span data-stu-id="dbeaf-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="dbeaf-121">Ad esempio, è possibile creare e pubblicare un'etichetta di riservatezza denominata "Riservato" con l'opzione di privacy dell'etichetta configurata come **Privato.**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="dbeaf-122">Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="dbeaf-123">Quando un utente crea un nuovo  team e seleziona l'etichetta Riservato, l'unica opzione di privacy disponibile per l'utente è **Privato.**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="dbeaf-124">Altre opzioni di privacy, ad esempio Pubblico e A livello di organizzazione, non sono disponibili per l'utente:</span><span class="sxs-lookup"><span data-stu-id="dbeaf-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Screenshot dell'etichetta riservatezza](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="dbeaf-126">Analogamente, si crea e si pubblica un'etichetta di riservatezza denominata "Generale" con l'opzione di privacy dell'etichetta configurata come **Pubblico.**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="dbeaf-127">Quando un utente crea un nuovo team, può creare team pubblici o a livello di organizzazione solo quando seleziona questa etichetta:</span><span class="sxs-lookup"><span data-stu-id="dbeaf-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Screenshot dell'etichetta di riservatezza Generale](media/sensitivity-labels-general-example.png)

<span data-ttu-id="dbeaf-129">Quando il team viene creato, l'etichetta di riservatezza è visibile nell'angolo in alto a destra dei canali del team.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> <span data-ttu-id="dbeaf-130">Si noti che se si usano etichette figlio padre gerarchiche, ad esempio "Riservato\Finanze", nell'intestazione del canale verrà mostrata solo l'etichetta padre.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-130">Note that if you are using hierarchical parent child labels such as "Confidential\Finance" then only the parent label will be showin the channel header.</span></span>


![Screenshot dell'etichetta di riservatezza nel canale del team](media/sensitivity-labels-channel.png)

<span data-ttu-id="dbeaf-132">Il proprietario di un team può modificare l'etichetta di riservatezza e l'impostazione della privacy del team in qualsiasi momento andando al team e quindi facendo clic **su Modifica team.**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Screenshot dell'etichetta di riservatezza nelle proprietà del team](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="dbeaf-134">Controllare l'accesso guest ai team</span><span class="sxs-lookup"><span data-stu-id="dbeaf-134">Control guest access to teams</span></span>

<span data-ttu-id="dbeaf-135">È possibile usare le etichette di riservatezza per controllare l'accesso dei guest ai team.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="dbeaf-136">I team creati con un'etichetta che non consente l'accesso guest sono disponibili solo per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="dbeaf-137">Le persone esterne all'organizzazione non possono essere aggiunte al team.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="dbeaf-138">Interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbeaf-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="dbeaf-139">È possibile applicare etichette di riservatezza quando si crea o si modifica un team nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="dbeaf-140">Le etichette di riservatezza sono visibili anche nelle proprietà del team e nella colonna **Classificazione** nella **pagina Gestisci team** dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="dbeaf-141">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="dbeaf-141">Limitations</span></span>

<span data-ttu-id="dbeaf-142">Prima di usare le etichette di riservatezza per Teams, tenere presenti le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbeaf-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="dbeaf-143">**I nomi delle etichette padre non vengono visualizzati per le etichette secondarie**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="dbeaf-144">Teams supporta le etichette secondarie ma non visualizza il nome dell'etichetta padre.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="dbeaf-145">Ad esempio, **Tutti** \\ **i dipendenti riservati** viene visualizzato come Tutti i **dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="dbeaf-146">**Le etichette di riservatezza non sono supportate dalle API di Teams Graph, dai cmdlet di PowerShell e dai modelli**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="dbeaf-147">Gli utenti non saranno in grado di applicare etichette di riservatezza ai team creati direttamente tramite le API di Teams Graph, i cmdlet di PowerShell di Teams e i modelli di Teams.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-147">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="dbeaf-148">**Supporto per i canali privati**</span><span class="sxs-lookup"><span data-stu-id="dbeaf-148">**Support for private channels**</span></span>
    
    <span data-ttu-id="dbeaf-149">I canali privati creati in un team ereditano l'etichetta di riservatezza applicata a un team.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-149">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="dbeaf-150">La stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-150">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="dbeaf-151">Tuttavia, se un utente modifica direttamente l'etichetta di riservatezza in un sito di SharePoint per un canale privato, la modifica dell'etichetta non viene riflessa nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-151">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="dbeaf-152">In questo scenario, gli utenti continuano a vedere l'etichetta di riservatezza originale applicata al team nell'intestazione del canale privato.</span><span class="sxs-lookup"><span data-stu-id="dbeaf-152">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="dbeaf-153">Come creare e configurare etichette di riservatezza per Teams</span><span class="sxs-lookup"><span data-stu-id="dbeaf-153">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="dbeaf-154">Seguire le istruzioni della documentazione di Microsoft 365 per creare e configurare etichette di riservatezza per Teams:</span><span class="sxs-lookup"><span data-stu-id="dbeaf-154">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="dbeaf-155">[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, nei gruppi di Microsoft 365 e nei siti di SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="dbeaf-155">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
