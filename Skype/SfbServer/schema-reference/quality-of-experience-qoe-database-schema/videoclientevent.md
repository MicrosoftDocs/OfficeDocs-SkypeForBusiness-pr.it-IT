---
title: Tabella VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Ogni record contiene l'evento client per un endpoint in una videochiamata. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804994"
---
# <a name="videoclientevent-table"></a>Tabella VideoClientEvent
 
Ogni record contiene l'evento client per un endpoint in una videochiamata. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |0: dati del destinatario  <br/> 1: dati del chiamante  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Percentuale della sessione l'evento LowBandwidth è stato generato per lo stato "Bad". La larghezza di banda disponibile è insufficiente per un'esperienza vocale accettabile.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Percentuale della sessione l'evento ReceiveSendQuality è stato generato per lo stato "Bad".  <br/> La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.  <br/> |
   

