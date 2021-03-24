---
title: Bloccare le chiamate in ingresso in Microsoft Teams
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
ms.openlocfilehash: fcf50f96f352cfb72ff3bd700f2118c3cda51dd7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092864"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="a96ec-102">Bloccare le chiamate in ingresso</span><span class="sxs-lookup"><span data-stu-id="a96ec-102">Block inbound calls</span></span>

<span data-ttu-id="a96ec-103">I piani di routing diretto e chiamate del sistema telefonico supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="a96ec-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a96ec-104">Questa caratteristica consente di definire un elenco globale tenant di schemi numerici in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere verificato rispetto all'elenco per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="a96ec-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="a96ec-105">Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.</span><span class="sxs-lookup"><span data-stu-id="a96ec-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="a96ec-106">Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso provenienti dalla rete PSTN e funziona solo su base tenant-globale.</span><span class="sxs-lookup"><span data-stu-id="a96ec-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="a96ec-107">Non è disponibile per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="a96ec-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="a96ec-108">I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati.</span><span class="sxs-lookup"><span data-stu-id="a96ec-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="a96ec-109">Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non è consentita per il completamento.</span><span class="sxs-lookup"><span data-stu-id="a96ec-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="a96ec-110">Alcuni esempi possono includere un messaggio dell'operatore che indica che la chiamata non può essere completata come chiamata o semplicemente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a96ec-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="a96ec-111">Informazioni e controlli di amministrazione del blocco delle chiamate</span><span class="sxs-lookup"><span data-stu-id="a96ec-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="a96ec-112">I controlli di amministrazione per i numeri di blocco vengono forniti solo tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a96ec-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="a96ec-113">I criteri dei blocchi numerici sono definiti come criteri di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="a96ec-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="a96ec-114">L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco causa il blocco della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a96ec-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="a96ec-115">Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore prima che il criterio diventi attivo.</span><span class="sxs-lookup"><span data-stu-id="a96ec-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="a96ec-116">Comandi di PowerShell per il blocco delle chiamate</span><span class="sxs-lookup"><span data-stu-id="a96ec-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="a96ec-117">Per gestire i modelli numerici, usare i cmdlet **New**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="a96ec-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="a96ec-118">È possibile gestire un determinato criterio usando questi cmdlet, inclusa la possibilità di attivare o disattivare un determinato criterio.</span><span class="sxs-lookup"><span data-stu-id="a96ec-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="a96ec-119">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco tenant, tra cui Name, Description, Enabled (True/False) e Pattern per ognuno.</span><span class="sxs-lookup"><span data-stu-id="a96ec-119">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="a96ec-120">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge uno schema di numeri bloccati all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-120">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="a96ec-121">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove uno schema di numeri bloccati dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-121">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="a96ec-122">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di uno schema di numeri bloccati nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-122">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="a96ec-123">La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate vengono gestite tramite i cmdlet **Get**, **Set**  - **CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="a96ec-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="a96ec-124">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco globale dei numeri bloccati, tra cui Enabled (True/False).</span><span class="sxs-lookup"><span data-stu-id="a96ec-124">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="a96ec-125">Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la caratteristica.</span><span class="sxs-lookup"><span data-stu-id="a96ec-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="a96ec-126">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale per essere attivate e disattivate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-126">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="a96ec-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="a96ec-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="a96ec-128">Bloccare un numero</span><span class="sxs-lookup"><span data-stu-id="a96ec-128">Block a number</span></span>

<span data-ttu-id="a96ec-129">In questo esempio i parametri **Abilitato e** **Descrizione** sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a96ec-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="a96ec-130">La creazione di un nuovo criterio aggiunge il motivo come abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a96ec-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="a96ec-131">La descrizione è un campo facoltativo per fornire altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="a96ec-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="a96ec-132">È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui è stato aggiunto il criterio.</span><span class="sxs-lookup"><span data-stu-id="a96ec-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="a96ec-133">Nel caso di bloccare semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso modello di numero corrispondente e aggiungere altre informazioni nella descrizione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a96ec-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="a96ec-134">I criteri vengono abbinati usando espressioni regolari (Regex).</span><span class="sxs-lookup"><span data-stu-id="a96ec-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="a96ec-135">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="a96ec-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="a96ec-136">Consenti un numero</span><span class="sxs-lookup"><span data-stu-id="a96ec-136">Allow a number</span></span>

<span data-ttu-id="a96ec-137">In questo esempio il **parametro Identity** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a96ec-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="a96ec-138">Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima il criterio appropriato e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="a96ec-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="a96ec-139">Eseguire quindi il cmdlet **Remove-CsTenantBlockedNumberPattern** e passare il valore identity appropriato.</span><span class="sxs-lookup"><span data-stu-id="a96ec-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="a96ec-140">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="a96ec-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="a96ec-141">Visualizzare tutti i modelli numerici</span><span class="sxs-lookup"><span data-stu-id="a96ec-141">View all number patterns</span></span>

<span data-ttu-id="a96ec-142">L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:</span><span class="sxs-lookup"><span data-stu-id="a96ec-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="a96ec-143">Usare le funzionalità di filtro incorporate di PowerShell per analizzare i valori restituiti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a96ec-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="a96ec-144">Aggiungere eccezioni numeri</span><span class="sxs-lookup"><span data-stu-id="a96ec-144">Add number exceptions</span></span>

