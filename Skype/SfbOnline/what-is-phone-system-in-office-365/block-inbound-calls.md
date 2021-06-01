---
title: Bloccare le chiamate in ingresso in Skype for Business Online
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238032"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="b8751-102">Bloccare le chiamate in ingresso</span><span class="sxs-lookup"><span data-stu-id="b8751-102">Block inbound calls</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="b8751-103">Skype for Business I piani per chiamate online ora supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="b8751-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="b8751-104">Questa caratteristica consente di definire un elenco globale tenant di schemi numerici in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere verificato rispetto all'elenco per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="b8751-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="b8751-105">Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.</span><span class="sxs-lookup"><span data-stu-id="b8751-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="b8751-106">Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso provenienti dalla rete PSTN e funziona solo su base tenant-globale.</span><span class="sxs-lookup"><span data-stu-id="b8751-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="b8751-107">Non è disponibile per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="b8751-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="b8751-108">Questa funzionalità non è ancora disponibile per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="b8751-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="b8751-109">I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati.</span><span class="sxs-lookup"><span data-stu-id="b8751-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="b8751-110">Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non è consentita per il completamento.</span><span class="sxs-lookup"><span data-stu-id="b8751-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="b8751-111">Alcuni esempi possono includere un messaggio dell'operatore che indica che la chiamata non può essere completata come chiamata o semplicemente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b8751-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="b8751-112">Informazioni e controlli di amministrazione del blocco delle chiamate</span><span class="sxs-lookup"><span data-stu-id="b8751-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="b8751-113">I controlli di amministrazione per i numeri di blocco vengono forniti solo tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8751-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="b8751-114">I criteri dei blocchi numerici sono definiti come criteri di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="b8751-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="b8751-115">L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco causa il blocco della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b8751-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="b8751-116">Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore prima che il criterio diventi attivo.</span><span class="sxs-lookup"><span data-stu-id="b8751-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="b8751-117">Comandi di PowerShell per il blocco delle chiamate</span><span class="sxs-lookup"><span data-stu-id="b8751-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="b8751-118">I modelli numerici vengono gestiti ```CsInboundBlockedNumberPattern``` tramite i comandi , , , e ```New``` ```Get``` ```Set``` ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="b8751-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="b8751-119">È possibile gestire un determinato criterio usando questi cmdlet, inclusa la possibilità di attivare o disattivare un determinato criterio.</span><span class="sxs-lookup"><span data-stu-id="b8751-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="b8751-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco tenant, tra cui Name, Description, Enabled (True/False) e Pattern per ognuno.</span><span class="sxs-lookup"><span data-stu-id="b8751-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="b8751-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge uno schema di numeri bloccati all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="b8751-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove uno schema di numeri bloccati dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="b8751-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di uno schema di numeri bloccati nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="b8751-124">La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate vengono gestite tramite ```CsTenantBlockingCallingNumbers``` i ```Get``` comandi e ```Set``` .</span><span class="sxs-lookup"><span data-stu-id="b8751-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="b8751-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco globale dei numeri bloccati, tra cui Enabled (True/False).</span><span class="sxs-lookup"><span data-stu-id="b8751-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="b8751-126">Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la caratteristica.</span><span class="sxs-lookup"><span data-stu-id="b8751-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="b8751-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale per essere attivate e disattivate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="b8751-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="b8751-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="b8751-129">Bloccare un numero</span><span class="sxs-lookup"><span data-stu-id="b8751-129">Block a number</span></span>

<span data-ttu-id="b8751-130">In questo esempio i parametri ```-Enabled``` e ```-Description``` sono facoltativi:</span><span class="sxs-lookup"><span data-stu-id="b8751-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="b8751-131">La creazione di un nuovo criterio aggiunge il motivo come abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b8751-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="b8751-132">La descrizione è un campo facoltativo per fornire altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b8751-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="b8751-133">È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui è stato aggiunto il criterio.</span><span class="sxs-lookup"><span data-stu-id="b8751-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="b8751-134">Nel caso di bloccare semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso modello di numero corrispondente e aggiungere altre informazioni nella descrizione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b8751-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="b8751-135">I criteri vengono abbinati usando espressioni regolari (Regex).</span><span class="sxs-lookup"><span data-stu-id="b8751-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="b8751-136">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="b8751-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="b8751-137">Consenti un numero</span><span class="sxs-lookup"><span data-stu-id="b8751-137">Allow a number</span></span>

<span data-ttu-id="b8751-138">In questo esempio il ```-Identity``` parametro è obbligatorio:</span><span class="sxs-lookup"><span data-stu-id="b8751-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="b8751-139">Se l'identità non è nota, usare il cmdlet per individuare prima lo ```Get-CsInboundBlockedNumberPattern``` schema corretto e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="b8751-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="b8751-140">Eseguire quindi il ```Remove-CsTenantBlockedNumberPattern``` cmdlet e passare il valore identity appropriato.</span><span class="sxs-lookup"><span data-stu-id="b8751-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="b8751-141">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="b8751-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="b8751-142">Visualizzare tutti i modelli numerici</span><span class="sxs-lookup"><span data-stu-id="b8751-142">View all number patterns</span></span>

