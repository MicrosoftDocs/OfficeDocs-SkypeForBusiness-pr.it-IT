---
title: Etichette di sensitività per Microsoft Teams
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
description: Informazioni su come usare le etichette di sensitività per proteggere i team in Microsoft teams.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937528"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="55dd6-103">Etichette di sensitività per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55dd6-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="55dd6-104">Le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di teams di proteggere e regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione all'interno di teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="55dd6-105">Dopo aver configurato le etichette di sensitività con i criteri associati nel [centro conformità Microsoft](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), queste etichette possono essere applicate ai team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55dd6-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="55dd6-106">Le etichette di sensitività non sono attualmente supportate per i clienti che usano SKU per l'istruzione teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="55dd6-107">Per ulteriori informazioni sulle licenze, vedere [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="55dd6-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="55dd6-108">Qual è la differenza tra etichette di sensitività e etichette di classificazione di Teams?</span><span class="sxs-lookup"><span data-stu-id="55dd6-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="55dd6-109">Le etichette di sensitività sono diverse dalle etichette di classificazione, note anche come classificazione dei gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55dd6-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="55dd6-110">Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo di Microsoft 365, ma non sono associate a criteri effettivi.</span><span class="sxs-lookup"><span data-stu-id="55dd6-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="55dd6-111">Si usano le etichette di classificazione come metadati e quindi si devono usare altri metodi, ad esempio strumenti interni e script, per applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="55dd6-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="55dd6-112">Il vantaggio derivante dall'uso di etichette di sensitività è che i loro criteri vengono applicati automaticamente tramite una combinazione della piattaforma Microsoft 365 groups, del centro conformità e dei servizi teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="55dd6-113">Le etichette di sensitività includono un potente supporto per l'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità con i criteri interni o le normative.</span><span class="sxs-lookup"><span data-stu-id="55dd6-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="55dd6-114">Se attualmente si usano le etichette di classificazione, vedere la documentazione seguente per altre informazioni e istruzioni su come eseguire la migrazione a etichette di sensitività: [classificazione dei gruppi di Azure ad classica](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span><span class="sxs-lookup"><span data-stu-id="55dd6-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="55dd6-115">Scenari di esempio per le etichette di sensitività</span><span class="sxs-lookup"><span data-stu-id="55dd6-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="55dd6-116">Scenari di esempio su come usare le etichette di sensitività con i team dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="55dd6-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="55dd6-117">Impostare il livello di privacy (pubblico o privato) per i team</span><span class="sxs-lookup"><span data-stu-id="55dd6-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="55dd6-118">Controllare l'accesso Guest ai team</span><span class="sxs-lookup"><span data-stu-id="55dd6-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="55dd6-119">Impostare il livello di privacy per Teams</span><span class="sxs-lookup"><span data-stu-id="55dd6-119">Set the privacy level for teams</span></span>

<span data-ttu-id="55dd6-120">È possibile creare e configurare un'etichetta di sensitivity che, se applicata durante la creazione del team, consente agli utenti di creare team con un'impostazione privacy specifica (pubblica o privata).</span><span class="sxs-lookup"><span data-stu-id="55dd6-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="55dd6-121">Ad esempio, è possibile creare e pubblicare un'etichetta di sensitività denominata "Confidential" con l'opzione per la privacy dell'etichetta configurata come **privata**.</span><span class="sxs-lookup"><span data-stu-id="55dd6-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="55dd6-122">Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato.</span><span class="sxs-lookup"><span data-stu-id="55dd6-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="55dd6-123">Quando un utente crea un nuovo team e seleziona l'etichetta **riservata** , l'unica opzione per la privacy disponibile per l'utente è **privata**.</span><span class="sxs-lookup"><span data-stu-id="55dd6-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="55dd6-124">Altre opzioni di privacy, ad esempio pubblica e a livello di organizzazione, non sono disponibili per l'utente per selezionare:</span><span class="sxs-lookup"><span data-stu-id="55dd6-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Screenshot dell'etichetta di sensitivity Confidential](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="55dd6-126">Analogamente, è possibile creare e pubblicare un'etichetta di sensitività denominata "generale" con l'opzione per la privacy dell'etichetta configurata come **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="55dd6-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="55dd6-127">Quando un utente crea un nuovo team, può creare solo team pubblici o a livello di organizzazione quando seleziona questa etichetta:</span><span class="sxs-lookup"><span data-stu-id="55dd6-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Schermata dell'etichetta di sensitività generale](media/sensitivity-labels-general-example.png)

