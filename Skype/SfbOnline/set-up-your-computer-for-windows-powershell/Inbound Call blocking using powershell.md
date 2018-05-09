---
title: Chiamata in arrivo il blocco di utilizzo di Powershell per Skype per layout Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Utilizzare PowerShell per gestire la chiamata in arrivo blocco in Skype Business online.
ms.openlocfilehash: 10aa92233f2a804edffef8bf6d5b8e5dd7746b06
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2018
---
# <a name="inbound-pstn-call-blocking-for-calling-plans"></a>In ingresso chiamata PSTN per chiamare i piani di blocco

Skype per Business Online la chiamata dei piani supporta il blocco delle chiamate in ingresso dalla rete pubblica commutata (PSTN). Questa funzionalità consente un tenant elenco globale di formati di numeri da definire in modo che possa essere archiviato l'ID chiamante di ogni chiamata PSTN in arrivo al tenant rispetto all'elenco in base alla corrispondenza. Se viene individuata una corrispondenza, verrà rifiutata una chiamata in arrivo. 

Questa caratteristica blocco chiamata in arrivo funziona solo sulle chiamate in ingresso proveniente dalla rete PSTN e funziona solo su base globale tenant e non è disponibile in per singoli utenti.

Questa funzionalità non è ancora disponibile per il Routing diretto.

>[Nota] I chiamanti bloccati potrebbero verificarsi comportamenti leggermente diversi quando sono stati bloccati. Il comportamento si baserà come gestore del chiamante bloccati gestisce la notifica di chiamata non è consentita per essere completata correttamente. Può ad esempio un messaggio di gestore di telefonia che segnala la chiamata non può essere completata, o recarsi semplicemente la chiamata.

## <a name="call-blocking-admin-controls-and-information"></a>Blocco delle informazioni e i controlli di amministrazione di chiamata
Vengono forniti controlli di amministrazione per i numeri di blocchi tramite PowerShell solo. Formati di numeri blocco vengono definiti come criteri di espressioni regolari. L'ordine delle espressioni è importante-il primo modello corrispondono nell'elenco genererà la chiamata viene bloccata. Un nuovo numero o un motivo aggiunte o rimosse in bloccati elenco chiamanti potrebbe richiedere fino a 24 ore per il motivo di diventare attivi.

## <a name="call-blocking-powershell-commands"></a>Chiamata di blocco dei comandi di PowerShell

*InboundBlockedNumberPattern* Formati di numeri vengono gestite tramite i comandi *CsInboundBlockedNumberPattern* **New**, **ottenere**, **impostare**e **rimuovere**.  

È possibile gestire un motivo specifico mediante l'utilizzo di questi cmdlet, inclusa la possibilità di attivare o disattivare l'attivazione di un determinato criterio.
- *Get-CsInboundBlockedNumberPattern* Restituisce un elenco di tutti i formati di numeri bloccati aggiunto all'elenco tenant inclusi nome, descrizione, attivato (True/False) e motivo per ognuno.
- *Nuovo CsInboundBlockedNumberPattern* Aggiunge un formato numero bloccato all'elenco dei tenant.
- *Remove-CsInboundBlockedNumberPattern* Rimuove un formato numero bloccato dall'elenco tenant.
- *Set-CsInboundBlockedNumberPattern* Consente di modificare uno o più parametri di un formato numero bloccato nell'elenco tenant.
- *TenantBlockedCallingNumbers* La visualizzazione e l'attivazione della caratteristica blocco intera chiamata viene gestita tramite CsTenantBlockingCallingNumbers comandi ottenere e impostare. 
- *Get-CsTenantBlockedCallingNumbers* Restituisce i parametri per l'elenco di numeri bloccato globale incluse Enabled (True/False). Non esiste un criterio di tenant singolo globali non può essere modificato manualmente diverso da per attivare la caratteristica completamente attivato/disattivato.
- *Set-CsTenantBlockedCallingNumbers* Consente di modificare le chiamate tenant globale bloccati per essere attivata o disattivata a livello di tenant.

### <a name="examples"></a>Esempi
#### <a name="blocking-a-number"></a>Blocco di un numero

In questo esempio,-abilitato e - descrizione parametri sono facoltativi:

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 Creazione di che un nuovo criterio per impostazione predefinita aggiungerà è sempre il formato come abilitato e la descrizione e un campo facoltativo per fornire ulteriori informazioni. 

È consigliabile è fornire un nome significativo facilmente comprendere il motivo per cui è stato aggiunto il motivo. Nel caso di posta indesiderata semplicemente blocco numeri, in considerazione la regola di denominazione lo stesso come il formato del numero viene corrispondente e aggiungere informazioni aggiuntive nella descrizione di come richiesto.

Vengono associati modelli di utilizzo delle espressioni regolari (regex). Consentire il tempo di replica prima di test e convalida.

#### <a name="allowing-a-number"></a>Supporto di un numero

In questo esempio, il parametro identity, se necessario (is?):`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
Se il parametro Identity non è noto, utilizzare il cmdlet *Get-CsInb undBlockedNumberPattern* innanzitutto individuare il motivo appropriato e annotare l'identità. Eseguire il cmdlet *rimuovere* , quindi passa il valore Identity appropriato.

Consentire il tempo di replica prima di test e convalida.
#### <a name="view-all-number-patterns"></a>Visualizzare tutti i modelli di numero
Esecuzione di questo cmdlet restituirà i numeri di elenco di tutte le immesso bloccato per un tenant:`Get-CsInboundBlockedNumberPattern`

Utilizzare PowerShell incorporati filtro delle capacità per analizzare i valori restituiti in base alle esigenze.

#### <a name="a-note-on-regex"></a>Nota sulla Regex
Come già detto, criteri di ricerca per il blocco dei chiamanti viene eseguito utilizzando le espressioni regolari (regex). Sono disponibili più strumenti disponibili in linea per convalidare un criterio di espressione regolare ricerca. Se non si ha familiarità con i formati di espressioni regolari, è consigliabile richiedere tempo per acquisire familiarità con i concetti di base e per accertarsi di disporre i risultati previsti, utilizzare uno strumento per la convalida di caratteri jolly prima di aggiungere nuove bloccati numero corrisponde al tenant. 

## <a name="related-topics"></a>See also
[Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell](set-up-your-computer-for-windows-powershell.md)