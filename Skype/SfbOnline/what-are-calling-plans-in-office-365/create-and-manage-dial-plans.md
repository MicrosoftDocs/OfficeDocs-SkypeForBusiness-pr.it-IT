---
title: Creare e gestire i dial plan
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Informazioni su come creare chiamante dial plan (chiamata PSTN dial plan) in Office 365 e a gestirli. '
ms.openlocfilehash: a7a9e599e54f5b59a748d5c9a215cc64b33e53a0
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="ad67d-103">Creare e gestire i dial plan</span><span class="sxs-lookup"><span data-stu-id="ad67d-103">Create and manage dial plans</span></span>

<span data-ttu-id="ad67d-104">Dopo aver pianificato i dial plan per l'organizzazione e individuare il tutte le regole di normalizzazione che devono essere creati per il routing delle chiamate, è necessario utilizzare Windows PowerShell per creare i dial plan e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ad67d-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad67d-105">Skype per interfaccia di amministrazione di Business non può essere utilizzato per creare e gestire i dial plan.</span><span class="sxs-lookup"><span data-stu-id="ad67d-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="ad67d-106">Verifica e avviare PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="ad67d-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="ad67d-107">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="ad67d-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="ad67d-108">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad67d-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ad67d-109">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad67d-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ad67d-p101">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="ad67d-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ad67d-p102">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="ad67d-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="ad67d-116">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="ad67d-117">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ad67d-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="ad67d-118">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad67d-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ad67d-119">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="ad67d-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad67d-120">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="ad67d-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="ad67d-121">Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="ad67d-122">Creazione e gestione dei dial plan</span><span class="sxs-lookup"><span data-stu-id="ad67d-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="ad67d-123">È possibile utilizzare un singolo cmdlet o uno script di PowerShell per creare e gestire i tenant dial plan.</span><span class="sxs-lookup"><span data-stu-id="ad67d-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="ad67d-124">Utilizzo dei cmdlet singolo</span><span class="sxs-lookup"><span data-stu-id="ad67d-124">Using single cmdlets</span></span>

- <span data-ttu-id="ad67d-125">Per creare un nuovo dial plan, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="ad67d-126">Per altri esempi e sui parametri, vedere [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="ad67d-127">Per apportare modifiche alle impostazioni a un dial plan esistente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="ad67d-128">Per altri esempi e sui parametri, vedere [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="ad67d-129">Per aggiungere utenti a un dial plan, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="ad67d-130">Per altri esempi e sui parametri, vedere [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="ad67d-131">Per visualizzare le impostazioni di un dial plan, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="ad67d-132">Per altri esempi e sui parametri, vedere [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="ad67d-133">Per eliminare un dial plan, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="ad67d-134">Per altri esempi e sui parametri, vedere [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="ad67d-135">Per visualizzare le impostazioni del efficace dial plan, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="ad67d-136">Per altri esempi e sui parametri, vedere [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="ad67d-137">Per testare le impostazioni effettive di un dial plan, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ad67d-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="ad67d-138">Per altri esempi e sui parametri, vedere [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad67d-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="ad67d-139">Utilizzo di uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad67d-139">Using a PowerShell script</span></span>

<span data-ttu-id="ad67d-140">Eseguire questa opzione per eliminare una regola di normalizzazione è associata un tenant plan di messaggistica unificata senza dover prima di eliminare il dial plan tenant:</span><span class="sxs-lookup"><span data-stu-id="ad67d-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="ad67d-141">Eseguire questo metodo per aggiungere una regola di normalizzazione seguenti a tenant dial plan esistente denominato RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="ad67d-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="ad67d-142">Eseguire questa operazione per rimuovere la regola di normalizzazione seguenti dal tenant dial plan esistente denominato RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="ad67d-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="ad67d-143">Eseguire quanto segue quando si desidera esaminare le regole di normalizzazione esistente, determinare quale si desidera eliminare e quindi utilizzare l'indice per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="ad67d-143">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="ad67d-144">Matrice delle regole di normalizzazione inizia con indice 0.</span><span class="sxs-lookup"><span data-stu-id="ad67d-144">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="ad67d-145">Si desidera rimuovere la regola di normalizzazione 3 cifre, in modo che sia indice 1.</span><span class="sxs-lookup"><span data-stu-id="ad67d-145">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="ad67d-146">Eseguire questa operazione per trovare tutti gli utenti che sono state concesse tenant RedmondDialPlan dial plan.</span><span class="sxs-lookup"><span data-stu-id="ad67d-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="ad67d-147">Eseguire questi per aggiungere che esistente locale dei dial plan denominato OPDP1 come un dial plan tenant per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad67d-147">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="ad67d-148">È necessario innanzitutto Salva locale dei dial plan in un file XML e quindi utilizzarla per creare il nuovo dial plan di tenant.</span><span class="sxs-lookup"><span data-stu-id="ad67d-148">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="ad67d-149">Eseguire questa operazione per salvare il dial plan locale per il file XML.</span><span class="sxs-lookup"><span data-stu-id="ad67d-149">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="ad67d-150">Eseguire questa operazione per creare il nuovo dial plan di tenant.</span><span class="sxs-lookup"><span data-stu-id="ad67d-150">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ad67d-151">Per ulteriori informazioni su Windows Powershell?</span><span class="sxs-lookup"><span data-stu-id="ad67d-151">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="ad67d-p105">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="ad67d-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ad67d-155">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ad67d-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ad67d-156">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="ad67d-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ad67d-p106">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad67d-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ad67d-159">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="ad67d-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ad67d-160">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ad67d-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ad67d-161">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ad67d-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ad67d-162">See also</span><span class="sxs-lookup"><span data-stu-id="ad67d-162">Related topics</span></span>
[<span data-ttu-id="ad67d-163">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="ad67d-163">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="ad67d-164">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="ad67d-164">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ad67d-165">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="ad67d-165">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="ad67d-166">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="ad67d-166">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="ad67d-167">Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ad67d-167">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 