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
description: 'Riepilogo: leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che utilizzano il sistema telefonico con connettività PSTN locale.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359322"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="4b8d1-103">Assegnare un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="4b8d1-104">Skype for business online si ritirerà il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="4b8d1-105">Inoltre, la connettività PSTN tra l'ambiente locale e Skype for Business Server o il Cloud Connector Edition e Skype for business online non sarà più supportato.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="4b8d1-106">Informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="4b8d1-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4b8d1-107">**Riepilogo:** Leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che utilizzano il sistema telefonico con connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="4b8d1-108">Una volta che un utente è su Skype for business online e utilizza un sistema telefonico con connettività PSTN locale, verranno applicati due criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="4b8d1-109">Uno è un criterio di routing vocale locale che verrà assegnato nei locali.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="4b8d1-110">Questo criterio può essere globale o specifico dell'utente e definisce quali record di utilizzo PSTN sono associati all'utente.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="4b8d1-111">In questo argomento viene illustrato come assegnare questo criterio.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="4b8d1-112">Gli altri criteri vocali definiscono quali funzionalità di chiamata sono disponibili per l'utente. Questo criterio vocale è definito da Microsoft ed è identico per tutti i sistemi di telefonia con gli utenti di connettività PSTN locali.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="4b8d1-113">Viene assegnato automaticamente agli utenti del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="4b8d1-114">**Utente locale**</span><span class="sxs-lookup"><span data-stu-id="4b8d1-114">**On-premises user**</span></span>|<span data-ttu-id="4b8d1-115">**Sistema telefonico con utente di connettività PSTN locale**</span><span class="sxs-lookup"><span data-stu-id="4b8d1-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b8d1-116">Funzionalità di chiamata definite in</span><span class="sxs-lookup"><span data-stu-id="4b8d1-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="4b8d1-117">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="4b8d1-117">Voice policy</span></span>  <br/> |<span data-ttu-id="4b8d1-118">Criteri vocali predefiniti, assegnati automaticamente quando l'utente viene concesso in licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="4b8d1-119">Record di utilizzo PSTN associati a</span><span class="sxs-lookup"><span data-stu-id="4b8d1-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="4b8d1-120">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="4b8d1-120">Voice policy</span></span>  <br/> |<span data-ttu-id="4b8d1-121">Criterio di routing vocale, assegnato mentre l'utente è ancora ospitato in locale.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="4b8d1-122">È necessario eseguire i passaggi seguenti utilizzando la distribuzione locale, mentre l'utente è ancora ospitato nella distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="4b8d1-123">Utilizzo di un criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-123">Using a global voice routing policy</span></span>

<span data-ttu-id="4b8d1-124">Prima di utilizzare un criterio di routing vocale globale per il sistema telefonico con gli utenti di connettività PSTN locali, è necessario aggiungere i record di utilizzo PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="4b8d1-125">Per assegnare i record di utilizzo PSTN al criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="4b8d1-126">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b8d1-127">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4b8d1-128">Aggiungere i record di utilizzo PSTN ai criteri:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="4b8d1-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="4b8d1-130">Creazione di un nuovo criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="4b8d1-131">Per creare un nuovo criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="4b8d1-132">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b8d1-133">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4b8d1-134">Creare un nuovo criterio di routing vocale:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="4b8d1-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="4b8d1-136">In questo esempio viene creato un nuovo criterio di routing vocale denominato HybridVoice, a cui sono associati due utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="4b8d1-137">Assegnazione di un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="4b8d1-138">Indipendentemente dal fatto che si utilizzi il criterio di routing vocale globale o quelli specifici dell'utente, utilizzare i passaggi seguenti per assegnare il criterio a un utente.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="4b8d1-139">Per assegnare il criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="4b8d1-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="4b8d1-140">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b8d1-141">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4b8d1-142">Assegnare un criterio vocale esistente a un utente:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="4b8d1-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="4b8d1-144">In questo esempio, l'utente con il nome visualizzato Bob Kelly viene assegnato al criterio vocale creato in precedenza con il nome HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="4b8d1-145">Per ulteriori informazioni sui criteri di routing vocale, vedere [creare o modificare criteri vocali e configurare i record di utilizzo PSTN in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4b8d1-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

