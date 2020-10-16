---
title: Etichette di sensitività per Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
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
description: Informazioni su come definire e usare le etichette di sensitività in Microsoft teams.
ms.openlocfilehash: 21d70bf48448ccef5555078e4aba65bb10d5d6a2
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476721"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="f120f-103">Etichette di sensitività per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f120f-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="f120f-104">Le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di teams di regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione in teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="f120f-105">È possibile definire le etichette di sensitività e i criteri associati nel [centro conformità & sicurezza](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="f120f-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="f120f-106">Queste etichette e criteri vengono applicati automaticamente ai team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f120f-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="f120f-107">Qual è la differenza tra etichette di sensitività e etichette di classificazione di Teams?</span><span class="sxs-lookup"><span data-stu-id="f120f-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="f120f-108">Le etichette di sensitività sono diverse dalle etichette di classificazione che richiedono di crearle usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f120f-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="f120f-109">Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo, ma non sono associate a criteri effettivi.</span><span class="sxs-lookup"><span data-stu-id="f120f-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="f120f-110">Le etichette di classificazione vengono usate come metadati per applicare manualmente i criteri tramite gli script e gli strumenti interni.</span><span class="sxs-lookup"><span data-stu-id="f120f-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="f120f-111">D'altra parte, le etichette di sensitività e i relativi criteri vengono applicati automaticamente da un lato all'altro tramite una combinazione della piattaforma groups, della Security & Compliance Center e dei servizi teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="f120f-112">Le etichette di sensitività includono un potente supporto per l'infrastruttura per proteggere i dati sensibili dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f120f-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="f120f-113">Per eseguire la migrazione dei gruppi esistenti dall'uso delle etichette di classificazione all'uso di etichette di sensitività, usare le istruzioni in [Azure Active Directory classificazione e etichette di sensitività per i gruppi di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="f120f-113">To migrate your existing Groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="f120f-114">Creare, gestire e pubblicare etichette di sensitività per i team</span><span class="sxs-lookup"><span data-stu-id="f120f-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="f120f-115">Per informazioni su come abilitare, creare e pubblicare etichette di sensitività per i team, vedere [classificazione di Azure Active Directory e etichette di sensitività per i gruppi di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="f120f-115">For how to enable, create, and publish sensitivity labels for Teams, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="f120f-116">La creazione, l'aggiornamento e l'eliminazione di etichette di sensibilità richiedono un'accurata sequenziazione con le etichette di pubblicazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f120f-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="f120f-117">Qualsiasi deviazione nella sequenza può causare errori permanenti per la creazione di team per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f120f-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="f120f-118">Pertanto, è fondamentale eseguire le operazioni seguenti quando si <a href="#createpublishlabels">creano e si pubblicano etichette</a>, si <a href="#modifydeletelabels">modificano ed eliminano le etichette pubblicate</a>e si <a href="#manageerrors">gestiscono gli errori di creazione del team</a>.</span><span class="sxs-lookup"><span data-stu-id="f120f-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="f120f-119">**Creare e pubblicare etichette** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="f120f-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="f120f-120">Quando un'etichetta viene creata e pubblicata nel centro conformità & sicurezza, può richiedere fino a 10 minuti affinché l'etichetta diventi visibile nell'interfaccia di creazione di teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-120">When a label is created and published in the Security & Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="f120f-121">Eseguire la procedura seguente per pubblicare l'etichetta per tutti gli utenti del tenant:</span><span class="sxs-lookup"><span data-stu-id="f120f-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="f120f-122">Creare l'etichetta e pubblicarla per alcuni account utente selezionati nel tenant.</span><span class="sxs-lookup"><span data-stu-id="f120f-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="f120f-123">Quando l'etichetta viene pubblicata, attendere 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="f120f-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="f120f-124">Dopo 10 minuti, provare a creare un team con l'etichetta usando uno degli account utente che hanno accesso all'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f120f-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="f120f-125">Se il team ha creato correttamente il passaggio 3, procedere e pubblicare l'etichetta per gli utenti rimanenti nel tenant.</span><span class="sxs-lookup"><span data-stu-id="f120f-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="f120f-126">**Modificare ed eliminare le etichette pubblicate** <a name="modifydeletelabels"> </a></span><span class="sxs-lookup"><span data-stu-id="f120f-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="f120f-127">L'eliminazione o la modifica dell'etichetta mentre è associata ai criteri di sensitività può causare errori di creazione del team in tutto il tenant.</span><span class="sxs-lookup"><span data-stu-id="f120f-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="f120f-128">Di conseguenza, prima di eliminare o modificare un'etichetta, devi prima dissociarla dai criteri associati.</span><span class="sxs-lookup"><span data-stu-id="f120f-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="f120f-129">Eseguire la procedura seguente</span><span class="sxs-lookup"><span data-stu-id="f120f-129">Use the following steps</span></span>  
<span data-ttu-id="f120f-130">per eliminare o modificare un'etichetta:</span><span class="sxs-lookup"><span data-stu-id="f120f-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="f120f-131">Rimuovere l'etichetta da tutti i criteri che usano l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f120f-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="f120f-132">In alternativa, puoi anche eliminare i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="f120f-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="f120f-133">Quando l'etichetta viene rimossa dai criteri o i criteri vengono eliminati, attendere 10 minuti prima di procedere ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="f120f-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="f120f-134">Dopo 10 minuti, avviare l'interfaccia di creazione del team e verificare che l'etichetta non sia più visibile per gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="f120f-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="f120f-135">A questo punto è possibile eliminare o modificare in modo sicuro l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f120f-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="f120f-136">**Gestire gli errori** <a name="manageerrors"> </a> di creazione del team</span><span class="sxs-lookup"><span data-stu-id="f120f-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="f120f-137">Se la creazione del team inizia a non riuscire in qualsiasi momento durante l'anteprima pubblica, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="f120f-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="f120f-138">Assicurarsi che le etichette di sensitività non siano obbligatorie per gli utenti durante la creazione del team.</span><span class="sxs-lookup"><span data-stu-id="f120f-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="f120f-139">Disattivare le etichette di sensitività usando gli script in [Enable this Preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span><span class="sxs-lookup"><span data-stu-id="f120f-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="f120f-140">Tieni presente che l'impostazione EnableMIPLabels deve essere impostata su false come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f120f-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="f120f-141">Uso di etichette di sensitività con teams</span><span class="sxs-lookup"><span data-stu-id="f120f-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="f120f-142">Ecco alcuni esempi di scenari in cui è possibile usare le etichette di sensitività con i team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f120f-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="f120f-143">Impostazione della privacy di Teams</span><span class="sxs-lookup"><span data-stu-id="f120f-143">Privacy setting of teams</span></span>

<span data-ttu-id="f120f-144">È possibile creare un'etichetta di sensitivity che, se applicata durante la creazione del team, consente agli utenti di creare team con un'impostazione di privacy (pubblica o privata) specifica.</span><span class="sxs-lookup"><span data-stu-id="f120f-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="f120f-145">Ad esempio, è possibile creare un'etichetta denominata "Confidential" nel centro conformità & sicurezza e configurare teams in modo che qualsiasi team creato con questa etichetta debba essere un team privato.</span><span class="sxs-lookup"><span data-stu-id="f120f-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="f120f-146">Quando un utente crea un nuovo team e seleziona l'etichetta **riservata** , l'unica opzione per la privacy disponibile per l'utente è **privata**.</span><span class="sxs-lookup"><span data-stu-id="f120f-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="f120f-147">Altre opzioni di privacy, ad esempio pubblica e a livello di organizzazione, sono disabilitate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f120f-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Screenshot dell'etichetta di sensitivity Confidential](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="f120f-149">Allo stesso modo, se l'utente seleziona **generale** quando crea un nuovo team, può creare solo team pubblici o a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f120f-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Schermata dell'etichetta di sensitività generale](media/sensitivity-labels-general-example.png)

