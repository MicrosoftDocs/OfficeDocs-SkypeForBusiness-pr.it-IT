---
title: Tabella AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La tabella AppSharingMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con la condivisione delle applicazioni. Queste soglie vengono usate per determinare se l'esperienza di condivisione dell'applicazione deve essere classificata come scadente.
ms.openlocfilehash: d3e7bab384c5fffea59e165d5fdf4e6b3d0c09a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194641"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabella AppSharingMetricsThreshold
 
La tabella AppSharingMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con la condivisione delle applicazioni. Queste soglie vengono usate per determinare se l'esperienza di condivisione dell'applicazione deve essere classificata come scadente.
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Principale  <br/> |Tipo di chiamata inserita.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 1 milione.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitazione della larghezza di banda accettabile per la condivisione delle applicazioni. Il valore predefinito è 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimale (5; 2)  <br/> ||Tasso percentuale ottimale per i riquadri "viziati" per la classificazione di una qualità di condivisione delle applicazioni. Questo valore è la percentuale del contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto può essere scartato (o viziato) quando il condivisore Elimina i riquadri dall'origine grafica o i riquadri di ASMCU scartano rispettivamente i riquadri di condivisione. Il valore predefinito è 11%.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimale (5; 2)  <br/> ||Tasso percentuale accettabile per i riquadri "viziati" per la classificazione di una qualità di condivisione delle applicazioni. Questo valore è la percentuale del contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto può essere scartato (o viziato) quando il condivisore Elimina i riquadri dall'origine grafica o i riquadri di ASMCU scartano rispettivamente i riquadri di condivisione. Il valore predefinito è 36%.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Questa colonna non viene usata in Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Questa colonna non viene usata in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |galleggiante  <br/> ||Questa colonna non viene usata in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |galleggiante  <br/> ||Questa colonna non viene usata in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |galleggiante  <br/> ||Questa colonna non viene usata in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |galleggiante  <br/> ||Questa colonna non viene usata in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |galleggiante  <br/> ||Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione dell'applicazione. Si tratta di una misura di latenza single-hop. Il valore predefinito è 1,0 secondi.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |galleggiante  <br/> ||Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione dell'applicazione. Si tratta di una misura di latenza single-hop. Il valore predefinito è 1,75 secondi.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |galleggiante  <br/> ||Valore ottimale della latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. La latenza è la differenza di orario tra il momento in cui il fotogramma iniziale è codificato nel server (condivisore o MCU a seconda dello scenario) e lo stesso fotogramma iniziale viene decodificato nel visualizzatore.  <br/> Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione. Un server di conferenza di overload può avere ritardi medi più alti. Il valore predefinito è 200ms.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |galleggiante  <br/> ||Valore accettabile della latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. La latenza è la differenza di orario tra il momento in cui il fotogramma iniziale è codificato nel server (condivisore o MCU a seconda dello scenario) e lo stesso fotogramma iniziale viene decodificato nel visualizzatore.  <br/> Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione. Un server di conferenza di overload può avere ritardi medi più alti. Il valore predefinito è 200ms.  <br/> La colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

