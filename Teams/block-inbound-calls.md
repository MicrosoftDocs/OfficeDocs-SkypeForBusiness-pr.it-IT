---
title: Bloccare le chiamate in Microsoft Teams
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689764"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="d3ab7-102">Bloccare le chiamate in ingresso</span><span class="sxs-lookup"><span data-stu-id="d3ab7-102">Block inbound calls</span></span>

<span data-ttu-id="d3ab7-103">I piani per chiamate Microsoft, il routing diretto e l'operatore Connessione supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d3ab7-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="d3ab7-104">Questa caratteristica consente a un amministratore di definire un elenco di schemi numerici a livello globale del tenant in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere verificato in base all'elenco per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="d3ab7-105">Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="d3ab7-106">Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso che provengono dalla rete PSTN e funzionano solo a livello globale del tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="d3ab7-107">I singoli Teams utenti non possono modificare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="d3ab7-108">Il client Teams consente ai singoli utenti di bloccare le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="d3ab7-109">Per informazioni su come gli utenti finali possono implementare il blocco delle chiamate, vedere [Gestire le impostazioni delle chiamate in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="d3ab7-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="d3ab7-110">I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="d3ab7-111">Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non è consentita per il completamento.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="d3ab7-112">Alcuni esempi possono includere un messaggio dell'operatore che indica che la chiamata non può essere completata come chiamata o semplicemente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="d3ab7-113">Informazioni e controlli di amministrazione del blocco delle chiamate</span><span class="sxs-lookup"><span data-stu-id="d3ab7-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="d3ab7-114">I controlli di amministrazione per i numeri di blocco vengono forniti solo tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="d3ab7-115">I criteri dei blocchi numerici sono definiti come criteri di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="d3ab7-116">L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco causa il blocco della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="d3ab7-117">Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore prima che il criterio diventi attivo.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="d3ab7-118">Comandi di PowerShell per il blocco delle chiamate</span><span class="sxs-lookup"><span data-stu-id="d3ab7-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="d3ab7-119">Per gestire i modelli numerici, usare i cmdlet **New-**, **Get-**, **Set-** e **Remove-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="d3ab7-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="d3ab7-120">È possibile gestire un determinato criterio usando questi cmdlet, inclusa la possibilità di attivare o disattivare un determinato criterio.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="d3ab7-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco tenant, tra cui Name, Description, Enabled (True/False) e Pattern per ognuno.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="d3ab7-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge uno schema di numeri bloccati all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="d3ab7-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove uno schema di numeri bloccati dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="d3ab7-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di uno schema di numeri bloccati nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="d3ab7-125">La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate vengono gestite tramite i cmdlet **Get-** e **Set-CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="d3ab7-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="d3ab7-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i modelli di numero di blocco in ingresso e i parametri dei modelli di numeri esenti in ingresso per l'elenco globale dei numeri bloccati.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="d3ab7-127">Questo cmdlet restituisce anche se il blocco è stato abilitato (True o False).</span><span class="sxs-lookup"><span data-stu-id="d3ab7-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="d3ab7-128">Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la caratteristica.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="d3ab7-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale per essere attivate e disattivate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="d3ab7-130">Esempi</span><span class="sxs-lookup"><span data-stu-id="d3ab7-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="d3ab7-131">Bloccare un numero</span><span class="sxs-lookup"><span data-stu-id="d3ab7-131">Block a number</span></span>

<span data-ttu-id="d3ab7-132">Nell'esempio seguente l'amministratore tenant vuole bloccare tutte le chiamate provenienti dall'intervallo di numeri 1 (312) da 555-0000 a 1 (312) 555-9999.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="d3ab7-133">Lo schema dei numeri viene creato in modo che sia i numeri nell'intervallo con + preceduti che i numeri nell'intervallo senza + prefissi corrispondano.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="d3ab7-134">Non è necessario includere i simboli e () nei numeri di telefono perché il sistema rimuove questi simboli prima della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="d3ab7-135">Per attivare lo schema dei numeri, il **parametro Enabled** è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="d3ab7-136">Per disabilitare questo modello di numero specifico, impostare il parametro su False.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="d3ab7-137">Nell'esempio successivo, l'amministratore tenant vuole bloccare tutte le chiamate provenienti dal numero 1 (412) 555-1234.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="d3ab7-138">Per attivare lo schema dei numeri, il **parametro Enabled** è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="d3ab7-139">La creazione di un nuovo criterio aggiunge il motivo come abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="d3ab7-140">La descrizione è un campo facoltativo per fornire altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="d3ab7-141">È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui è stato aggiunto il criterio.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="d3ab7-142">Nel caso di bloccare semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso modello di numero corrispondente e aggiungere altre informazioni nella descrizione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="d3ab7-143">I criteri vengono abbinati usando espressioni regolari (Regex).</span><span class="sxs-lookup"><span data-stu-id="d3ab7-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="d3ab7-144">Per altre informazioni, vedere [Uso di Regex.](#using-regex)</span><span class="sxs-lookup"><span data-stu-id="d3ab7-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="d3ab7-145">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="d3ab7-146">Consenti un numero</span><span class="sxs-lookup"><span data-stu-id="d3ab7-146">Allow a number</span></span>

<span data-ttu-id="d3ab7-147">È possibile consentire la chiamata di un numero rimuovendo lo schema di numeri bloccati.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="d3ab7-148">Nell'esempio seguente l'amministratore tenant vuole consentire a 1 (412) 555-1234 di effettuare di nuovo le chiamate.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="d3ab7-149">Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima il criterio appropriato e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="d3ab7-150">Eseguire quindi il cmdlet **Remove-CsInboundBlockedNumberPattern** e passare il valore identity appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="d3ab7-151">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="d3ab7-152">Visualizzare tutti i modelli numerici</span><span class="sxs-lookup"><span data-stu-id="d3ab7-152">View all number patterns</span></span>

<span data-ttu-id="d3ab7-153">L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:</span><span class="sxs-lookup"><span data-stu-id="d3ab7-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="d3ab7-154">Usare le funzionalità di filtro incorporate di PowerShell per analizzare i valori restituiti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="d3ab7-155">Aggiungere eccezioni numeri</span><span class="sxs-lookup"><span data-stu-id="d3ab7-155">Add number exceptions</span></span>

<span data-ttu-id="d3ab7-156">È possibile aggiungere eccezioni ai modelli di numero bloccati usando i cmdlet **New-**, **Get-**, **Set-** e **Remove-CsInboundExemptNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="d3ab7-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="d3ab7-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) aggiunge un modello di eccezione numerica all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="d3ab7-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) restituisce un elenco di tutti i modelli di eccezione numerica aggiunti all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="d3ab7-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica uno o più parametri in un modello di eccezione numerica nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="d3ab7-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) rimuove uno schema di eccezione numerica dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="d3ab7-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="d3ab7-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="d3ab7-162">Aggiungere un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="d3ab7-162">Add a number exception</span></span>

