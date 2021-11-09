---
title: Tabella AppSharingMetricsThreshold
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
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La tabella AppSharingMetricsThreshold contiene i valori ottimali e accettabili delle metriche QoE utilizzate con la condivisione delle applicazioni. Questi valori soglia sono utilizzati per determinare se l'esperienza di condivisione deve essere classificata come insufficiente.
ms.openlocfilehash: 23e97758d5398b8c8797900f043de7c1b6a3ebf6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864563"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabella AppSharingMetricsThreshold
 
La tabella AppSharingMetricsThreshold contiene i valori ottimali e accettabili delle metriche QoE utilizzate con la condivisione delle applicazioni. Questi valori soglia sono utilizzati per determinare se l'esperienza di condivisione deve essere classificata come insufficiente.
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Principale  <br/> |Tipo di chiamata effettuata.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitazione accettabile della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Percentuale ottimale per i riquadri "viziati" per classificare una qualità di condivisione applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 11 percento.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Percentuale accettabile per i riquadri "viziati" per classificare una qualità di condivisione applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 36 percento.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Questa colonna non viene utilizzata in Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Questa colonna non viene utilizzata in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Questa colonna non viene utilizzata in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Questa colonna non viene utilizzata in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Questa colonna non viene utilizzata in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Questa colonna non viene utilizzata in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,0 secondi.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,75 secondi.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Latenza ottimale di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione. La latenza è la differenza di tempo tra la codifica del fotogramma iniziale nel server (condivisore o MCU a seconda dello scenario) e la decodifica dello stesso fotogramma iniziale nel visualizzatore.  <br/> Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Latenza accettabile di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione. La latenza è la differenza di tempo tra la codifica del fotogramma iniziale nel server (condivisore o MCU a seconda dello scenario) e la decodifica dello stesso fotogramma iniziale nel visualizzatore.  <br/> Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

