---
title: Tabella VideoClientEvent
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Ogni record contiene un evento client per un endpoint in una videochiamata. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
ms.openlocfilehash: 8c2f9142bb187fec8ceb55c34ea28c7f62b06d23
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858933"
---
# <a name="videoclientevent-table"></a>Tabella VideoClientEvent
 
Ogni record contiene un evento client per un endpoint in una videochiamata. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principale  <br/> |0: dati del chiamato  <br/> 1: Dati del chiamante  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Percentuale della sessione in cui è stato generato l'evento LowBandwidth per lo stato "Bad". La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Percentuale della sessione in cui è stato generato l'evento ReceiveSendQuality per lo stato "Bad".  <br/> La qualità della rete in termini di instabilità o perdita di pacchetti è grave e influisce sulla qualità dell'audio ricevuto.  <br/> |
   

