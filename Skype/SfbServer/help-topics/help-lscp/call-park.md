---
title: Parcheggio di chiamata
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
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Quando una chiamata è parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando qualcuno non la recupera o si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Parcheggio di chiamata può avere uno o più intervalli di interni. Tali intervalli devono essere univoci nell'intera distribuzione.
ms.openlocfilehash: 7723b3bb3145725834059c73c0acc273fc67ca61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800306"
---
# <a name="call-park"></a>Parcheggio di chiamata

Quando una chiamata è parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando qualcuno non la recupera o si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Parcheggio di chiamata può avere uno o più intervalli di interni. Tali intervalli devono essere univoci nell'intera distribuzione.

Nella **pagina Parcheggio di** chiamata viene visualizzato un elenco di tutti gli intervalli di numeri del parcheggio di chiamata definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Parcheggio di chiamata** è possibile eseguire le attività seguenti:

- Creare un nuovo intervallo di numeri

- Modificare un intervallo di numeri esistente

- Eliminare un intervallo di numeri

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Nell'elenco seguente sono descritti i comandi della pagina.

- **Nuovo** Avvia un nuovo intervallo di numeri del parcheggio di chiamata.

- **Modifica** Apre l'intervallo di numeri selezionato per la modifica, seleziona tutti gli intervalli di numeri nell'elenco oppure elimina l'intervallo di numeri selezionato.

- **Aggiorna** Aggiorna l'elenco di intervalli di numeri.

L'elenco seguente descrive i campi presenti nella pagina.

- **Name** Nome univoco che identifica l'intervallo di numeri.

- **Intervallo iniziale** Numero iniziale dell'intervallo.

- **Intervallo di fine** Numero finale dell'intervallo.

- **Destinazione** Nome di dominio completo (FQDN) o ID servizio del servizio applicazione che ospita l'applicazione Parcheggio di chiamata per l'intervallo di numeri.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del parcheggio di chiamata, vedere [Pianificare il parcheggio di chiamata in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md) Per informazioni dettagliate sull'utilizzo degli intervalli di numeri del parcheggio di chiamata, vedere [Configure Phone Number Extensions for Parking Calls.](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)


