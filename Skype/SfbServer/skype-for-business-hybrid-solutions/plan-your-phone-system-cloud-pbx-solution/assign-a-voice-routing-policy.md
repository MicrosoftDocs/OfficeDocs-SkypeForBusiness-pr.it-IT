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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Riepilogo: leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che usano il sistema telefonico in Office 365 con connettività PSTN locale.'
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194548"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="72f03-103">Assegnare un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="72f03-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="72f03-104">**Riepilogo:** Leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che usano il sistema telefonico in Office 365 con connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="72f03-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="72f03-105">Quando un utente si trova in Skype for business online e usa il sistema telefonico in Office 365 con connettività PSTN locale, verranno applicati due criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="72f03-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="72f03-106">Uno è un criterio di routing vocale locale che verrà assegnato in locale.</span><span class="sxs-lookup"><span data-stu-id="72f03-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="72f03-107">Questo criterio può essere globale o specifico per gli utenti e definisce i record di utilizzo PSTN associati all'utente.</span><span class="sxs-lookup"><span data-stu-id="72f03-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="72f03-108">Questo argomento spiega come assegnare questo criterio.</span><span class="sxs-lookup"><span data-stu-id="72f03-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="72f03-109">Gli altri criteri vocali definiscono le funzionalità di chiamata disponibili per l'utente. Questo criterio vocale è definito da Microsoft ed è identico per tutti i sistemi telefonici in Office 365 con gli utenti di connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="72f03-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="72f03-110">Viene assegnato automaticamente al sistema telefonico negli utenti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="72f03-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="72f03-111">**Utente locale**</span><span class="sxs-lookup"><span data-stu-id="72f03-111">**On-premises user**</span></span>|<span data-ttu-id="72f03-112">**Sistema telefonico in Office 365 con l'utente di connettività PSTN locale**</span><span class="sxs-lookup"><span data-stu-id="72f03-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="72f03-113">Funzionalità di chiamata definite in</span><span class="sxs-lookup"><span data-stu-id="72f03-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="72f03-114">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="72f03-114">Voice policy</span></span>  <br/> |<span data-ttu-id="72f03-115">Criteri vocali predefiniti, assegnati automaticamente quando l'utente ha una licenza per il sistema telefonico in Office 365.</span><span class="sxs-lookup"><span data-stu-id="72f03-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="72f03-116">Record di utilizzo PSTN associati a</span><span class="sxs-lookup"><span data-stu-id="72f03-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="72f03-117">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="72f03-117">Voice policy</span></span>  <br/> |<span data-ttu-id="72f03-118">Criteri di routing vocale, assegnati mentre l'utente viene ancora ospitato in locale.</span><span class="sxs-lookup"><span data-stu-id="72f03-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="72f03-119">Eseguire la procedura seguente usando la distribuzione locale, mentre l'utente è ancora ospitato nella distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="72f03-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="72f03-120">Uso di un criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="72f03-120">Using a global voice routing policy</span></span>

<span data-ttu-id="72f03-121">Prima di usare un criterio di routing vocale globale per il sistema telefonico in Office 365 con gli utenti di connettività PSTN locale, è necessario aggiungere i record di utilizzo PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="72f03-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="72f03-122">Per assegnare i record di utilizzo PSTN ai criteri di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="72f03-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="72f03-123">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="72f03-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="72f03-124">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72f03-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="72f03-125">Aggiungere i record di utilizzo PSTN ai criteri:</span><span class="sxs-lookup"><span data-stu-id="72f03-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="72f03-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72f03-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="72f03-127">Creazione di un nuovo criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="72f03-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="72f03-128">Per creare un nuovo criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="72f03-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="72f03-129">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="72f03-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="72f03-130">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72f03-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="72f03-131">Creare un nuovo criterio di routing vocale:</span><span class="sxs-lookup"><span data-stu-id="72f03-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="72f03-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72f03-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="72f03-133">Questo esempio crea un nuovo criterio di routing vocale denominato HybridVoice, a cui sono associati due utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="72f03-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="72f03-134">Assegnazione di un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="72f03-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="72f03-135">Indipendentemente dal fatto che si usi il criterio di routing vocale globale o un utente specifico, usare la procedura seguente per assegnare i criteri a un utente.</span><span class="sxs-lookup"><span data-stu-id="72f03-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="72f03-136">Per assegnare i criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="72f03-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="72f03-137">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="72f03-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="72f03-138">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72f03-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="72f03-139">Assegnare un criterio vocale esistente a un utente:</span><span class="sxs-lookup"><span data-stu-id="72f03-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="72f03-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72f03-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="72f03-141">In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato al criterio vocale creato in precedenza con il nome HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="72f03-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="72f03-142">Per altre informazioni sui criteri di routing vocale, vedere [creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="72f03-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

