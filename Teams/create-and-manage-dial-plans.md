---
title: Creare e impostare dial plan
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft Teams o Windows PowerShell per creare e gestire i dial plan (piani di chiamata PSTN).
ms.openlocfilehash: 0b2c8c64d1e4e01843c6565d43a07e0ebdb24d71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120808"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="09cff-103">Creare e impostare dial plan</span><span class="sxs-lookup"><span data-stu-id="09cff-103">Create and manage dial plans</span></span>

<span data-ttu-id="09cff-104">Dopo aver programmato i dial plan per l'organizzazione e aver trovato tutte le regole di normalizzazione che devono essere create per il routing delle chiamate, è possibile creare i dial plan.</span><span class="sxs-lookup"><span data-stu-id="09cff-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="09cff-105">È possibile usare l'interfaccia di amministrazione di Microsoft Teams o Windows PowerShell per creare e gestire i piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="09cff-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="09cff-106">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09cff-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="09cff-107">Creare un piano di chiamata</span><span class="sxs-lookup"><span data-stu-id="09cff-107">Create a dial plan</span></span>

1. <span data-ttu-id="09cff-108">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Piano di**  >  **chiamata vocale.**</span><span class="sxs-lookup"><span data-stu-id="09cff-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="09cff-109">Fare **clic su** Aggiungi e quindi immettere un nome e una descrizione per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="09cff-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="09cff-110">![Screenshot che mostra la pagina Aggiungi per la creazione di un dial plan](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="09cff-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="09cff-111">In **Dettagli piano di** chiamata specificare un prefisso di composizione esterno se gli utenti devono comporre una o più cifre iniziali aggiuntive , ad esempio 9, per ottenere una linea esterna.</span><span class="sxs-lookup"><span data-stu-id="09cff-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="09cff-112">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="09cff-112">To do this:</span></span>
    1. <span data-ttu-id="09cff-113">Nella casella **Prefisso di composizione esterno** immettere un prefisso di composizione esterno.</span><span class="sxs-lookup"><span data-stu-id="09cff-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="09cff-114">Il prefisso può contenere fino a quattro caratteri (#,\*, e 0-9).</span><span class="sxs-lookup"><span data-stu-id="09cff-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="09cff-115">Attivare la **composizione ottimizzata del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="09cff-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="09cff-116">Se si specifica un prefisso di composizione esterno, è necessario attivare questa impostazione anche per applicare il prefisso in modo che le chiamate possano essere effettuate all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="09cff-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="09cff-117">In **Regole di normalizzazione** configurare e associare una o più regole [di normalizzazione](what-are-dial-plans.md#normalization-rules) per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="09cff-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="09cff-118">A ogni piano di chiamata deve essere associata almeno una regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="09cff-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="09cff-119">A questo scopo, eseguire una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="09cff-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="09cff-120">Per creare una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Aggiungi** e quindi definire la regola.</span><span class="sxs-lookup"><span data-stu-id="09cff-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="09cff-121">Per modificare una regola di normalizzazione già associata al dial plan, selezionarla facendo clic a sinistra del nome della regola e quindi su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="09cff-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="09cff-122">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="09cff-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="09cff-123">Per rimuovere una regola di normalizzazione dal dial plan, selezionarla facendo clic a sinistra del nome della regola e quindi su **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="09cff-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="09cff-124">Disporre le regole di normalizzazione nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="09cff-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="09cff-125">Fare **clic su Sposta su** o Sposta **giù** per modificare la posizione delle regole nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="09cff-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09cff-126">Teams attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="09cff-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="09cff-127">Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano ordinate al di sopra di quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="09cff-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="09cff-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09cff-128">Click **Save**.</span></span>
7. <span data-ttu-id="09cff-129">Se si vuole testare il piano di chiamata, in **Test piano di chiamata** immettere un numero di telefono e quindi fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="09cff-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="09cff-130">Modificare un piano di chiamata</span><span class="sxs-lookup"><span data-stu-id="09cff-130">Edit a dial plan</span></span>

1. <span data-ttu-id="09cff-131">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Piano di**  >  **chiamata vocale.**</span><span class="sxs-lookup"><span data-stu-id="09cff-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="09cff-132">Selezionare il piano di chiamata facendo clic a sinistra del nome del dial plan e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="09cff-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="09cff-133">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="09cff-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="09cff-134">Assegnare un piano di chiamata agli utenti</span><span class="sxs-lookup"><span data-stu-id="09cff-134">Assign a dial plan to users</span></span>

<span data-ttu-id="09cff-135">Assegnare un piano di chiamata nello stesso modo in cui si assegnano i criteri.</span><span class="sxs-lookup"><span data-stu-id="09cff-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="09cff-136">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="09cff-136">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="09cff-137">Avviare PowerShell</span><span class="sxs-lookup"><span data-stu-id="09cff-137">Start PowerShell</span></span>
- <span data-ttu-id="09cff-138">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="09cff-138">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="09cff-139">Creare e gestire i dial plan</span><span class="sxs-lookup"><span data-stu-id="09cff-139">Create and manage your dial plans</span></span>

<span data-ttu-id="09cff-140">È possibile utilizzare un singolo cmdlet o uno script di PowerShell per creare e gestire i piani di chiamata dei tenant.</span><span class="sxs-lookup"><span data-stu-id="09cff-140">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="09cff-141">Utilizzo di cmdlet singolo</span><span class="sxs-lookup"><span data-stu-id="09cff-141">Using single cmdlets</span></span>

- <span data-ttu-id="09cff-142">Per creare un nuovo piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-142">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="09cff-143">Per altri esempi e parametri, consultare[New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09cff-143">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="09cff-144">Per modificare le impostazioni di un piano di chiamata esistente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-144">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="09cff-145">Per altri esempi e parametri, consultare[Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09cff-145">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="09cff-146">Per aggiungere utenti a un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-146">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="09cff-147">Per altri esempi e parametri, consultare [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09cff-147">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="09cff-148">Per visualizzare le impostazioni di un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-148">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="09cff-149">Per altri esempi e parametri, consultare [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="09cff-149">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="09cff-150">Per eliminare un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-150">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="09cff-151">Per altri esempi e parametri, consultare [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="09cff-151">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="09cff-152">Per visualizzare le impostazioni dell'effettivo piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-152">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="09cff-153">Per altri esempi e parametri, consultare [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09cff-153">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="09cff-154">Per testare le impostazioni effettive di un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="09cff-154">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="09cff-155">Per altri esempi e parametri, consultare [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="09cff-155">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="09cff-156">Uso di uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="09cff-156">Using a PowerShell script</span></span>

<span data-ttu-id="09cff-157">Eseguire questa operazione per eliminare una regola di normalizzazione associata a un piano di chiamata tenant senza prima eliminare il piano di chiamata del tenant:</span><span class="sxs-lookup"><span data-stu-id="09cff-157">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="09cff-158">Eseguire questo metodo per aggiungere la seguente regola di normalizzazione al piano di chiamata del tenant denominato RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="09cff-158">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="09cff-159">Eseguire questa operazione per rimuovere la seguente regola di normalizzazione dal piano di chiamata del tenant denominato RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="09cff-159">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="09cff-160">Eseguire quanto segue quando si desidera esaminare anche le regole di normalizzazione esistenti, determinare quale si desidera eliminare e quindi utilizzare l'indice per rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="09cff-160">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="09cff-161">Matrice delle regole di normalizzazione inizia con l'indice 0.</span><span class="sxs-lookup"><span data-stu-id="09cff-161">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="09cff-162">Si desidera rimuovere la regola di normalizzazione a 3 cifre, in modo che sia indice 1.</span><span class="sxs-lookup"><span data-stu-id="09cff-162">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="09cff-163">Eseguire questa operazione per trovare tutti gli utenti a cui è stato concesso il piano di chiamata del tenant RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="09cff-163">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="09cff-164">Esegui questa operazione per rimuovere qualsiasi TenantDialPlan assegnato da tutti gli utenti che hanno un HostingProvider di sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="09cff-164">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="09cff-165">Eseguirli per aggiungere il piano di chiamata esistente locale denominato OPDP1 come un piano di chiamata del tenant per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="09cff-165">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="09cff-166">È necessario innanzitutto salvare il piano di chiamata del tenant locale in un file .xml e quindi utilizzarlo per creare il nuovo piano di chiamata del tenant.</span><span class="sxs-lookup"><span data-stu-id="09cff-166">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="09cff-167">Eseguire questa operazione per salvare il piano di chiamata del tenant locale nel file .xml.</span><span class="sxs-lookup"><span data-stu-id="09cff-167">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="09cff-168">Eseguire questa operazione per creare il nuovo piano di chiamata del tenant.</span><span class="sxs-lookup"><span data-stu-id="09cff-168">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="09cff-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="09cff-169">Related topics</span></span>

- [<span data-ttu-id="09cff-170">Che cosa sono i piani di chiamata?</span><span class="sxs-lookup"><span data-stu-id="09cff-170">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="09cff-171">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="09cff-171">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="09cff-172">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="09cff-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="09cff-173">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="09cff-173">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="09cff-174">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="09cff-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="09cff-175">[Etichetta di esclusione di responsabilità per chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="09cff-175">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="09cff-176">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="09cff-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)