---
title: Bloccare le chiamate in ingresso in Skype for business online
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266065"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="ad31c-102">Bloccare le chiamate in ingresso</span><span class="sxs-lookup"><span data-stu-id="ad31c-102">Block inbound calls</span></span>

<span data-ttu-id="ad31c-103">I piani per le chiamate di Skype for business online ora supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="ad31c-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="ad31c-104">Questa caratteristica consente di definire un elenco globale tenant di pattern numerici in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere controllato rispetto all'elenco per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ad31c-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="ad31c-105">Se viene eseguita una corrispondenza, viene rifiutata una chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="ad31c-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="ad31c-106">Questa funzionalità di blocco delle chiamate in ingresso funziona solo sulle chiamate in ingresso che provengono dalla rete PSTN e funziona solo su base globale del tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="ad31c-107">Non è disponibile per singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="ad31c-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="ad31c-108">Questa caratteristica non è ancora disponibile per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ad31c-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="ad31c-109">I chiamanti bloccati possono verificare comportamenti leggermente diversi quando sono stati bloccati.</span><span class="sxs-lookup"><span data-stu-id="ad31c-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="ad31c-110">Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non può essere completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ad31c-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="ad31c-111">Gli esempi possono includere un messaggio portante che indica che la chiamata non può essere completata come chiamata o semplicemente eliminando la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad31c-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="ad31c-112">Chiamata che blocca i controlli e le informazioni dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="ad31c-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="ad31c-113">I controlli di amministratore per il blocco dei numeri vengono forniti solo con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad31c-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="ad31c-114">I modelli di blocco numerico sono definiti come modelli di espressione regolari.</span><span class="sxs-lookup"><span data-stu-id="ad31c-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="ad31c-115">L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco restituisce la chiamata bloccata.</span><span class="sxs-lookup"><span data-stu-id="ad31c-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="ad31c-116">Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore affinché il modello diventi attivo.</span><span class="sxs-lookup"><span data-stu-id="ad31c-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="ad31c-117">Chiamata che blocca i comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad31c-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="ad31c-118">I modelli di numero vengono gestiti ```CsInboundBlockedNumberPattern``` tramite ```New```i ```Get```comandi ```Set```,, ```Remove```e.</span><span class="sxs-lookup"><span data-stu-id="ad31c-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="ad31c-119">Puoi gestire un modello specifico usando questi cmdlet, inclusa la possibilità di attivare o disattivare l'attivazione di un modello specifico.</span><span class="sxs-lookup"><span data-stu-id="ad31c-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="ad31c-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco del tenant, inclusi nome, descrizione, Enabled (vero/falso) e pattern for each.</span><span class="sxs-lookup"><span data-stu-id="ad31c-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="ad31c-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge un modello di numero bloccato all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="ad31c-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove un modello di numero bloccato dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="ad31c-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di un modello di numero bloccato nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="ad31c-124">La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate ```CsTenantBlockingCallingNumbers``` viene ```Get``` gestita ```Set```tramite i comandi e.</span><span class="sxs-lookup"><span data-stu-id="ad31c-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="ad31c-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco numero bloccati globale, incluso Enabled (vero/falso).</span><span class="sxs-lookup"><span data-stu-id="ad31c-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="ad31c-126">Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ad31c-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="ad31c-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare il tenant globale le chiamate bloccate per essere attivate e disattivate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="ad31c-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="ad31c-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="ad31c-129">Bloccare un numero</span><span class="sxs-lookup"><span data-stu-id="ad31c-129">Block a number</span></span>

