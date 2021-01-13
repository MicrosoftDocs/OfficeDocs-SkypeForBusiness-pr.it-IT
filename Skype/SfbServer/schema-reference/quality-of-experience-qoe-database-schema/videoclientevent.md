---
title: Tabella VideoClientEvent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Ogni record contiene l'evento client per un endpoint in una chiamata video. In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821396"
---
# <a name="videoclientevent-table"></a>Tabella VideoClientEvent
 
Ogni record contiene l'evento client per un endpoint in una chiamata video. In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |0: dati del destinatario della chiamata  <br/> 1: dati del chiamante  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '. La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.  <br/> La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.  <br/> |
   