<span data-ttu-id="55dd6-129">Quando viene creato un team, l'etichetta di sensitività è visibile nell'angolo in alto a destra dei canali del team.</span><span class="sxs-lookup"><span data-stu-id="55dd6-129">When a team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-channel.png)

<span data-ttu-id="55dd6-131">Un proprietario del team può modificare l'etichetta di sensitività e l'impostazione di privacy del team in qualsiasi momento accedendo al team e quindi fare clic su **modifica team**.</span><span class="sxs-lookup"><span data-stu-id="55dd6-131">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Screenshot dell'etichetta di sensitivity nelle proprietà del team](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="55dd6-133">Controllare l'accesso Guest ai team</span><span class="sxs-lookup"><span data-stu-id="55dd6-133">Control guest access to teams</span></span>

<span data-ttu-id="55dd6-134">Puoi usare le etichette di sensitività per controllare l'accesso Guest ai team.</span><span class="sxs-lookup"><span data-stu-id="55dd6-134">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="55dd6-135">I team creati con un'etichetta che non consente l'accesso Guest sono disponibili solo per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55dd6-135">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="55dd6-136">Gli utenti esterni all'organizzazione non possono essere aggiunti al team.</span><span class="sxs-lookup"><span data-stu-id="55dd6-136">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="55dd6-137">Interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55dd6-137">Microsoft Teams admin center</span></span>

<span data-ttu-id="55dd6-138">È possibile applicare etichette di sensitività quando si crea o si modifica un team nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-138">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="55dd6-139">Le etichette di sensitività sono visibili anche nelle proprietà del team e nella colonna **classificazione** nella pagina **Gestisci teams** dell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-139">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="55dd6-140">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="55dd6-140">Limitations</span></span>

<span data-ttu-id="55dd6-141">Prima di usare le etichette di sensitività per i team, tenere presenti le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55dd6-141">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="55dd6-142">**I nomi di etichetta padre non vengono visualizzati per le sottoetichette**</span><span class="sxs-lookup"><span data-stu-id="55dd6-142">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="55dd6-143">Teams supporta le sottoetichette ma non Visualizza il nome dell'etichetta padre.</span><span class="sxs-lookup"><span data-stu-id="55dd6-143">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="55dd6-144">Ad esempio, **Confidential** \\ **tutti i dipendenti** vengono visualizzati come **tutti i dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="55dd6-144">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="55dd6-145">**Le etichette di sensitività non sono supportate da API del grafico team, cmdlet di PowerShell e modelli**</span><span class="sxs-lookup"><span data-stu-id="55dd6-145">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="55dd6-146">Gli utenti non potranno applicare etichette di sensitività ai team creati direttamente tramite le API del grafico teams, i cmdlet di PowerShell teams e i modelli teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-146">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="55dd6-147">**Supporto per i canali privati**</span><span class="sxs-lookup"><span data-stu-id="55dd6-147">**Support for private channels**</span></span>
    
    <span data-ttu-id="55dd6-148">I canali privati creati in un team ereditano l'etichetta di sensitività applicata a un team.</span><span class="sxs-lookup"><span data-stu-id="55dd6-148">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="55dd6-149">La stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.</span><span class="sxs-lookup"><span data-stu-id="55dd6-149">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="55dd6-150">Tuttavia, se un utente modifica direttamente l'etichetta di sensitivity in un sito di SharePoint per un canale privato, la modifica dell'etichetta non viene applicata al client teams.</span><span class="sxs-lookup"><span data-stu-id="55dd6-150">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="55dd6-151">In questo scenario, gli utenti continuano a vedere l'etichetta di sensitività originale applicata al team nell'intestazione del canale privato.</span><span class="sxs-lookup"><span data-stu-id="55dd6-151">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="55dd6-152">Come creare e configurare le etichette di sensitività per i team</span><span class="sxs-lookup"><span data-stu-id="55dd6-152">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="55dd6-153">Usare le istruzioni della documentazione di Microsoft 365 per creare e configurare etichette di sensitività per i team:</span><span class="sxs-lookup"><span data-stu-id="55dd6-153">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="55dd6-154">[Usare le etichette di sensitività per proteggere il contenuto in Microsoft teams, microsoft 365 Groups e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="55dd6-154">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
