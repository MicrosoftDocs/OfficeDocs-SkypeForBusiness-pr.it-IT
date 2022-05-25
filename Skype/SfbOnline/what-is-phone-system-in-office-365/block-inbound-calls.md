---
title: Bloccare le chiamate in ingresso in Skype for Business Online
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: Gli amministratori possono imparare a bloccare le chiamate in ingresso in Skype for Business Online.
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671652"
---
# <a name="block-inbound-calls"></a>Bloccare le chiamate in ingresso

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Piani per chiamate online ora supporta il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network). Questa caratteristica consente di definire un elenco globale tenant di modelli di numeri in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere confrontato con l'elenco per trovare una corrispondenza. Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.

Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso provenienti dalla rete PSTN e funziona solo su base tenant-globale. Non è disponibile per utente.

Questa funzionalità non è ancora disponibile per il routing diretto.

>[!NOTE]
> I chiamanti bloccati possono riscontrare comportamenti leggermente diversi quando sono stati bloccati. Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non può essere completata correttamente. Alcuni esempi possono includere un messaggio del corriere che indica che la chiamata non può essere completata come chiamata effettuata o semplicemente che è stata annullata.

## <a name="call-blocking-admin-controls-and-information"></a>Controlli e informazioni per il blocco delle chiamate

Amministrazione controlli per il blocco dei numeri vengono forniti solo con PowerShell. I modelli di blocchi numerici vengono definiti come criteri di espressione regolare. L'ordine delle espressioni non è importante: il primo criterio di corrispondenza nell'elenco determina il blocco della chiamata. Un nuovo numero o criterio aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore perché il modello diventi attivo.

## <a name="call-blocking-powershell-commands"></a>Comandi di PowerShell che bloccano le chiamate

I modelli numerici vengono gestiti tramite i ```CsInboundBlockedNumberPattern``` comandi ```New```, ```Get```, ```Set```e ```Remove```. È possibile gestire un determinato modello usando questi cmdlet, inclusa la possibilità di attivare o disattivare l'attivazione di un determinato criterio.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numeri bloccati aggiunti all'elenco tenant, inclusi Nome, Descrizione, Abilitato (Vero/Falso) e Pattern per ciascuno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge un modello di numero bloccato all'elenco tenant.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove un modello di numero bloccato dall'elenco tenant.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di un modello di numero bloccato nell'elenco dei tenant.

La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate viene gestita tramite i ```CsTenantBlockingCallingNumbers``` comandi ```Get``` e ```Set```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco di numeri bloccati globali, tra cui Enabled (True/False). Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la funzionalità.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale da attivare e disattivare a livello di tenant.

### <a name="examples"></a>Esempi

#### <a name="block-a-number"></a>Bloccare un numero

In questo esempio i ```-Enabled``` parametri e ```-Description``` sono facoltativi:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creazione di un nuovo criterio aggiunge il criterio come abilitato per impostazione predefinita. La descrizione è un campo facoltativo per fornire altre informazioni.

È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui il modello è stato aggiunto. Nel caso in cui si blocchino semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso criterio numerico con cui viene trovata una corrispondenza e aggiungere altre informazioni nella descrizione in base alle esigenze.

I modelli vengono confrontati con espressioni regolari (Regex).
Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="allow-a-number"></a>Consenti un numero

In questo esempio il ```-Identity``` parametro è obbligatorio:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

Se l'identità non è nota, usare il ```Get-CsInboundBlockedNumberPattern``` cmdlet per individuare prima lo schema corretto e prendere nota dell'identità. Quindi, eseguire il ```Remove-CsTenantBlockedNumberPattern``` cmdlet e passare il valore di identità appropriato.

Consentire il tempo per la replica prima di testare e convalidare.

#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli numerici

L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Usare le funzionalità di filtro predefinite di PowerShell per analizzare i valori restituiti in base alle esigenze.

## <a name="add-number-exceptions"></a>Aggiungere eccezioni ai numeri

È possibile aggiungere eccezioni ai modelli di numeri bloccati tramite i ```CsTenantBlockNumberExceptionPattern``` comandi, , ```New``````Get```, ```Set```e ```Remove```.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) aggiunge un modello di eccezione numero all'elenco tenant.
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) restituisce un elenco di tutti i modelli di eccezione numero aggiunti all'elenco tenant.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o più parametri in un criterio di eccezione numero nell'elenco tenant.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove un modello di eccezione numero dall'elenco tenant.

### <a name="examples"></a>Esempi

#### <a name="add-a-number-exception"></a>Aggiungere un'eccezione numero

In questo esempio viene creato un nuovo criterio di eccezione numero e per impostazione predefinita lo aggiungerà come abilitato. I ```-Enabled``` parametri e ```-Description``` sono facoltativi.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>Visualizzare tutte le eccezioni numeri

In questo esempio il parametro -Identity è facoltativo. Se il ```-Identity``` parametro non è specificato, questo cmdlet restituisce un elenco di tutti i criteri di eccezione dei numeri immessi per un tenant.

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificare un'eccezione numero

In questo esempio il parametro -Identity è obbligatorio. Il ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet consente di modificare uno o più parametri per una determinata identità del modello di numero.

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>Rimuovere un'eccezione numero

In questo esempio il ```-Identity``` parametro è obbligatorio. Questo cmdlet rimuoverà il criterio di numero specificato dall'elenco tenant.  Se l'identità non è nota, usare il ```Get-CsInboundBlockedNumberPattern``` cmdlet per individuare prima lo schema corretto e prendere nota dell'identità. Quindi, eseguire il ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet e passare il valore di identità appropriato. Consentire il tempo per la replica prima di testare e convalidare.

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Verificare se un numero è bloccato

Usare il ```Test-CsInboundBlockedNumberPattern``` cmdlet per verificare se un numero è bloccato nel tenant.

In questo esempio i ```-Phonenumber``` parametri e ```-Tenant``` sono obbligatori. Il ```-PhoneNumber``` parametro deve essere una stringa numerica senza altri caratteri, ad esempio + o -. In TRPS, il ```-Tenant parameter``` è facoltativo. Il parametro risultante ```isNumberBlocked``` restituisce il valore True se il numero è bloccato nel tenant e False se non è bloccato.

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

## <a name="a-note-about-regex"></a>Una nota su Regex

Come indicato in precedenza, la corrispondenza dei criteri per il blocco dei chiamanti viene eseguita usando Regex. Sono disponibili più strumenti online per convalidare una corrispondenza del modello Regex. Se non si ha familiarità con i modelli Regex, è consigliabile dedicare del tempo per acquisire familiarità con le nozioni di base. Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze ai numeri bloccati al tenant.

## <a name="related-topics"></a>Argomenti correlati

- [Configurare il computer per gestire Skype for Business Online tramite Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
