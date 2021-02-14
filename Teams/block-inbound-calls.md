---
title: Bloccare le chiamate in entrata in Microsoft Teams
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
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799906"
---
# <a name="block-inbound-calls"></a>Bloccare le chiamate in entrata

L'instradamento diretto e i piani per chiamate del sistema telefonico supportano il blocco delle chiamate in entrata dalla rete PSTN (Public Switched Telephone Network). Questa caratteristica consente di definire un elenco globale tenant di modelli di numerazione in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere controllato rispetto all'elenco per trovare una corrispondenza. Se viene trovata una corrispondenza, una chiamata in arrivo viene rifiutata.

Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso provenienti dalla rete PSTN e funziona solo su base tenant-globale. Non è disponibile per utente.  

>[!NOTE]
> I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati. Il comportamento dipende dal modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non è consentita per il completamento. Ad esempio, è possibile includere un messaggio del gestore che indica che la chiamata non può essere completata come chiamata o semplicemente inviare la chiamata.

## <a name="call-blocking-admin-controls-and-information"></a>Controlli e informazioni di amministrazione del blocco delle chiamate

I controlli di amministrazione per il blocco dei numeri vengono forniti solo con PowerShell. I motivi dei blocchi numerici sono definiti come modelli di espressioni regolari. L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco comporta il blocco della chiamata. L'aggiunta o la rimozione di un nuovo numero nell'elenco di chiamanti bloccati può richiedere fino a 24 ore prima che il modello diventi attivo.

## <a name="call-blocking-powershell-commands"></a>Comandi di PowerShell per il blocco delle chiamate

È possibile gestire i modelli di numerazione usando i cmdlet **New**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberNumberNumber.** È possibile gestire un determinato criterio usando questi cmdlet, inclusa la possibilità di attivare o disattivare un determinato criterio.

- [Get-CsInboundBlockedNumberNumerazione Restituisce](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) un elenco di tutti i modelli di numerazione bloccati aggiunti all'elenco tenant, tra cui Nome, Descrizione, Abilitato (True/False) e Pattern per ogni elemento.
- [New-CsInboundBlockedNumberNumber Consente](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) di aggiungere uno schema di numero bloccato all'elenco tenant.
- [Remove-CsInboundBlockedNumberNumber Consente di](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) rimuovere uno schema di numero bloccato dall'elenco dei tenant.
- [Set-CsInboundBlockedNumberNumberNumber Modifies](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) one or more parameters of a blocked number pattern in the tenant list.

La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate vengono gestite tramite i cmdlet **Get,** **Set**  - **CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco dei numeri bloccati globali, tra cui Enabled (True/False). Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la caratteristica.
- [Set-CsTenantBlockedCallingNumbers consente](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) di modificare il tenant globale, le chiamate bloccate possono essere attivate e disattivate a livello di tenant.

### <a name="examples"></a>Esempi

#### <a name="block-a-number"></a>Bloccare un numero

In questo esempio i parametri **Abilitata** **e Descrizione** sono facoltativi.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creazione di un nuovo motivo lo aggiunge come abilitato per impostazione predefinita. La descrizione è un campo facoltativo per fornire altre informazioni.

È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui sono stati aggiunti i criteri. Nel caso di bloccare semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola un nome uguale al modello di numero corrispondente e aggiungere altre informazioni nella descrizione in base alle esigenze.

I criteri vengono trovati con espressioni regolari (Regex). Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="allow-a-number"></a>Consenti un numero

In questo esempio è **necessario il parametro Identity.**

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberNumberNumber Dopo** avere individuato il modello corretto e prendere nota dell'identità. Eseguire quindi il cmdlet **Remove-CsTenantBlockedNumberNumberNumber E** passare il valore di identità appropriato.

Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli di numerazione

L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Usare le funzionalità di filtro incorporate di PowerShell per analizzare i valori restituiti come necessario.

## <a name="add-number-exceptions"></a>Aggiungere eccezioni numeri

È possibile aggiungere eccezioni ai modelli di numero bloccati usando i cmdlet **New**, **Get**, **Set**, **Remove**  - **CsTenantBlockNumberExceptionExceptionNumber.**

- [New-CsTenantBlockedNumberExceptionNumber adds](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) a number exception pattern to the tenant list. 
- [Get-CsTenantBlockedNumberExceptionStradali restituisce](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) un elenco di tutti i modelli di eccezione numerica aggiunti all'elenco tenant.
- [Set-CsTenantBlockedNumberException Modifies](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) one or more parameters to a number exception pattern in the tenant list.
- [Remove-CsTenantBlockedNumberExceptionLoc](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove un modello di eccezione numerica dall'elenco tenant.

### <a name="examples"></a>Esempi

#### <a name="add-a-number-exception"></a>Aggiungere un'eccezione numerica

In questo esempio viene creato un nuovo modello di eccezione numerica che, per impostazione predefinita, lo aggiunge come abilitato. I **parametri Abilitata** **e Descrizione** sono facoltativi.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Visualizzare tutte le eccezioni numeri

In questo esempio il **parametro Identity** è facoltativo. Se il **parametro Identity** non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione numerica immessi per un tenant.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificare un'eccezione numerica

In questo esempio il **parametro Identity** è obbligatorio. Il cmdlet **Set-CsTenantBlockedNumberExceptionLoc** consente di modificare uno o più parametri per una determinata identità dei criteri di numero.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Rimuovere un'eccezione numerica

In questo esempio è **necessario il parametro Identity.** Questo cmdlet rimuove il criterio di numero specificato dall'elenco dei tenant.  Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberNumberNumber Dopo** avere individuato il modello corretto e prendere nota dell'identità. Eseguire quindi il cmdlet **Remove-CsTenantBlockedNumberExceptionLoc** e passare il valore di identità appropriato.Consentire il tempo per la replica prima di testare e convalidare.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Verificare se un numero è bloccato

Usare il **cmdlet Test-CsInboundBlockedNumberNumberNumber Per** verificare se un numero è bloccato nel tenant.
 
In questo esempio sono necessari **i parametri PhoneNumber** e **Tenant.** Il **parametro PhoneNumber** deve essere una stringa numerica senza altri caratteri, ad esempio + o -. In TRPS il **parametro Tenant è** facoltativo. Il parametro **isNumberBlocked** risultante restituisce un valore True se il numero è bloccato nel tenant e False se non è bloccato.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Vero        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Falso        |         |

## <a name="a-note-about-regex"></a>Nota sul regex

Come indicato in precedenza, i criteri di ricerca per il blocco dei chiamanti vengono esemperti tramite Regex. Sono disponibili più strumenti online per convalidare una corrispondenza con un criterio Regex. Se non si ha familiarità con i modelli Regex, è consigliabile acquisire familiarità con le nozioni di base. Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze ai criteri prima di aggiungere nuove corrispondenze a numeri bloccati nel tenant.
