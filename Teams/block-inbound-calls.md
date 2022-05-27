---
title: Bloccare le chiamate in ingresso in Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
ms.custom: ''
description: Informazioni su come usare PowerShell per gestire il blocco delle chiamate in ingresso.
ms.openlocfilehash: 25b271cbcf62acd732463e9dd34d4189479d2417
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674388"
---
# <a name="block-inbound-calls"></a>Bloccare le chiamate in ingresso

Piani per chiamate Microsoft, Routing diretto e Connessione con operatore supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network). Questa caratteristica consente all'amministratore di definire un elenco di modelli numerici a livello globale tenant in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere confrontato con l'elenco per individuare una corrispondenza. Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.

Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso provenienti dalla rete PSTN e funziona solo a livello globale tenant. I singoli utenti Teams non possono manipolare questo elenco. Il client Teams consente ai singoli utenti di bloccare le chiamate PSTN. Per informazioni su come gli utenti finali possono implementare il blocco delle chiamate, vedere [Gestire le impostazioni delle chiamate in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

> [!NOTE]
> I chiamanti bloccati possono riscontrare comportamenti leggermente diversi quando sono stati bloccati. Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non può essere completata correttamente. Alcuni esempi possono includere un messaggio del corriere che indica che la chiamata non può essere completata come chiamata effettuata o semplicemente che è stata annullata.

## <a name="call-blocking-admin-controls-and-information"></a>Controlli e informazioni per il blocco delle chiamate

Amministrazione controlli per il blocco dei numeri vengono forniti solo con PowerShell. I modelli di blocchi numerici vengono definiti come criteri di espressione regolare. L'ordine delle espressioni non è importante: il primo criterio di corrispondenza nell'elenco determina il blocco della chiamata. Un nuovo numero o criterio aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore perché il modello diventi attivo.

## <a name="call-blocking-powershell-commands"></a>Comandi di PowerShell che bloccano le chiamate

Puoi gestire i modelli numerici utilizzando i cmdlet **New-**, **Get-**, **Set-**, e **Remove-CsInboundBlockedNumberPattern** . È possibile gestire un determinato modello usando questi cmdlet, inclusa la possibilità di attivare o disattivare l'attivazione di un determinato criterio.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numeri bloccati aggiunti all'elenco tenant, inclusi Nome, Descrizione, Abilitato (Vero/Falso) e Pattern per ciascuno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge un modello di numero bloccato all'elenco tenant.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove un modello di numero bloccato dall'elenco tenant.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di un modello di numero bloccato nell'elenco dei tenant.

La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate viene gestita tramite i cmdlet **Get-** e **Set-CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i modelli di numeri di blocco in ingresso e i parametri dei modelli di numeri esenti in ingresso per l'elenco di numeri bloccati globali. Questo cmdlet restituisce anche un valore che indica se il blocco è stato abilitato (True o False). Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la funzionalità.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale da attivare e disattivare a livello di tenant.

### <a name="examples"></a>Esempi

#### <a name="block-a-number"></a>Bloccare un numero

Nell'esempio seguente l'amministratore del tenant vuole bloccare tutte le chiamate provenienti dal numero compreso tra 1 (312) 555-0000 e 1 (312) 555-9999. Il criterio numerico viene creato in modo che sia i numeri nell'intervallo con il prefisso + che i numeri nell'intervallo senza prefisso + vengano confrontati. Non è necessario includere i simboli e () nei numeri di telefono perché il sistema rimuove questi simboli prima della corrispondenza.  Per attivare il criterio numerico, il parametro **Enabled** è impostato su True. Per disabilitare questo criterio numerico specifico, impostare il parametro su False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

Nell'esempio successivo, l'amministratore del tenant vuole bloccare tutte le chiamate provenienti dal numero 1 (412) 555-1234. Per attivare il criterio numerico, il parametro **Enabled** è impostato su True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

La creazione di un nuovo criterio aggiunge il criterio come abilitato per impostazione predefinita. La descrizione è un campo facoltativo per fornire altre informazioni.

È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui il modello è stato aggiunto. Nel caso in cui si blocchino semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso criterio numerico con cui viene trovata una corrispondenza e aggiungere altre informazioni nella descrizione in base alle esigenze.

I modelli vengono confrontati con espressioni regolari (Regex). Per ulteriori informazioni, vedere [Uso di Regex](#using-regex).

Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="allow-a-number"></a>Consenti un numero

È possibile consentire la chiamata a un numero rimuovendo il modello di numero bloccato. Nell'esempio seguente l'amministratore del tenant vuole consentire a 1 (412) 555-1234 di effettuare nuovamente le chiamate.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

Se l'identità non è nota, utilizza il cmdlet **Get-CsInboundBlockedNumberPattern** per individuare prima il modello corretto e prendere nota dell'identità. Quindi, esegui il cmdlet **Remove-CsInboundBlockedNumberPattern** e passa il valore di identità appropriato.

Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli numerici

L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Usare le funzionalità di filtro predefinite di PowerShell per analizzare i valori restituiti in base alle esigenze.

## <a name="add-number-exceptions"></a>Aggiungere eccezioni ai numeri

Puoi aggiungere eccezioni ai modelli di numeri bloccati utilizzando i cmdlet **New-**, **Get-**, **Set-**, e **Remove-CsInboundExemptNumberPattern** .

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) aggiunge un modello di eccezione numero all'elenco tenant.
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) restituisce un elenco di tutti i modelli di eccezione numero aggiunti all'elenco tenant.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica uno o più parametri in un modello di eccezione numero nell'elenco tenant.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) rimuove un modello di eccezione numero dall'elenco tenant.