<span data-ttu-id="ad31c-130">In questo esempio i ```-Enabled``` parametri e ```-Description``` sono facoltativi:</span><span class="sxs-lookup"><span data-stu-id="ad31c-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="ad31c-131">La creazione di un nuovo modello aggiunge il modello come abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ad31c-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="ad31c-132">La descrizione è un campo facoltativo per ottenere altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="ad31c-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="ad31c-133">Ti consigliamo di specificare un nome significativo per capire facilmente il motivo per cui è stato aggiunto il pattern.</span><span class="sxs-lookup"><span data-stu-id="ad31c-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="ad31c-134">In caso di bloccare semplicemente i numeri di posta indesiderata, considera la regola come il modello di numero corrispondente e Aggiungi altre informazioni nella descrizione, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="ad31c-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="ad31c-135">I modelli vengono combinati usando le espressioni regolari (Regex).</span><span class="sxs-lookup"><span data-stu-id="ad31c-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="ad31c-136">Consentire il tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="ad31c-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="ad31c-137">Consentire un numero</span><span class="sxs-lookup"><span data-stu-id="ad31c-137">Allow a number</span></span>

<span data-ttu-id="ad31c-138">In questo esempio il ```-Identity``` parametro è obbligatorio:</span><span class="sxs-lookup"><span data-stu-id="ad31c-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="ad31c-139">Se l'identità non è nota, usare ```Get-CsInboundBlockedNumberPattern``` il cmdlet per individuare prima il modello appropriato e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="ad31c-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ad31c-140">Esegui quindi il ```Remove-CsTenantBlockedNumberPattern``` cmdlet e passa il valore di identità appropriato.</span><span class="sxs-lookup"><span data-stu-id="ad31c-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="ad31c-141">Consentire il tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="ad31c-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="ad31c-142">Visualizzare tutti i modelli di numeri</span><span class="sxs-lookup"><span data-stu-id="ad31c-142">View all number patterns</span></span>

<span data-ttu-id="ad31c-143">L'uso di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:</span><span class="sxs-lookup"><span data-stu-id="ad31c-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="ad31c-144">Usare le funzionalità di filtro di PowerShell predefinite per analizzare i valori restituiti come richiesto.</span><span class="sxs-lookup"><span data-stu-id="ad31c-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="ad31c-145">Aggiungere eccezioni per i numeri</span><span class="sxs-lookup"><span data-stu-id="ad31c-145">Add number exceptions</span></span>

<span data-ttu-id="ad31c-146">È possibile aggiungere eccezioni ai modelli di numero bloccati tramite ```CsTenantBlockNumberExceptionPattern``` i comandi ```New```, ```Get``` ```Set```,, e ```Remove```.</span><span class="sxs-lookup"><span data-stu-id="ad31c-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="ad31c-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) aggiunge un modello di eccezione numero all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="ad31c-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) restituisce un elenco di tutti i modelli di eccezione Number aggiunti all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="ad31c-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o più parametri in un modello di eccezione Number nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="ad31c-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove un modello di eccezione Number dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="ad31c-151">Esempi</span><span class="sxs-lookup"><span data-stu-id="ad31c-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="ad31c-152">Aggiungere un'eccezione Number</span><span class="sxs-lookup"><span data-stu-id="ad31c-152">Add a number exception</span></span>

<span data-ttu-id="ad31c-153">In questo esempio viene creato un nuovo modello di eccezione Number e per impostazione predefinita verrà aggiunto il modello come abilitato.</span><span class="sxs-lookup"><span data-stu-id="ad31c-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="ad31c-154">I ```-Enabled``` parametri ```-Description``` e sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="ad31c-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="ad31c-155">Visualizzare tutte le eccezioni numeriche</span><span class="sxs-lookup"><span data-stu-id="ad31c-155">View all number exceptions</span></span>

<span data-ttu-id="ad31c-156">In questo esempio, il parametro-Identity è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad31c-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="ad31c-157">Se il ```-Identity``` parametro non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione Number immessi per un tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="ad31c-158">Modificare un'eccezione numero</span><span class="sxs-lookup"><span data-stu-id="ad31c-158">Modify a number exception</span></span>

