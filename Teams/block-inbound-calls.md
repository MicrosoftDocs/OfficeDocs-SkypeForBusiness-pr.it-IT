---
title: Bloccare le chiamate in ingresso in Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094682"
---
# <a name="block-inbound-calls"></a>Bloccare le chiamate in ingresso

Sistema telefonico i piani di routing e chiamata diretti supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network). Questa caratteristica consente di definire un elenco globale tenant di pattern numerici in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere controllato rispetto all'elenco per una corrispondenza. Se viene eseguita una corrispondenza, viene rifiutata una chiamata in arrivo.

Questa funzionalità di blocco delle chiamate in ingresso funziona solo sulle chiamate in ingresso che provengono dalla rete PSTN e funziona solo su base globale del tenant. Non è disponibile per singoli utenti.  

>[!NOTE]
> I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati. Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non può essere completata correttamente. Gli esempi possono includere un messaggio portante che indica che la chiamata non può essere completata come chiamata o semplicemente eliminando la chiamata.

## <a name="call-blocking-admin-controls-and-information"></a>Chiamata che blocca i controlli e le informazioni dell'amministratore

I controlli di amministratore per il blocco dei numeri vengono forniti solo con PowerShell. I modelli di blocco numerico sono definiti come modelli di espressione regolari. L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco restituisce la chiamata bloccata. Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore affinché il modello diventi attivo.

## <a name="call-blocking-powershell-commands"></a>Chiamata che blocca i comandi di PowerShell

Puoi gestire i modelli di numero usando i cmdlet **nuovo**, **Ottieni**, **imposta**, **Rimuovi**  - **CsInboundBlockedNumberPattern** . Puoi gestire un modello specifico usando questi cmdlet, inclusa la possibilità di attivare o disattivare l'attivazione di un modello specifico.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco del tenant, inclusi nome, descrizione, Enabled (vero/falso) e pattern for each.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge un modello di numero bloccato all'elenco tenant.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove un modello di numero bloccato dall'elenco tenant.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di un modello di numero bloccato nell'elenco tenant.

La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate viene gestita tramite i cmdlet **Get**, **set**  - **CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco numero bloccati globale, incluso Enabled (vero/falso). Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la funzionalità.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare il tenant globale le chiamate bloccate per essere attivate e disattivate a livello di tenant.

### <a name="examples"></a>Esempi

#### <a name="block-a-number"></a>Bloccare un numero

In questo esempio i parametri **Enabled** e **Description** sono facoltativi.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creazione di un nuovo modello aggiunge il modello come abilitato per impostazione predefinita. La descrizione è un campo facoltativo per ottenere altre informazioni.

Ti consigliamo di specificare un nome significativo per capire facilmente il motivo per cui è stato aggiunto il pattern. In caso di bloccare semplicemente i numeri di posta indesiderata, considera la regola come il modello di numero corrispondente e Aggiungi altre informazioni nella descrizione, come richiesto.

I modelli vengono combinati usando le espressioni regolari (Regex). Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="allow-a-number"></a>Consentire un numero

In questo esempio, il parametro **Identity** è obbligatorio.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima di tutto il modello appropriato e prendere nota dell'identità. Esegui quindi il cmdlet **Remove-CsTenantBlockedNumberPattern** e passa il valore di identità appropriato.

Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli di numeri

L'uso di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Usare le funzionalità di filtro di PowerShell predefinite per analizzare i valori restituiti come richiesto.

## <a name="add-number-exceptions"></a>Aggiungere eccezioni per i numeri

È possibile aggiungere eccezioni ai modelli di numero bloccati usando i cmdlet **nuovo**, **Ottieni**, **imposta**, **Rimuovi**  - **CsTenantBlockNumberExceptionPattern** .

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) aggiunge un modello di eccezione numero all'elenco tenant. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) restituisce un elenco di tutti i modelli di eccezione Number aggiunti all'elenco tenant.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o più parametri in un modello di eccezione Number nell'elenco tenant.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove un modello di eccezione Number dall'elenco tenant.

### <a name="examples"></a>Esempi

#### <a name="add-a-number-exception"></a>Aggiungere un'eccezione Number

In questo esempio viene creato un nuovo modello di eccezione Number e per impostazione predefinita verrà aggiunto il modello come abilitato. I parametri **Enabled** e **Description** sono facoltativi.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Visualizzare tutte le eccezioni numeriche

In questo esempio, il parametro **Identity** è facoltativo. Se il parametro **Identity** non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione Number immessi per un tenant.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificare un'eccezione numero

In questo esempio, il parametro **Identity** è obbligatorio. Il cmdlet **set-CsTenantBlockedNumberExceptionPattern** consente di modificare uno o più parametri per una determinata identità del pattern di numeri.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Rimuovere un'eccezione numero

In questo esempio, il parametro **Identity** è obbligatorio. Questo cmdlet rimuoverà il modello di numero assegnato dall'elenco tenant.  Se l'identità non è nota, usare il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima di tutto il modello appropriato e prendere nota dell'identità. Esegui quindi il cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** e passa il valore di identità appropriato.Consentire il tempo per la replica prima di testare e convalidare.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Verificare se un numero è bloccato

Usa il cmdlet **test-CsInboundBlockedNumberPattern** per verificare se un numero è bloccato nel tenant.
 
In questo esempio sono necessari i parametri **PhoneNumber** e **tenant** . Il parametro **PhoneNumber** deve essere una stringa numerica senza altri caratteri, ad esempio + o-. In TRP il **parametro tenant** è facoltativo. Il parametro **isNumberBlocked** risultante restituisce il valore true se il numero è bloccato nel tenant e false se non è bloccato.

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

## <a name="a-note-about-regex"></a>Nota su Regex

Come indicato in precedenza, il criterio di corrispondenza per il blocco dei chiamanti viene eseguito usando Regex. Sono disponibili più strumenti online per convalidare una corrispondenza di pattern Regex. Se non si ha familiarità con i modelli Regex, è consigliabile richiedere un po' di tempo per familiarizzare con le nozioni di base. Per assicurarsi di ottenere i risultati previsti, usare uno strumento per la convalida delle corrispondenze di pattern prima di aggiungere nuove corrispondenze di numeri bloccati al tenant.