### <a name="examples"></a>Esempi

#### <a name="add-a-number-exception"></a>Aggiungere un'eccezione numero

Nell'esempio seguente l'amministratore del tenant vuole consentire ai numeri di telefono 1 (312) 555-8882 e 1 (312) 555-8883 di effettuare chiamate al tenant, anche se questi due numeri di telefono si trovano nell'intervallo bloccato nell'esempio precedente. Per abilitarlo, viene creato un nuovo criterio di eccezione numero nel modo seguente:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Per attivare il criterio numerico, il parametro **Enabled** è impostato su True. Per disabilitare questo criterio numerico specifico, impostare il parametro su False.

#### <a name="view-all-number-exceptions"></a>Visualizzare tutte le eccezioni numeri

In questo esempio il parametro **Identity** è facoltativo. Se il parametro **Identity** non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione dei numeri immessi per un tenant.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>Modificare un'eccezione numero

Il cmdlet **Set-CsInboundExemptNumberPattern** consente di modificare uno o più parametri per una determinata identità di pattern numerico. In questo esempio il parametro **Identity** è obbligatorio.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Rimuovere un'eccezione numero

Il cmdlet **Remove-CsInboundExemptNumberPattern** rimuoverà il modello di numero specificato dall'elenco tenant. In questo esempio il parametro **Identity** è obbligatorio.

Se l'identità non è nota, utilizza il cmdlet **Get-CsInboundExemptNumberPattern** per individuare prima il modello corretto e prendere nota dell'identità. Quindi, esegui il cmdlet **Remove-CsInboundExemptNumberPattern** e passa il valore di identità appropriato. Consentire il tempo per la replica prima di testare e convalidare.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Verificare se un numero è bloccato

Utilizza il cmdlet **Test-CsInboundBlockedNumberPattern** per verificare se un numero è bloccato nel tenant.

Il parametro **PhoneNumber** è obbligatorio e deve essere una stringa numerica senza altri caratteri, ad esempio +, - o (). Il parametro **IsNumberBlocked** risultante restituisce il valore True se il numero è bloccato nel tenant; il parametro restituisce False se non è bloccato.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Esempi

In questi esempi puoi vedere che il numero di telefono 1 (312) 555-8884 è bloccato come dovrebbe essere a causa di essere nell'intervallo bloccato sopra, mentre il numero di telefono 1 (312) 555-8883 è autorizzato a chiamare come dovrebbe essere basato sull'esenzione creata sopra.

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

La corrispondenza dei criteri per il blocco dei chiamanti viene eseguita con Regex. Sono disponibili più strumenti online per convalidare una corrispondenza del modello Regex. Se non si ha familiarità con i modelli Regex, è consigliabile dedicare del tempo per acquisire familiarità con le nozioni di base. Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze ai numeri bloccati al tenant.
