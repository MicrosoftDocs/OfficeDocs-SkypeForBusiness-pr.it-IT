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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come definire e usare le etichette di sensitività in Microsoft teams.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653587"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="52b51-103">Etichette di sensitività per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52b51-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="52b51-104">Le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di teams di regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione in teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="52b51-105">È possibile definire le etichette di sensitività e i criteri associati nel [centro conformità & sicurezza](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="52b51-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="52b51-106">Queste etichette e criteri vengono applicati automaticamente ai team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52b51-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="52b51-107">Qual è la differenza tra etichette di sensitività e etichette di classificazione di Teams?</span><span class="sxs-lookup"><span data-stu-id="52b51-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="52b51-108">Le etichette di sensitività sono diverse dalle etichette di classificazione che richiedono di crearle usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52b51-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="52b51-109">Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo, ma non sono associate a criteri effettivi.</span><span class="sxs-lookup"><span data-stu-id="52b51-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="52b51-110">Le etichette di classificazione vengono usate come metadati per applicare manualmente i criteri tramite gli script e gli strumenti interni.</span><span class="sxs-lookup"><span data-stu-id="52b51-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="52b51-111">D'altra parte, le etichette di sensitività e i relativi criteri vengono applicati automaticamente da un lato all'altro tramite una combinazione della piattaforma groups, della Security & Compliance Center e dei servizi teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="52b51-112">Le etichette di sensitività includono un potente supporto per l'infrastruttura per proteggere i dati sensibili dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52b51-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="52b51-113">Creare e pubblicare etichette di sensitività per Teams</span><span class="sxs-lookup"><span data-stu-id="52b51-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="52b51-114">Per informazioni su come abilitare, creare e pubblicare etichette di sensitività per i team, vedere [usare le etichette di sensitività con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="52b51-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="52b51-115">Uso di etichette di sensitività con teams</span><span class="sxs-lookup"><span data-stu-id="52b51-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="52b51-116">Ecco alcuni esempi di scenari in cui è possibile usare le etichette di sensitività con i team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52b51-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="52b51-117">Impostazione della privacy di Teams</span><span class="sxs-lookup"><span data-stu-id="52b51-117">Privacy setting of teams</span></span>

<span data-ttu-id="52b51-118">È possibile creare un'etichetta di sensitivity che, se applicata durante la creazione del team, consente agli utenti di creare team con un'impostazione di privacy (pubblica o privata) specifica.</span><span class="sxs-lookup"><span data-stu-id="52b51-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="52b51-119">Ad esempio, è possibile creare un'etichetta denominata "Confidential" nel centro conformità & sicurezza e configurare teams in modo che qualsiasi team creato con questa etichetta debba essere un team privato.</span><span class="sxs-lookup"><span data-stu-id="52b51-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="52b51-120">Quando un utente crea un nuovo team e seleziona l'etichetta **riservata** , l'unica opzione per la privacy disponibile per l'utente è **privata**.</span><span class="sxs-lookup"><span data-stu-id="52b51-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="52b51-121">Altre opzioni di privacy, ad esempio pubblica e a livello di organizzazione, sono disabilitate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="52b51-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Screenshot dell'etichetta di sensitivity Confidential](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="52b51-123">Allo stesso modo, se l'utente seleziona **generale** quando crea un nuovo team, può creare solo team pubblici o a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52b51-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Schermata dell'etichetta di sensitività generale](media/sensitivity-labels-general-example.png)

<span data-ttu-id="52b51-125">Quando il team viene creato, l'etichetta di sensitività è visibile nell'angolo in alto a destra dei canali del team.</span><span class="sxs-lookup"><span data-stu-id="52b51-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-channel.png)

<span data-ttu-id="52b51-127">Un proprietario del team può modificare l'etichetta di sensitività e l'impostazione di privacy del team in qualsiasi momento accedendo al team e quindi facendo clic su **modifica team**.</span><span class="sxs-lookup"><span data-stu-id="52b51-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="52b51-129">Accesso Guest ai team</span><span class="sxs-lookup"><span data-stu-id="52b51-129">Guest access to teams</span></span>

<span data-ttu-id="52b51-130">Puoi specificare se un team creato con una specifica etichetta consente l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="52b51-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="52b51-131">I team creati con un'etichetta che non consente l'accesso Guest sono disponibili solo per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52b51-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="52b51-132">Gli utenti esterni all'organizzazione non possono essere aggiunti al team.</span><span class="sxs-lookup"><span data-stu-id="52b51-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="52b51-133">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="52b51-133">Known issues</span></span>

<span data-ttu-id="52b51-134">**Supporto per le etichette di sensitività nell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="52b51-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="52b51-135">Attualmente, le etichette di sensitività non sono supportate nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="52b51-136">Se si usano le etichette di sensitività, non sarà possibile impostare le etichette di sensibilità quando si crea o si modifica un team.</span><span class="sxs-lookup"><span data-stu-id="52b51-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="52b51-137">Anche le etichette di sensitività non sono visibili nelle proprietà del team e non saranno visibili nella colonna **classificazione** nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="52b51-138">**Supporto per le etichette di sensitività nelle API del grafico teams, cmdlet e modelli di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="52b51-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="52b51-139">Attualmente gli utenti non potranno applicare etichette di sensitività ai team creati direttamente tramite API grafico, cmdlet di PowerShell e modelli.</span><span class="sxs-lookup"><span data-stu-id="52b51-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="52b51-140">**Modifica di etichette di sensitività direttamente in una raccolta siti di SharePoint per canali privati**</span><span class="sxs-lookup"><span data-stu-id="52b51-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="52b51-141">I canali privati creati in un team ereditano l'etichetta di sensitività applicata a un team.</span><span class="sxs-lookup"><span data-stu-id="52b51-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="52b51-142">Inoltre, la stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.</span><span class="sxs-lookup"><span data-stu-id="52b51-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="52b51-143">Se un utente aggiorna direttamente l'etichetta di sensitivity in una raccolta siti di SharePoint per un canale privato, tale etichetta non viene aggiornata nel client teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="52b51-144">In questo scenario, gli utenti continueranno a vedere l'etichetta di sensitività applicata a un team nell'intestazione del canale privato.</span><span class="sxs-lookup"><span data-stu-id="52b51-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="52b51-145">**Tempi di propagazione per le modifiche applicate alle etichette di sensitività all'esterno dell'app Teams**</span><span class="sxs-lookup"><span data-stu-id="52b51-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="52b51-146">Le modifiche apportate alle etichette di sensitività all'esterno dell'app teams possono richiedere fino a 24 ore per riflettere nell'app teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="52b51-147">Questo vale per tutte le modifiche apportate per abilitare o disabilitare le etichette per un tenant, le modifiche apportate ai nomi delle etichette, alle impostazioni e ai criteri.</span><span class="sxs-lookup"><span data-stu-id="52b51-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="52b51-148">Inoltre, le modifiche apportate a un'etichetta direttamente a un gruppo o a una raccolta siti di SharePoint che il team può richiedere fino a 24 ore per propagarsi all'app teams.</span><span class="sxs-lookup"><span data-stu-id="52b51-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>