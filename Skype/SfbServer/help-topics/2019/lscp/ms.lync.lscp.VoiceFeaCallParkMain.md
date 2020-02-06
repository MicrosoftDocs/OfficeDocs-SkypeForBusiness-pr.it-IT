---
title: Parcheggio di chiamata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando non viene recuperata o eliminata. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Call Park può avere uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.
ms.openlocfilehash: 7f4a660c3fdd1dbba5080b93bec0aac116d453ea
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797813"
---
# <a name="call-park"></a>Parcheggio di chiamata

Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando non viene recuperata o eliminata. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Call Park può avere uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.

Nella pagina del **parco chiamate** viene visualizzato un elenco di tutti gli intervalli di numeri di parcheggio di chiamata definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Parcheggio di chiamata** è possibile eseguire le attività seguenti:

- Creare un nuovo intervallo di numeri

- Modificare un intervallo di numeri esistente

- Eliminare un intervallo di numeri

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i comandi presenti nella pagina.

- **Nuovo** Avvia un nuovo intervallo di numeri di parcheggio per le chiamate.

- **Modifica** Apre l'intervallo di numeri selezionato per la modifica, seleziona tutti gli intervalli di numeri nell'elenco o Elimina l'intervallo di numeri selezionato.

- **Aggiornare** Aggiorna l'elenco di intervalli di numeri.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Nome univoco che identifica l'intervallo di numeri.

- **Intervallo di inizio** Numero iniziale dell'intervallo.

- **Intervallo di fine** Numero finale dell'intervallo.

- **Destinazione** Nome di dominio completo (FQDN) o ID servizio del servizio applicazione che ospita l'applicazione Call Park per l'intervallo di numeri.

Per informazioni dettagliate sulle funzionalità e le funzionalità di Call Park, vedere [pianificare il parcheggio delle chiamate in Skype for business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Per informazioni dettagliate sull'uso degli intervalli di numeri di Call Park, vedere [configurare le estensioni dei numeri di telefono per le chiamate di parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


