---
title: Anteprima pubblica in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sull'anteprima pubblica in Microsoft Teams. Provare le nuove funzionalità e fornire commenti e suggerimenti.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530983"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="4541d-104">Anteprima pubblica in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4541d-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="4541d-p102">Le funzionalità incluse nell'anteprima potrebbero non essere complete e potrebbero subire modifiche prima di essere disponibili nella versione pubblica. Sono disponibili solo a scopo di valutazione ed esplorazione.</span><span class="sxs-lookup"><span data-stu-id="4541d-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="4541d-p103">L'anteprima pubblica per Microsoft Teams offre accesso anticipato alle funzionalità non rilasciate in Teams. Le anteprime consentono di esplorare e testare le funzionalità imminenti. Microsoft è lieta di ricevere feedback sulle funzionalità presentata nelle anteprime pubbliche. L'anteprima pubblica è abilitata per ogni utente di Teams, pertanto non è necessario preoccuparsi per l'impatto sull'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4541d-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="4541d-111">Impostare i criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="4541d-111">Set the Update policy</span></span>

 <span data-ttu-id="4541d-112">L'anteprima pubblica è abilitata per ogni utente e l'opzione per attivarla è controllata da un criterio amministrativo.</span><span class="sxs-lookup"><span data-stu-id="4541d-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="4541d-113">I criteri di aggiornamento vengono usati per gestire gli utenti delle anteprime di Teams e Office che visualizzano le funzionalità non definitive o di anteprima nell'app di Teams.</span><span class="sxs-lookup"><span data-stu-id="4541d-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="4541d-114">È possibile usare il criterio globale (impostazione predefinita a livello dell'organizzazione) e personalizzarlo oppure creare uno o più criteri personalizzati per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4541d-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="4541d-115">Occorre assegnare il criterio a utenti specifici poiché tale criterio non sovrascrive il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="4541d-115">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="4541d-116">Accedere all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4541d-116">Sign in to the admin center.</span></span>
2. <span data-ttu-id="4541d-117">Selezionare **Teams**>**Criteri di aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="4541d-117">Select **Teams**>**Update policies**.</span></span>

   ![Selezionare l'opzione Aggiorna criteri](media/updatePolicies.png)

3. <span data-ttu-id="4541d-119">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4541d-119">Select **Add**.</span></span>
4. <span data-ttu-id="4541d-120">Assegnare un nome ai criteri di aggiornamento, aggiungere una descrizione e attivare **Mostra le funzionalità di anteprima**.</span><span class="sxs-lookup"><span data-stu-id="4541d-120">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="4541d-121">È anche possibile impostare il criterio tramite PowerShell usando il cmdlet `CsTeamsUpdateManagementPolicy`.</span><span class="sxs-lookup"><span data-stu-id="4541d-121">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="4541d-122">Abilitare l'anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="4541d-122">Enable public preview</span></span>

<span data-ttu-id="4541d-123">Per abilitare l'anteprima pubblica su un client desktop o Web, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4541d-123">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="4541d-124">Selezionare il profilo per visualizzare il menu di Teams.</span><span class="sxs-lookup"><span data-stu-id="4541d-124">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="4541d-125">Selezionare **Informazioni** → **Anteprima pubblica**.</span><span class="sxs-lookup"><span data-stu-id="4541d-125">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="4541d-126">Selezionare **Passa all'anteprima pubblica**.</span><span class="sxs-lookup"><span data-stu-id="4541d-126">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4541d-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4541d-127">Related topics</span></span>

[<span data-ttu-id="4541d-128">Anteprima pubblica per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="4541d-128">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
