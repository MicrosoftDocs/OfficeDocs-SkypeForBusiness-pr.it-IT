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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La tabella VideoMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con le videochiamate.
ms.openlocfilehash: 89d3095ef7222cacc7633116c43d66cbcc2be2e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804736"
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

