---
title: Parcheggio di chiamata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta finché un utente non lo recupera o non si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si desidera riservare per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812166"
---
# <a name="call-park"></a>Parcheggio di chiamata

Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta finché un utente non lo recupera o non si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si desidera riservare per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.

Nella pagina **parcheggio di chiamata** viene visualizzato un elenco di tutti gli intervalli di numeri del parcheggio di chiamata definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Parcheggio di chiamata** è possibile eseguire le attività seguenti:

- Creare un nuovo intervallo di numeri

- Modificare un intervallo di numeri esistente

- Eliminare un intervallo di numeri

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Nell'elenco seguente sono descritti i comandi della pagina.

- **Nuovo** Avvia un nuovo intervallo di numeri del parcheggio di chiamata.

- **Modifica** Consente di aprire l'intervallo di numeri selezionato per la modifica, di selezionare tutti gli intervalli di numeri nell'elenco oppure di eliminare l'intervallo di numeri selezionato.

- **Aggiorna** Aggiorna l'elenco di intervalli di numeri.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Nome univoco che identifica l'intervallo di numeri.

- **Intervallo di avvio** Il numero iniziale dell'intervallo.

- **Intervallo finale** Numero finale dell'intervallo.

- **Destinazione** Il nome di dominio completo (FQDN) o l'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata per l'intervallo di numeri.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del parcheggio di chiamata, vedere [pianificare il parcheggio di chiamata in Skype for business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Per informazioni dettagliate sull'utilizzo di intervalli di numeri di parcheggio di chiamata, vedere [Configure Phone Number Extensions for parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)calls.


