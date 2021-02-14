---
title: Assegnare un criterio di routing vocale
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Riepilogo: leggere questo argomento per informazioni su come assegnare un criterio vocale agli utenti che utilizzano Sistema telefonico con connettività PSTN locale.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359322"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="d4066-103">Assegnare un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="d4066-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="d4066-104">Skype for Business online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="d4066-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="d4066-105">Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.</span><span class="sxs-lookup"><span data-stu-id="d4066-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="d4066-106">Informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="d4066-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d4066-107">**Riepilogo:** Leggere questo argomento per informazioni su come assegnare criteri vocali agli utenti che utilizzano Sistema telefonico con connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="d4066-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="d4066-108">Una volta che un utente si trova su Skype for Business online e usa Sistema telefonico con connettività PSTN locale, verranno applicati due criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="d4066-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="d4066-109">Uno è un criterio di routing vocale locale che verrà assegnato in locale.</span><span class="sxs-lookup"><span data-stu-id="d4066-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="d4066-110">Questo criterio può essere globale o specifico dell'utente e definisce i record di utilizzo PSTN associati all'utente.</span><span class="sxs-lookup"><span data-stu-id="d4066-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="d4066-111">In questo argomento viene illustrato come assegnare questo criterio.</span><span class="sxs-lookup"><span data-stu-id="d4066-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="d4066-112">Gli altri criteri vocali definiscono le funzionalità di chiamata disponibili per l'utente. Questo criterio vocale è definito da Microsoft ed è identico per tutti i sistemi telefonici con utenti di connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="d4066-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="d4066-113">Viene assegnato automaticamente agli utenti di Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="d4066-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="d4066-114">**Utente locale**</span><span class="sxs-lookup"><span data-stu-id="d4066-114">**On-premises user**</span></span>|<span data-ttu-id="d4066-115">**Sistema telefonico con utente di connettività PSTN locale**</span><span class="sxs-lookup"><span data-stu-id="d4066-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4066-116">Funzionalità di chiamata definite in</span><span class="sxs-lookup"><span data-stu-id="d4066-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="d4066-117">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="d4066-117">Voice policy</span></span>  <br/> |<span data-ttu-id="d4066-118">Criteri vocali predefiniti, assegnati automaticamente quando l'utente ha una licenza per Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="d4066-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="d4066-119">Record di utilizzo PSTN associati a</span><span class="sxs-lookup"><span data-stu-id="d4066-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="d4066-120">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="d4066-120">Voice policy</span></span>  <br/> |<span data-ttu-id="d4066-121">Criterio di routing vocale, assegnato mentre l'utente è ancora in locale.</span><span class="sxs-lookup"><span data-stu-id="d4066-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="d4066-122">La procedura seguente viene eseguita utilizzando la distribuzione locale, mentre l'utente è ancora presente nella distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="d4066-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="d4066-123">Utilizzo di un criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="d4066-123">Using a global voice routing policy</span></span>

<span data-ttu-id="d4066-124">Prima di utilizzare un criterio di routing vocale globale per sistema telefonico con utenti di connettività PSTN locale, è necessario aggiungere i record di utilizzo PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="d4066-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="d4066-125">Per assegnare record di utilizzo PSTN al criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="d4066-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="d4066-126">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d4066-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d4066-127">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="d4066-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d4066-128">Aggiungere i record di utilizzo PSTN ai criteri:</span><span class="sxs-lookup"><span data-stu-id="d4066-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="d4066-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4066-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="d4066-130">Creazione di un nuovo criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="d4066-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="d4066-131">Per creare un nuovo criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="d4066-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="d4066-132">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d4066-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d4066-133">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="d4066-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d4066-134">Creare un nuovo criterio di routing vocale:</span><span class="sxs-lookup"><span data-stu-id="d4066-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="d4066-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4066-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="d4066-136">In questo esempio viene creato un nuovo criterio di routing vocale denominato HybridVoice, a cui sono associati due utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="d4066-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="d4066-137">Assegnazione di un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="d4066-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="d4066-138">Indipendentemente dal fatto che si utilizzi il criterio di routing vocale globale o quelli specifici dell'utente, eseguire la procedura seguente per assegnare il criterio a un utente.</span><span class="sxs-lookup"><span data-stu-id="d4066-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="d4066-139">Per assegnare il criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="d4066-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="d4066-140">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d4066-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d4066-141">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="d4066-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d4066-142">Assegnare un criterio vocale esistente a un utente:</span><span class="sxs-lookup"><span data-stu-id="d4066-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="d4066-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4066-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="d4066-144">In questo esempio, l'utente con il nome visualizzato Bob Kelly viene assegnato al criterio vocale creato in precedenza con il nome HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="d4066-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="d4066-145">Per ulteriori informazioni sui criteri di routing vocale, vedere Creare o modificare un criterio vocale e configurare i record di utilizzo [PSTN in Skype for Business 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d4066-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

