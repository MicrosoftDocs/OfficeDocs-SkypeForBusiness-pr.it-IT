---
title: Tabella VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La tabella VideoMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con le videochiamate.
ms.openlocfilehash: a923334596ea6b3e6b56c43682be0f0f6a640f15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194558"
---
# <a name="videometricsthreshold-table"></a>Tabella VideoMetricsThreshold
 
La tabella VideoMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con le videochiamate.
  

| **Colonna**                                               | **Tipo di dati**       | **Chiave/indice**  | **Dettagli**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Principale  <br/> | Tipo di chiamata inserita.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimale (5; 2)  <br/> |                | Il valore predefinito è 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimale (5; 2)  <br/> |                | Il valore predefinito è 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimale (5; 2)  <br/> |                | Il valore predefinito è 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimale (5; 2)  <br/> |                | Il valore predefinito è 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimale (9; 4)  <br/> |                | Il valore predefinito è 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimale (9; 4)  <br/> |                | Il valore predefinito è 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimale (5; 2)  <br/> |                | Il valore predefinito è 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimale (5; 2)  <br/> |                | Il valore predefinito è 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimale (5; 2)  <br/> |                | Il valore predefinito è 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimale (5; 2)  <br/> |                | Il valore predefinito è 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | Il valore predefinito è 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | galleggiante  <br/>        |                | Il valore predefinito è 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | galleggiante  <br/>        |                | Il valore predefinito è 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | galleggiante  <br/>        |                | Il valore predefinito è 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimale (5; 2)  <br/> |                | Il valore predefinito è 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimale (5; 2)  <br/> |                | Il valore predefinito è 10,00.  <br/>   |

