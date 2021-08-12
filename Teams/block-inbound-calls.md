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
ms.openlocfilehash: 971235754c88d082a43c152867dee9d1b60d0da9adfb1fda9659c53aec71b829
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295213"
---
# <a name="block-inbound-calls"></a>Bloccare le chiamate in ingresso

Piani per chiamate Microsoft, routing diretto e Connessione con operatore supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network). Questa caratteristica consente a un amministratore di definire un elenco di schemi numerici a livello globale del tenant in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere verificato in base all'elenco per trovare una corrispondenza. Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.

Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso che provengono dalla rete PSTN e funzionano solo a livello globale del tenant. I singoli Teams utenti non possono modificare l'elenco. Il client Teams consente ai singoli utenti di bloccare le chiamate PSTN. Per informazioni su come gli utenti finali possono implementare il blocco delle chiamate, vedere [Gestire le impostazioni delle chiamate in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

>[!NOTE]
> I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati. Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non è consentita per il completamento. Alcuni esempi possono includere un messaggio dell'operatore che indica che la chiamata non può essere completata come chiamata o semplicemente la chiamata.

## <a name="call-blocking-admin-controls-and-information"></a>Informazioni e controlli di amministrazione del blocco delle chiamate

I controlli di amministrazione per i numeri di blocco vengono forniti solo tramite PowerShell. I criteri dei blocchi numerici sono definiti come criteri di espressione regolare. L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco causa il blocco della chiamata. Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore prima che il criterio diventi attivo.

## <a name="call-blocking-powershell-commands"></a>Comandi di PowerShell per il blocco delle chiamate

Per gestire i modelli numerici, usare i cmdlet **New-**, **Get-**, **Set-** e **Remove-CsInboundBlockedNumberPattern.** È possibile gestire un determinato criterio usando questi cmdlet, inclusa la possibilità di attivare o disattivare un determinato criterio.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco tenant, tra cui Name, Description, Enabled (True/False) e Pattern per ognuno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge uno schema di numeri bloccati all'elenco tenant.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove uno schema di numeri bloccati dall'elenco tenant.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di uno schema di numeri bloccati nell'elenco tenant.

La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate vengono gestite tramite i cmdlet **Get-** e **Set-CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i modelli di numero di blocco in ingresso e i parametri dei modelli di numeri esenti in ingresso per l'elenco globale dei numeri bloccati. Questo cmdlet restituisce anche se il blocco è stato abilitato (True o False). Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la caratteristica.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale per essere attivate e disattivate a livello di tenant.

### <a name="examples"></a>Esempi

#### <a name="block-a-number"></a>Bloccare un numero

Nell'esempio seguente l'amministratore tenant vuole bloccare tutte le chiamate provenienti dall'intervallo di numeri 1 (312) da 555-0000 a 1 (312) 555-9999. Lo schema dei numeri viene creato in modo che sia i numeri nell'intervallo con + preceduti che i numeri nell'intervallo senza + prefissi corrispondano. Non è necessario includere i simboli e () nei numeri di telefono perché il sistema rimuove questi simboli prima della corrispondenza.  Per attivare lo schema dei numeri, il **parametro Enabled** è impostato su True. Per disabilitare questo modello di numero specifico, impostare il parametro su False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

Nell'esempio successivo, l'amministratore tenant vuole bloccare tutte le chiamate provenienti dal numero 1 (412) 555-1234. Per attivare lo schema dei numeri, il **parametro Enabled** è impostato su True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

La creazione di un nuovo criterio aggiunge il motivo come abilitato per impostazione predefinita. La descrizione è un campo facoltativo per fornire altre informazioni.

È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui è stato aggiunto il criterio. Nel caso di bloccare semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso modello di numero corrispondente e aggiungere altre informazioni nella descrizione in base alle esigenze.