<span data-ttu-id="f120f-151">Quando il team viene creato, l'etichetta di sensitività è visibile nell'angolo in alto a destra dei canali del team.</span><span class="sxs-lookup"><span data-stu-id="f120f-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-channel.png)

<span data-ttu-id="f120f-153">Un proprietario del team può modificare l'etichetta di sensitività e l'impostazione di privacy del team in qualsiasi momento accedendo al team e quindi facendo clic su **modifica team**.</span><span class="sxs-lookup"><span data-stu-id="f120f-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="f120f-155">Accesso Guest ai team</span><span class="sxs-lookup"><span data-stu-id="f120f-155">Guest access to teams</span></span>

<span data-ttu-id="f120f-156">Puoi specificare se un team creato con una specifica etichetta consente l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="f120f-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="f120f-157">I team creati con un'etichetta che non consente l'accesso Guest sono disponibili solo per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f120f-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="f120f-158">Gli utenti esterni all'organizzazione non possono essere aggiunti al team.</span><span class="sxs-lookup"><span data-stu-id="f120f-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f120f-159">Etichette di sensitività nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f120f-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="f120f-160">Quando si crea o si modifica un team nell'interfaccia di amministrazione di Microsoft teams, è possibile impostare le etichette di sensitività.</span><span class="sxs-lookup"><span data-stu-id="f120f-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f120f-161">Le etichette di sensitività sono visibili anche nelle proprietà del team e nella colonna **classificazione** nella pagina Gestisci Teams dell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f120f-162">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="f120f-162">Known issues</span></span>

