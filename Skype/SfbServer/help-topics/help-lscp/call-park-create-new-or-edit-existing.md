---
title: Parcheggio di chiamata creare un nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Gli intervalli di numeri del parcheggio di chiamata definiscono i numeri temporanei in cui vengono mantenute le chiamate parcheggiate fino a quando qualcuno non le recupera o il timeout.
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819386"
---
# <a name="call-park-create-new-or-edit-existing"></a>Parcheggio di chiamata: creare un nuovo intervallo di codici orbit o modificarne uno esistente

Gli intervalli di numeri del parcheggio di chiamata definiscono i numeri temporanei in cui vengono mantenute le chiamate parcheggiate fino a quando qualcuno non le recupera o il timeout.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri. Questo nome non potrà essere modificato dopo aver salvato l'intervallo di numeri.

- **Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri. Nel secondo campo digitare il numero finale dell'intervallo.

  - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.

  - Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

  - L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.

  - Se l'intervallo di numeri inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.

  - Valori validi: deve corrispondere alla stringa di espressione regolare ([ \\ * | #]? [ 1-9] \d {0,7} ) | ([1-9] \d {0,8} ). Questo significa che il valore deve essere una stringa che inizia con il carattere \* o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o #, il carattere seguente deve essere un numero compreso tra 1 e 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero compreso tra 0 e 9 fino a sette caratteri aggiuntivi, ad esempio "#6000", " \* 92000", " \* 95551212" e "915551212". Se il primo carattere non è \* o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9 (ad esempio: 915551212; 41212; 300).

  - Non è possibile definire più di 50.000 numeri in totale per ogni pool. Ogni intervallo di numeri include in genere 100 numeri o meno, ma può essere molto più esteso a condizione che includa meno di 10.000 numeri. Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".

- **FQDN del server di destinazione** Selezionare il nome di dominio completo (FQDN) o l'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate nei numeri entro l'intervallo specificato dal numero iniziale e da quello finale nell'intervallo saranno instradate a questo server o pool.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del parcheggio di chiamata, vedere [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Per informazioni dettagliate sull'utilizzo di intervalli di numeri di parcheggio di chiamata, vedere [Configure Phone Number Extensions for parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)calls.


