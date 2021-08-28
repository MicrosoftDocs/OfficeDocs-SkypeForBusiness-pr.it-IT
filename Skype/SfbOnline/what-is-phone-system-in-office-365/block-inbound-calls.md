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
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 8b4c26fb1f0a34c2dd0b7fb5159398e7eaf54df3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581130"
---
# <a name="block-inbound-calls"></a>Bloccare le chiamate in ingresso

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business I piani per chiamate online ora supportano il blocco delle chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network). Questa caratteristica consente di definire un elenco globale tenant di schemi numerici in modo che l'ID chiamante di ogni chiamata PSTN in arrivo al tenant possa essere verificato rispetto all'elenco per trovare una corrispondenza. Se viene effettuata una corrispondenza, una chiamata in arrivo viene rifiutata.

Questa funzionalità di blocco delle chiamate in ingresso funziona solo per le chiamate in ingresso provenienti dalla rete PSTN e funziona solo su base tenant-globale. Non è disponibile per ogni utente.  

Questa funzionalità non è ancora disponibile per il routing diretto.

>[!NOTE]
> I chiamanti bloccati potrebbero avere comportamenti leggermente diversi quando sono stati bloccati. Il comportamento si basa sul modo in cui il gestore del chiamante bloccato gestisce la notifica che la chiamata non può essere completata correttamente. Alcuni esempi possono includere un messaggio dell'operatore che indica che la chiamata non può essere completata come chiamata o semplicemente la chiamata.

## <a name="call-blocking-admin-controls-and-information"></a>Informazioni e controlli di amministrazione del blocco delle chiamate

I controlli di amministrazione per i numeri di blocco vengono forniti solo tramite PowerShell. I criteri dei blocchi numerici sono definiti come criteri di espressione regolare. L'ordine delle espressioni non è importante: il primo criterio corrispondente nell'elenco causa il blocco della chiamata. Un nuovo numero o modello aggiunto o rimosso nell'elenco dei chiamanti bloccati può richiedere fino a 24 ore prima che il criterio diventi attivo.

## <a name="call-blocking-powershell-commands"></a>Comandi di PowerShell per il blocco delle chiamate

I modelli numerici vengono gestiti ```CsInboundBlockedNumberPattern``` tramite i comandi , , , e ```New``` ```Get``` ```Set``` ```Remove``` . È possibile gestire un determinato criterio usando questi cmdlet, inclusa la possibilità di attivare o disattivare un determinato criterio.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) restituisce un elenco di tutti i modelli di numero bloccati aggiunti all'elenco tenant, tra cui Name, Description, Enabled (True/False) e Pattern per ognuno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) aggiunge uno schema di numeri bloccati all'elenco tenant.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) rimuove uno schema di numeri bloccati dall'elenco tenant.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o più parametri di uno schema di numeri bloccati nell'elenco tenant.

La visualizzazione e l'attivazione dell'intera funzionalità di blocco delle chiamate vengono gestite tramite ```CsTenantBlockingCallingNumbers``` i ```Get``` comandi e ```Set``` .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) restituisce i parametri per l'elenco globale dei numeri bloccati, tra cui Enabled (True/False). Esiste un singolo criterio tenant globale che non può essere modificato manualmente se non per attivare o disattivare la caratteristica.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) consente di modificare le chiamate bloccate del tenant globale per essere attivate e disattivate a livello di tenant.

### <a name="examples"></a>Esempi

#### <a name="block-a-number"></a>Bloccare un numero

In questo esempio i parametri ```-Enabled``` e ```-Description``` sono facoltativi:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creazione di un nuovo criterio aggiunge il motivo come abilitato per impostazione predefinita. La descrizione è un campo facoltativo per fornire altre informazioni.

È consigliabile specificare un nome significativo per comprendere facilmente il motivo per cui è stato aggiunto il criterio. Nel caso di bloccare semplicemente i numeri di posta indesiderata, è consigliabile assegnare alla regola lo stesso modello di numero corrispondente e aggiungere altre informazioni nella descrizione in base alle esigenze.