<span data-ttu-id="ad31c-159">In questo esempio, il parametro-Identity è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad31c-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="ad31c-160">Il ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet consente di modificare uno o più parametri per una determinata identità del pattern numerico.</span><span class="sxs-lookup"><span data-stu-id="ad31c-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="ad31c-161">Rimuovere un'eccezione numero</span><span class="sxs-lookup"><span data-stu-id="ad31c-161">Remove a number exception</span></span>

<span data-ttu-id="ad31c-162">In questo esempio il ```-Identity``` parametro è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad31c-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="ad31c-163">Questo cmdlet rimuoverà il modello di numero assegnato dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="ad31c-164">Se l'identità non è nota, usare ```Get-CsInboundBlockedNumberPattern``` il cmdlet per individuare prima il modello appropriato e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="ad31c-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ad31c-165">Esegui quindi il ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet e passa il valore di identità appropriato.</span><span class="sxs-lookup"><span data-stu-id="ad31c-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="ad31c-166">Consentire il tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="ad31c-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="ad31c-167">Verificare se un numero è bloccato</span><span class="sxs-lookup"><span data-stu-id="ad31c-167">Test whether a number is blocked</span></span>

<span data-ttu-id="ad31c-168">Usa il ```Test-CsInboundBlockedNumberPattern``` cmdlet per verificare se un numero è bloccato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="ad31c-169">In questo esempio sono necessari ```-Phonenumber``` i ```-Tenant``` parametri e.</span><span class="sxs-lookup"><span data-stu-id="ad31c-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="ad31c-170">Il ```-PhoneNumber``` parametro deve essere una stringa numerica senza altri caratteri, ad esempio + o-.</span><span class="sxs-lookup"><span data-stu-id="ad31c-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="ad31c-171">In TRP l' ```-Tenant parameter``` opzione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ad31c-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="ad31c-172">Il parametro ```isNumberBlocked``` risultante restituisce il valore true se il numero è bloccato nel tenant e false se non è bloccato.</span><span class="sxs-lookup"><span data-stu-id="ad31c-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="ad31c-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="ad31c-173">httpResponseCode</span></span>  |<span data-ttu-id="ad31c-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="ad31c-174">isNumberBlocked</span></span>   |<span data-ttu-id="ad31c-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="ad31c-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ad31c-176">200</span><span class="sxs-lookup"><span data-stu-id="ad31c-176">200</span></span>    | <span data-ttu-id="ad31c-177">True</span><span class="sxs-lookup"><span data-stu-id="ad31c-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="ad31c-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="ad31c-178">httpResponseCode</span></span>  |<span data-ttu-id="ad31c-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="ad31c-179">isNumberBlocked</span></span>   |<span data-ttu-id="ad31c-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="ad31c-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ad31c-181">200</span><span class="sxs-lookup"><span data-stu-id="ad31c-181">200</span></span>    | <span data-ttu-id="ad31c-182">False</span><span class="sxs-lookup"><span data-stu-id="ad31c-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="ad31c-183">Nota su Regex</span><span class="sxs-lookup"><span data-stu-id="ad31c-183">A note about Regex</span></span>

<span data-ttu-id="ad31c-184">Come indicato in precedenza, il criterio di corrispondenza per il blocco dei chiamanti viene eseguito usando Regex.</span><span class="sxs-lookup"><span data-stu-id="ad31c-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="ad31c-185">Sono disponibili più strumenti online per convalidare una corrispondenza di pattern Regex.</span><span class="sxs-lookup"><span data-stu-id="ad31c-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="ad31c-186">Se non si ha familiarità con i modelli Regex, è consigliabile richiedere un po' di tempo per familiarizzare con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="ad31c-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="ad31c-187">Per assicurarsi di ottenere i risultati previsti, usare uno strumento per la convalida delle corrispondenze di pattern prima di aggiungere nuove corrispondenze di numeri bloccati al tenant.</span><span class="sxs-lookup"><span data-stu-id="ad31c-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ad31c-188">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ad31c-188">Related topics</span></span>

- [<span data-ttu-id="ad31c-189">Configurare il computer per la gestione di Skype for business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad31c-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
