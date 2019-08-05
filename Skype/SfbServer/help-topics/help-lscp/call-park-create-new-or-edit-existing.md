---
title: Parcheggio di chiamata creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Gli intervalli di numeri di parcheggio per le chiamate definiscono i numeri temporanei in cui vengono mantenute le chiamate parcheggiate finché qualcuno non li recupera o ne esce fuori.
ms.openlocfilehash: 8e6748f0e106195148453094de3b95e9dc48254c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195127"
---
# <a name="call-park-create-new-or-edit-existing"></a>Parcheggio di chiamata: creare un nuovo intervallo di codici orbit o modificarne uno esistente

Gli intervalli di numeri di parcheggio per le chiamate definiscono i numeri temporanei in cui vengono mantenute le chiamate parcheggiate finché qualcuno non li recupera o ne esce fuori.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri. Questo nome non potrà essere modificato dopo aver salvato l'intervallo di numeri.

- **Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri. Nel secondo campo digitare il numero finale dell'intervallo.

  - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

  - Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

  - L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.

  - Se l'intervallo di numeri inizia con il \* carattere o #, l'intervallo deve essere maggiore di 100.

  - Valori validi: deve corrispondere alla stringa di espressione regolare (\\[* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Questo significa che il valore deve essere una stringa che inizia con il \* carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000"\*, "92000"\*, "95551212" e "915551212"). Se il primo carattere non \* è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9 (ad esempio: 915551212; 41212; 300).

  - Non è possibile definire più di 50.000 numeri in totale per ogni pool. Ogni intervallo di numeri include in genere 100 numeri o meno, ma può essere molto più esteso a condizione che includa meno di 10.000 numeri. Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".

- **Nome di dominio completo del server di destinazione** Selezionare il nome di dominio completo (FQDN) o l'ID servizio del servizio applicazione che ospita l'applicazione Call Park. Tutte le chiamate parcheggiate nei numeri entro l'intervallo specificato dal numero iniziale e da quello finale nell'intervallo saranno instradate a questo server o pool.

Per informazioni dettagliate sulle caratteristiche e le funzionalità di Call Park, vedere [pianificare il parcheggio delle chiamate in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Per informazioni dettagliate sull'uso degli intervalli di numeri di Call Park, vedere [configurare le estensioni dei numeri di telefono per le chiamate di parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