<span data-ttu-id="b8751-143">L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:</span><span class="sxs-lookup"><span data-stu-id="b8751-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="b8751-144">Usare le funzionalità di filtro incorporate di PowerShell per analizzare i valori restituiti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b8751-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="b8751-145">Aggiungere eccezioni numeri</span><span class="sxs-lookup"><span data-stu-id="b8751-145">Add number exceptions</span></span>

<span data-ttu-id="b8751-146">È possibile aggiungere eccezioni ai modelli di numeri bloccati tramite i ```CsTenantBlockNumberExceptionPattern``` comandi , , , e ```New``` ```Get``` ```Set``` ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="b8751-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="b8751-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) aggiunge un modello di eccezione numerica all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="b8751-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) restituisce un elenco di tutti i modelli di eccezione numerica aggiunti all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="b8751-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o più parametri in un modello di eccezione numerica nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="b8751-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove uno schema di eccezione numerica dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="b8751-151">Esempi</span><span class="sxs-lookup"><span data-stu-id="b8751-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="b8751-152">Aggiungere un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="b8751-152">Add a number exception</span></span>

<span data-ttu-id="b8751-153">In questo esempio viene creato un nuovo modello di eccezione numerica che, per impostazione predefinita, aggiunge il modello come abilitato.</span><span class="sxs-lookup"><span data-stu-id="b8751-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="b8751-154">I ```-Enabled``` parametri e sono ```-Description``` facoltativi.</span><span class="sxs-lookup"><span data-stu-id="b8751-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="b8751-155">Visualizzare tutte le eccezioni numeri</span><span class="sxs-lookup"><span data-stu-id="b8751-155">View all number exceptions</span></span>

<span data-ttu-id="b8751-156">In questo esempio il parametro -Identity è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b8751-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="b8751-157">Se il parametro non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione ```-Identity``` numerica immessi per un tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="b8751-158">Modificare un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="b8751-158">Modify a number exception</span></span>

<span data-ttu-id="b8751-159">In questo esempio il parametro -Identity è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8751-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="b8751-160">Il ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet consente di modificare uno o più parametri per una determinata identità dello schema di numeri.</span><span class="sxs-lookup"><span data-stu-id="b8751-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="b8751-161">Rimuovere un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="b8751-161">Remove a number exception</span></span>

<span data-ttu-id="b8751-162">In questo esempio il ```-Identity``` parametro è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8751-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="b8751-163">Questo cmdlet rimuove il modello di numero specificato dall'elenco dei tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="b8751-164">Se l'identità non è nota, usare il cmdlet per individuare prima lo ```Get-CsInboundBlockedNumberPattern``` schema corretto e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="b8751-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="b8751-165">Eseguire quindi il ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet e passare il valore identity appropriato.</span><span class="sxs-lookup"><span data-stu-id="b8751-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="b8751-166">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="b8751-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="b8751-167">Verificare se un numero è bloccato</span><span class="sxs-lookup"><span data-stu-id="b8751-167">Test whether a number is blocked</span></span>

<span data-ttu-id="b8751-168">Usare il ```Test-CsInboundBlockedNumberPattern``` cmdlet per verificare se un numero è bloccato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="b8751-169">In questo esempio i ```-Phonenumber``` parametri e ```-Tenant``` sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="b8751-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="b8751-170">Il ```-PhoneNumber``` parametro deve essere una stringa numerica senza altri caratteri, ad esempio + o -.</span><span class="sxs-lookup"><span data-stu-id="b8751-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="b8751-171">In TRPS l'opzione ```-Tenant parameter``` è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b8751-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="b8751-172">Il parametro risultante restituisce il valore True se il numero è bloccato nel ```isNumberBlocked``` tenant e False se non è bloccato.</span><span class="sxs-lookup"><span data-stu-id="b8751-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="b8751-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="b8751-173">httpResponseCode</span></span>  |<span data-ttu-id="b8751-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="b8751-174">isNumberBlocked</span></span>   |<span data-ttu-id="b8751-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="b8751-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b8751-176">200</span><span class="sxs-lookup"><span data-stu-id="b8751-176">200</span></span>    | <span data-ttu-id="b8751-177">Vero</span><span class="sxs-lookup"><span data-stu-id="b8751-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="b8751-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="b8751-178">httpResponseCode</span></span>  |<span data-ttu-id="b8751-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="b8751-179">isNumberBlocked</span></span>   |<span data-ttu-id="b8751-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="b8751-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b8751-181">200</span><span class="sxs-lookup"><span data-stu-id="b8751-181">200</span></span>    | <span data-ttu-id="b8751-182">Falso</span><span class="sxs-lookup"><span data-stu-id="b8751-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="b8751-183">Nota su Regex</span><span class="sxs-lookup"><span data-stu-id="b8751-183">A note about Regex</span></span>

<span data-ttu-id="b8751-184">Come indicato in precedenza, la corrispondenza dei criteri per bloccare i chiamanti viene eseguita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="b8751-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="b8751-185">Sono disponibili più strumenti online per convalidare una corrispondenza dei criteri Regex.</span><span class="sxs-lookup"><span data-stu-id="b8751-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="b8751-186">Se non si ha familiarità con i modelli Regex, è consigliabile acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="b8751-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="b8751-187">Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze di numeri bloccati al tenant.</span><span class="sxs-lookup"><span data-stu-id="b8751-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b8751-188">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b8751-188">Related topics</span></span>

- [<span data-ttu-id="b8751-189">Configurare il computer per la gestione Skype for Business Online usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8751-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