I criteri vengono abbinati usando espressioni regolari (Regex). Per altre informazioni, vedere [Uso di Regex.](#using-regex)

Concedere tempo per la replica prima di testare e convalidare. 

#### <a name="allow-a-number"></a>Consenti un numero

È possibile consentire la chiamata di un numero rimuovendo lo schema di numeri bloccati. Nell'esempio seguente l'amministratore tenant vuole consentire a 1 (412) 555-1234 di effettuare di nuovo le chiamate.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima il criterio appropriato e prendere nota dell'identità. Eseguire quindi il cmdlet **Remove-CsInboundBlockedNumberPattern** e passare il valore identity appropriato.

Concedere tempo per la replica prima di testare e convalidare.

#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli numerici

L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Usare le funzionalità di filtro incorporate di PowerShell per analizzare i valori restituiti in base alle esigenze.

## <a name="add-number-exceptions"></a>Aggiungere eccezioni numeri

È possibile aggiungere eccezioni ai modelli di numero bloccati usando i cmdlet **New-**, **Get-**, **Set-** e **Remove-CsInboundExemptNumberPattern.**

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) aggiunge un modello di eccezione numerica all'elenco tenant. 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) restituisce un elenco di tutti i modelli di eccezione numerica aggiunti all'elenco tenant.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica uno o più parametri in un modello di eccezione numerica nell'elenco tenant.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) rimuove uno schema di eccezione numerica dall'elenco tenant.

### <a name="examples"></a>Esempi

#### <a name="add-a-number-exception"></a>Aggiungere un'eccezione numerica

Nell'esempio seguente l'amministratore del tenant vuole consentire ai numeri di telefono 1 (312) 555-8882 e 1 (312) 555-8883 di effettuare chiamate al tenant, anche se questi due numeri di telefono sono nell'intervallo bloccato nell'esempio precedente. Per abilitare questa funzionalità, viene creato un nuovo modello di eccezione numerica nel modo seguente:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Per attivare lo schema dei numeri, il **parametro Enabled** è impostato su True. Per disabilitare questo modello di numero specifico, impostare il parametro su False.


#### <a name="view-all-number-exceptions"></a>Visualizzare tutte le eccezioni numeri

In questo esempio il parametro **Identity** è facoltativo. Se il **parametro Identity** non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione numerica immessi per un tenant.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>Modificare un'eccezione numerica

Il cmdlet **Set-CsInboundExemptNumberPattern** consente di modificare uno o più parametri per una determinata identità dello schema di numeri. In questo esempio il **parametro Identity** è obbligatorio.
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Rimuovere un'eccezione numerica

Il cmdlet **Remove-CsInboundExemptNumberPattern** rimuove il modello di numero specificato dall'elenco tenant. In questo esempio il **parametro Identity** è obbligatorio. 

Se l'identità non è nota, usare il cmdlet **Get-CsInboundExemptNumberPattern** per individuare prima il criterio appropriato e prendere nota dell'identità. Eseguire quindi il cmdlet **Remove-CsInboundExemptNumberPattern** e passare il valore identity appropriato.Concedere tempo per la replica prima di testare e convalidare.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Verificare se un numero è bloccato

Usare il cmdlet **Test-CsInboundBlockedNumberPattern** per verificare se un numero è bloccato nel tenant.
 
Il **parametro PhoneNumber** è obbligatorio e deve essere una stringa numerica senza altri caratteri, ad esempio +, - o (). Il parametro **IsNumberBlocked** risultante restituisce il valore True se il numero è bloccato nel tenant. il parametro restituisce False se non è bloccato.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Esempi

In questi esempi si può vedere che il numero di telefono 1 (312) 555-8884 è bloccato perché dovrebbe essere nell'intervallo bloccato sopra, mentre il numero di telefono 1 (312) 555-8883 è autorizzato a chiamare come dovrebbe essere basato sull'esenzione creata in precedenza.

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

## <a name="using-regex"></a>Uso di Regex

La corrispondenza dei criteri per bloccare i chiamanti viene eseguita usando Regex. Sono disponibili più strumenti online per convalidare una corrispondenza dei criteri Regex. Se non si ha familiarità con i modelli Regex, è consigliabile acquisire familiarità con le nozioni di base. Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze di numeri bloccati al tenant.