<span data-ttu-id="d3ab7-163">Nell'esempio seguente l'amministratore del tenant vuole consentire ai numeri di telefono 1 (312) 555-8882 e 1 (312) 555-8883 di effettuare chiamate al tenant, anche se questi due numeri di telefono sono nell'intervallo bloccato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="d3ab7-164">Per abilitare questa funzionalità, viene creato un nuovo modello di eccezione numerica nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d3ab7-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="d3ab7-165">Per attivare lo schema dei numeri, il **parametro Enabled** è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="d3ab7-166">Per disabilitare questo modello di numero specifico, impostare il parametro su False.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="d3ab7-167">Visualizzare tutte le eccezioni numeri</span><span class="sxs-lookup"><span data-stu-id="d3ab7-167">View all number exceptions</span></span>

<span data-ttu-id="d3ab7-168">In questo esempio il parametro **Identity** è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="d3ab7-169">Se il **parametro Identity** non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione numerica immessi per un tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="d3ab7-170">Modificare un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="d3ab7-170">Modify a number exception</span></span>

<span data-ttu-id="d3ab7-171">Il cmdlet **Set-CsInboundExemptNumberPattern** consente di modificare uno o più parametri per una determinata identità dello schema di numeri.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="d3ab7-172">In questo esempio il **parametro Identity** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="d3ab7-173">Rimuovere un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="d3ab7-173">Remove a number exception</span></span>

<span data-ttu-id="d3ab7-174">Il cmdlet **Remove-CsInboundExemptNumberPattern** rimuove il modello di numero specificato dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="d3ab7-175">In questo esempio il **parametro Identity** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="d3ab7-176">Se l'identità non è nota, usare il cmdlet **Get-CsInboundExemptNumberPattern** per individuare prima il criterio appropriato e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="d3ab7-177">Eseguire quindi il cmdlet **Remove-CsInboundExemptNumberPattern** e passare il valore identity appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="d3ab7-178">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="d3ab7-179">Verificare se un numero è bloccato</span><span class="sxs-lookup"><span data-stu-id="d3ab7-179">Test whether a number is blocked</span></span>

<span data-ttu-id="d3ab7-180">Usare il cmdlet **Test-CsInboundBlockedNumberPattern** per verificare se un numero è bloccato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="d3ab7-181">Il **parametro PhoneNumber** è obbligatorio e deve essere una stringa numerica senza altri caratteri, ad esempio +, - o ().</span><span class="sxs-lookup"><span data-stu-id="d3ab7-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="d3ab7-182">Il parametro **IsNumberBlocked** risultante restituisce il valore True se il numero è bloccato nel tenant. il parametro restituisce False se non è bloccato.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="d3ab7-183">Esempi</span><span class="sxs-lookup"><span data-stu-id="d3ab7-183">Examples</span></span>

<span data-ttu-id="d3ab7-184">In questi esempi si può vedere che il numero di telefono 1 (312) 555-8884 è bloccato perché dovrebbe essere nell'intervallo bloccato sopra, mentre il numero di telefono 1 (312) 555-8883 è autorizzato a chiamare come dovrebbe essere basato sull'esenzione creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a><span data-ttu-id="d3ab7-185">Uso di Regex</span><span class="sxs-lookup"><span data-stu-id="d3ab7-185">Using Regex</span></span>

<span data-ttu-id="d3ab7-186">La corrispondenza dei criteri per bloccare i chiamanti viene eseguita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="d3ab7-187">Sono disponibili più strumenti online per convalidare una corrispondenza dei criteri Regex.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="d3ab7-188">Se non si ha familiarità con i modelli Regex, è consigliabile acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="d3ab7-189">Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze di numeri bloccati al tenant.</span><span class="sxs-lookup"><span data-stu-id="d3ab7-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>