<span data-ttu-id="a96ec-145">È possibile aggiungere eccezioni ai modelli di numero bloccati usando i cmdlet **New**, **Get**, **Set**, **Remove**  - **CsTenantBlockNumberExceptionPattern.**</span><span class="sxs-lookup"><span data-stu-id="a96ec-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="a96ec-146">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) aggiunge un modello di eccezione numerica all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-146">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="a96ec-147">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) restituisce un elenco di tutti i modelli di eccezione numerica aggiunti all'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-147">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="a96ec-148">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o più parametri in un modello di eccezione numerica nell'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-148">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="a96ec-149">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove uno schema di eccezione numerica dall'elenco tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-149">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="a96ec-150">Esempi</span><span class="sxs-lookup"><span data-stu-id="a96ec-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="a96ec-151">Aggiungere un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="a96ec-151">Add a number exception</span></span>

<span data-ttu-id="a96ec-152">In questo esempio viene creato un nuovo modello di eccezione numerica che, per impostazione predefinita, aggiunge il modello come abilitato.</span><span class="sxs-lookup"><span data-stu-id="a96ec-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="a96ec-153">I **parametri Abilitato** e **Descrizione** sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a96ec-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="a96ec-154">Visualizzare tutte le eccezioni numeri</span><span class="sxs-lookup"><span data-stu-id="a96ec-154">View all number exceptions</span></span>

<span data-ttu-id="a96ec-155">In questo esempio il parametro **Identity** è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a96ec-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="a96ec-156">Se il **parametro Identity** non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione numerica immessi per un tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="a96ec-157">Modificare un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="a96ec-157">Modify a number exception</span></span>

<span data-ttu-id="a96ec-158">In questo esempio il **parametro Identity** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a96ec-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="a96ec-159">Il cmdlet **Set-CsTenantBlockedNumberExceptionPattern** consente di modificare uno o più parametri per una determinata identità dello schema di numeri.</span><span class="sxs-lookup"><span data-stu-id="a96ec-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="a96ec-160">Rimuovere un'eccezione numerica</span><span class="sxs-lookup"><span data-stu-id="a96ec-160">Remove a number exception</span></span>

<span data-ttu-id="a96ec-161">In questo esempio il **parametro Identity** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a96ec-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="a96ec-162">Questo cmdlet rimuove il modello di numero specificato dall'elenco dei tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="a96ec-163">Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima il criterio appropriato e prendere nota dell'identità.</span><span class="sxs-lookup"><span data-stu-id="a96ec-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="a96ec-164">Eseguire quindi il cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** e passare il valore identity appropriato.</span><span class="sxs-lookup"><span data-stu-id="a96ec-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="a96ec-165">Concedere tempo per la replica prima di testare e convalidare.</span><span class="sxs-lookup"><span data-stu-id="a96ec-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="a96ec-166">Verificare se un numero è bloccato</span><span class="sxs-lookup"><span data-stu-id="a96ec-166">Test whether a number is blocked</span></span>

<span data-ttu-id="a96ec-167">Usare il cmdlet **Test-CsInboundBlockedNumberPattern** per verificare se un numero è bloccato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="a96ec-168">In questo esempio sono necessari **i parametri PhoneNumber** e **Tenant.**</span><span class="sxs-lookup"><span data-stu-id="a96ec-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="a96ec-169">Il **parametro PhoneNumber** deve essere una stringa numerica senza altri caratteri, ad esempio + o -.</span><span class="sxs-lookup"><span data-stu-id="a96ec-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="a96ec-170">In TRPS il parametro **Tenant è** facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a96ec-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="a96ec-171">Il parametro **isNumberBlocked** risultante restituisce il valore True se il numero è bloccato nel tenant e False se non è bloccato.</span><span class="sxs-lookup"><span data-stu-id="a96ec-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="a96ec-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="a96ec-172">httpResponseCode</span></span>  |<span data-ttu-id="a96ec-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="a96ec-173">isNumberBlocked</span></span>   |<span data-ttu-id="a96ec-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="a96ec-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a96ec-175">200</span><span class="sxs-lookup"><span data-stu-id="a96ec-175">200</span></span>    | <span data-ttu-id="a96ec-176">Vero</span><span class="sxs-lookup"><span data-stu-id="a96ec-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="a96ec-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="a96ec-177">httpResponseCode</span></span>  |<span data-ttu-id="a96ec-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="a96ec-178">isNumberBlocked</span></span>   |<span data-ttu-id="a96ec-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="a96ec-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a96ec-180">200</span><span class="sxs-lookup"><span data-stu-id="a96ec-180">200</span></span>    | <span data-ttu-id="a96ec-181">Falso</span><span class="sxs-lookup"><span data-stu-id="a96ec-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="a96ec-182">Nota su Regex</span><span class="sxs-lookup"><span data-stu-id="a96ec-182">A note about Regex</span></span>

<span data-ttu-id="a96ec-183">Come indicato in precedenza, la corrispondenza dei criteri per bloccare i chiamanti viene eseguita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="a96ec-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="a96ec-184">Sono disponibili più strumenti online per convalidare una corrispondenza dei criteri Regex.</span><span class="sxs-lookup"><span data-stu-id="a96ec-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="a96ec-185">Se non si ha familiarità con i modelli Regex, è consigliabile acquisire familiarità con le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="a96ec-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="a96ec-186">Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze di numeri bloccati al tenant.</span><span class="sxs-lookup"><span data-stu-id="a96ec-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>