I criteri vengono abbinati usando espressioni regolari (Regex). Concedere tempo per la replica prima di testare e convalidare.

#### <a name="allow-a-number"></a>Consenti un numero

In questo esempio il ```-Identity``` parametro è obbligatorio:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se l'identità non è nota, usare il cmdlet per individuare prima lo ```Get-CsInboundBlockedNumberPattern``` schema corretto e prendere nota dell'identità. Eseguire quindi il ```Remove-CsTenantBlockedNumberPattern``` cmdlet e passare il valore identity appropriato.

Concedere tempo per la replica prima di testare e convalidare.

#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli numerici

L'esecuzione di questo cmdlet restituisce un elenco di tutti i numeri bloccati immessi per un tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Usare le funzionalità di filtro incorporate di PowerShell per analizzare i valori restituiti in base alle esigenze.

## <a name="add-number-exceptions"></a>Aggiungere eccezioni numeri

È possibile aggiungere eccezioni ai modelli di numeri bloccati tramite i ```CsTenantBlockNumberExceptionPattern``` comandi , , , e ```New``` ```Get``` ```Set``` ```Remove``` .

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) aggiunge un modello di eccezione numerica all'elenco tenant. 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) restituisce un elenco di tutti i modelli di eccezione numerica aggiunti all'elenco tenant.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o più parametri in un modello di eccezione numerica nell'elenco tenant.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) rimuove uno schema di eccezione numerica dall'elenco tenant.

### <a name="examples"></a>Esempi

#### <a name="add-a-number-exception"></a>Aggiungere un'eccezione numerica

In questo esempio viene creato un nuovo modello di eccezione numerica che, per impostazione predefinita, lo aggiunge come abilitato. I ```-Enabled``` parametri e sono ```-Description``` facoltativi.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Visualizzare tutte le eccezioni numeri

In questo esempio il parametro -Identity è facoltativo. Se il parametro non è specificato, questo cmdlet restituisce un elenco di tutti i modelli di eccezione ```-Identity``` numerica immessi per un tenant.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificare un'eccezione numerica

In questo esempio il parametro -Identity è obbligatorio. Il ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet consente di modificare uno o più parametri per una determinata identità dello schema di numeri.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Rimuovere un'eccezione numerica

In questo esempio il ```-Identity``` parametro è obbligatorio. Questo cmdlet rimuove il modello di numero specificato dall'elenco dei tenant.  Se l'identità non è nota, usare il cmdlet per individuare prima lo ```Get-CsInboundBlockedNumberPattern``` schema corretto e prendere nota dell'identità. Eseguire quindi il ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet e passare il valore identity appropriato.Concedere tempo per la replica prima di testare e convalidare.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Verificare se un numero è bloccato

Usare il ```Test-CsInboundBlockedNumberPattern``` cmdlet per verificare se un numero è bloccato nel tenant.
 
In questo esempio i ```-Phonenumber``` parametri e ```-Tenant``` sono obbligatori. Il ```-PhoneNumber``` parametro deve essere una stringa numerica senza altri caratteri, ad esempio + o -. In TRPS l'opzione ```-Tenant parameter``` è facoltativa. Il parametro risultante restituisce il valore True se il numero è bloccato nel ```isNumberBlocked``` tenant e False se non è bloccato.

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

Come indicato in precedenza, la corrispondenza dei criteri per bloccare i chiamanti viene eseguita usando Regex. Sono disponibili più strumenti online per convalidare una corrispondenza dei criteri Regex. Se non si ha familiarità con i modelli Regex, è consigliabile acquisire familiarità con le nozioni di base. Per assicurarsi di ottenere i risultati previsti, usare uno strumento per convalidare le corrispondenze dei criteri prima di aggiungere nuove corrispondenze di numeri bloccati al tenant. 

## <a name="related-topics"></a>Argomenti correlati

- [Configurare il computer per la gestione Skype for Business Online usando Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