<span data-ttu-id="f120f-163">**Supporto per le etichette di sensitività nelle API del grafico teams, cmdlet e modelli di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f120f-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="f120f-164">Attualmente gli utenti non potranno applicare etichette di sensitività ai team creati direttamente tramite API grafico, cmdlet di PowerShell e modelli.</span><span class="sxs-lookup"><span data-stu-id="f120f-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="f120f-165">**Supporto per le etichette di sensitività nelle SKU di Team EDU**</span><span class="sxs-lookup"><span data-stu-id="f120f-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="f120f-166">Le etichette di sensitività non sono attualmente supportate per i clienti che usano SKU per l'istruzione teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="f120f-167">**Modifica di etichette di sensitività direttamente in una raccolta siti di SharePoint per canali privati**</span><span class="sxs-lookup"><span data-stu-id="f120f-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="f120f-168">I canali privati creati in un team ereditano l'etichetta di sensitività applicata a un team.</span><span class="sxs-lookup"><span data-stu-id="f120f-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="f120f-169">Inoltre, la stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.</span><span class="sxs-lookup"><span data-stu-id="f120f-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="f120f-170">Se un utente aggiorna direttamente l'etichetta di sensitivity in una raccolta siti di SharePoint per un canale privato, tale etichetta non viene aggiornata nel client teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="f120f-171">In questo scenario, gli utenti continueranno a vedere l'etichetta di sensitività applicata a un team nell'intestazione del canale privato.</span><span class="sxs-lookup"><span data-stu-id="f120f-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="f120f-172">**Tempi di propagazione per le modifiche applicate alle etichette di sensitività all'esterno dell'app Teams**</span><span class="sxs-lookup"><span data-stu-id="f120f-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="f120f-173">Le modifiche apportate alle etichette di sensitività all'esterno dell'app teams possono richiedere fino a 24 ore per riflettere nell'app teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="f120f-174">Questo vale per tutte le modifiche apportate per abilitare o disabilitare le etichette per un tenant, le modifiche apportate ai nomi delle etichette, alle impostazioni e ai criteri.</span><span class="sxs-lookup"><span data-stu-id="f120f-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="f120f-175">Inoltre, le modifiche apportate a un'etichetta direttamente a un gruppo o a una raccolta siti di SharePoint che il team può richiedere fino a 24 ore per propagarsi all'app teams.</span><span class="sxs-lookup"><span data-stu-id="f120f-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
