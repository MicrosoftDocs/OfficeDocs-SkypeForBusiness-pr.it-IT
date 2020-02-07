---
title: Creare e impostare piani di chiamata
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
description: Informazioni su come creare e gestire i dial plan (PSTN Calling dial plans) e su come gestirli.
ms.openlocfilehash: 774b0a78f39b91b634ed0833be3497935cb25c4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826924"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="14329-103">Creare e impostare piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="14329-103">Create and manage dial plans</span></span>

<span data-ttu-id="14329-104">Dopo aver pianificato i dial plan per l'organizzazione e aver individuato tutte le regole di normalizzazione che devono essere create per il routing delle chiamate, si è pronti per creare i dial plan.</span><span class="sxs-lookup"><span data-stu-id="14329-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="14329-105">È possibile usare l'interfaccia di amministrazione di Microsoft teams o Windows PowerShell per creare e gestire piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="14329-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="14329-106">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14329-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="14329-107">Creare un dial plan</span><span class="sxs-lookup"><span data-stu-id="14329-107">Create a dial plan</span></span>

1. <span data-ttu-id="14329-108">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Voice** > **dial plan**.</span><span class="sxs-lookup"><span data-stu-id="14329-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="14329-109">Fare clic su **Aggiungi**e quindi immettere un nome e una descrizione per il dial plan.</span><span class="sxs-lookup"><span data-stu-id="14329-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="14329-110">![Schermata che mostra la pagina Aggiungi per la creazione di un dial plan](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="14329-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="14329-111">In **Dettagli dial plan**specificare un prefisso di chiamata esterna se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna.</span><span class="sxs-lookup"><span data-stu-id="14329-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="14329-112">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="14329-112">To do this:</span></span>
    1. <span data-ttu-id="14329-113">Nella casella **prefisso di chiamata esterna** immettere un prefisso per la chiamata esterna.</span><span class="sxs-lookup"><span data-stu-id="14329-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="14329-114">Il prefisso può contenere fino a quattro caratteri (#, \* e 0-9).</span><span class="sxs-lookup"><span data-stu-id="14329-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="14329-115">Attivare la **chiamata a dispositivi ottimizzati**.</span><span class="sxs-lookup"><span data-stu-id="14329-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="14329-116">Se si specifica un prefisso di chiamata esterna, è necessario attivare anche questa impostazione per applicare il prefisso, in modo che le chiamate possano essere effettuate all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14329-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="14329-117">In **regole di normalizzazione**configurare e associare una o più [regole di normalizzazione](what-are-dial-plans.md#normalization-rules) per il dial plan.</span><span class="sxs-lookup"><span data-stu-id="14329-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="14329-118">A ogni dial plan deve essere associata almeno una regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="14329-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="14329-119">A questo scopo, eseguire una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="14329-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="14329-120">Per creare una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Aggiungi**e quindi definire la regola.</span><span class="sxs-lookup"><span data-stu-id="14329-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="14329-121">Per modificare una regola di normalizzazione già associata al dial plan, selezionare la regola facendo clic a sinistra del nome della regola, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="14329-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="14329-122">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="14329-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="14329-123">Per rimuovere una regola di normalizzazione dal dial plan, selezionare la regola facendo clic a sinistra del nome della regola, quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="14329-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="14329-124">Disporre le regole di normalizzazione nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="14329-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="14329-125">Fare clic su spostarsi verso l' **alto** o spostarsi verso il **basso** per modificare la posizione delle regole nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="14329-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="14329-126">Teams attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="14329-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="14329-127">Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="14329-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="14329-128">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="14329-128">Click **Save**.</span></span>
7. <span data-ttu-id="14329-129">Se si vuole testare il dial plan, in **dial plan di prova**immettere un numero di telefono e quindi fare clic su **test**.</span><span class="sxs-lookup"><span data-stu-id="14329-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="14329-130">Modificare un dial plan</span><span class="sxs-lookup"><span data-stu-id="14329-130">Edit a dial plan</span></span>

1. <span data-ttu-id="14329-131">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Voice** > **dial plan**.</span><span class="sxs-lookup"><span data-stu-id="14329-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="14329-132">Selezionare il dial plan facendo clic a sinistra del nome del dial plan, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="14329-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="14329-133">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="14329-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="14329-134">Aggiungere utenti a un dial plan</span><span class="sxs-lookup"><span data-stu-id="14329-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="14329-135">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Voice** > **dial plan**.</span><span class="sxs-lookup"><span data-stu-id="14329-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="14329-136">Selezionare il dial plan facendo clic a sinistra del nome del dial plan.</span><span class="sxs-lookup"><span data-stu-id="14329-136">Select the dial plan by clicking to the left of the dial plan name.</span></span>
3. <span data-ttu-id="14329-137">Selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="14329-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="14329-138">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="14329-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="14329-139">Ripetere questo passaggio per ogni utente che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="14329-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="14329-140">Al termine dell'aggiunta di utenti, selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="14329-140">When you're finished adding users, select **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="14329-141">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="14329-141">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="14329-142">Verificare e avviare Remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="14329-142">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="14329-143">**Verificare che sia in esecuzione Windows PowerShell versione 3,0 o successiva**</span><span class="sxs-lookup"><span data-stu-id="14329-143">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="14329-144">Per verificare che sia in esecuzione la versione 3,0 o successiva: **menu** > Start di**Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="14329-144">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="14329-145">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="14329-145">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="14329-146">Se non si ha la versione 3,0 o successiva, scaricare e installare gli aggiornamenti in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14329-146">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="14329-147">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="14329-147">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="14329-148">Riavviare il computer quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="14329-148">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="14329-149">È inoltre necessario installare il modulo Windows PowerShell per Skype for business online che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="14329-149">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="14329-150">Puoi scaricare questo modulo, supportato solo in computer a 64 bit, nel [modulo di Windows PowerShell per Skype for business online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="14329-150">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="14329-151">Riavviare il computer se richiesto.</span><span class="sxs-lookup"><span data-stu-id="14329-151">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="14329-152">Per altre informazioni, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="14329-152">To learn more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="14329-153">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="14329-153">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="14329-154">Fare clic su **Avvia** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="14329-154">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="14329-155">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="14329-155">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14329-156">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="14329-156">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="14329-157">Creare e gestire i piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="14329-157">Create and manage your dial plans</span></span>

<span data-ttu-id="14329-158">È possibile utilizzare un singolo cmdlet o uno script di PowerShell per creare e gestire i piani di chiamata dei tenant.</span><span class="sxs-lookup"><span data-stu-id="14329-158">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="14329-159">Utilizzo di cmdlet singolo</span><span class="sxs-lookup"><span data-stu-id="14329-159">Using single cmdlets</span></span>

- <span data-ttu-id="14329-160">Per creare un nuovo piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-160">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="14329-161">Per altri esempi e parametri, consultare[New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="14329-161">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="14329-162">Per modificare le impostazioni di un dial plan esistente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-162">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="14329-163">Per altri esempi e parametri, consultare[Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="14329-163">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="14329-164">Per aggiungere utenti a un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-164">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="14329-165">Per altri esempi e parametri, consultare [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="14329-165">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="14329-166">Per visualizzare le impostazioni di un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-166">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="14329-167">Per altri esempi e parametri, consultare [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14329-167">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="14329-168">Per eliminare un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-168">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="14329-169">Per altri esempi e parametri, consultare [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14329-169">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="14329-170">Per visualizzare le impostazioni dell'effettivo piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-170">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="14329-171">Per altri esempi e parametri, consultare [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="14329-171">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="14329-172">Per testare le impostazioni effettive di un piano di chiamata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="14329-172">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="14329-173">Per altri esempi e parametri, consultare [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14329-173">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="14329-174">Uso di uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="14329-174">Using a PowerShell script</span></span>

<span data-ttu-id="14329-175">Esegui questa operazione per eliminare una regola di normalizzazione associata a un dial plan tenant senza dover eliminare prima di tutto il piano di chiamata del tenant:</span><span class="sxs-lookup"><span data-stu-id="14329-175">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="14329-176">Eseguire questo metodo per aggiungere la seguente regola di normalizzazione al piano di chiamata del tenant denominato RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="14329-176">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="14329-177">Eseguire questa operazione per rimuovere la seguente regola di normalizzazione dal piano di chiamata del tenant denominato RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="14329-177">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="14329-178">Eseguire quanto segue quando si desidera esaminare anche le regole di normalizzazione esistenti, determinare quale si desidera eliminare e quindi utilizzare l'indice per rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="14329-178">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="14329-179">Matrice delle regole di normalizzazione inizia con l'indice 0.</span><span class="sxs-lookup"><span data-stu-id="14329-179">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="14329-180">Si desidera rimuovere la regola di normalizzazione a 3 cifre, in modo che sia indice 1.</span><span class="sxs-lookup"><span data-stu-id="14329-180">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="14329-181">Eseguire questa operazione per trovare tutti gli utenti a cui è stato concesso il piano di chiamata del tenant RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="14329-181">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="14329-182">Esegui questa operazione per rimuovere eventuali TenantDialPlan assegnati da tutti gli utenti che hanno un provider dihosting di sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14329-182">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="14329-183">Eseguirli per aggiungere il piano di chiamata esistente locale denominato OPDP1 come un piano di chiamata del tenant per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14329-183">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="14329-184">È necessario innanzitutto salvare il piano di chiamata del tenant locale in un file .xml e quindi utilizzarlo per creare il nuovo piano di chiamata del tenant.</span><span class="sxs-lookup"><span data-stu-id="14329-184">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="14329-185">Eseguire questa operazione per salvare il piano di chiamata del tenant locale nel file .xml.</span><span class="sxs-lookup"><span data-stu-id="14329-185">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="14329-186">Eseguire questa operazione per creare il nuovo piano di chiamata del tenant.</span><span class="sxs-lookup"><span data-stu-id="14329-186">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="14329-187">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="14329-187">Related topics</span></span>

- [<span data-ttu-id="14329-188">Che cosa sono i piani di chiamata?</span><span class="sxs-lookup"><span data-stu-id="14329-188">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="14329-189">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="14329-189">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="14329-190">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="14329-190">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="14329-191">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="14329-191">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="14329-192">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="14329-192">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="14329-193">[Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="14329-193">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="14329-194">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="14329-194">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
