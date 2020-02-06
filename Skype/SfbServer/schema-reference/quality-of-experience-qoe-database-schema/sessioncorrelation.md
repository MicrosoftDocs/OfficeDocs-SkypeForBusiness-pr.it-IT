---
title: Tabella SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un CorrelationID usato per correlare più sessioni.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805744"
---
# <a name="sessioncorrelation-table"></a>Tabella SessionCorrelation
 
La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un CorrelationID usato per correlare più sessioni. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Checksum** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo server di conferenza A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar (256)  <br/> |Univoci  <br/> |Le sessioni correlate avranno lo stesso ID di correlazione.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> | <br/> |Solo per uso interno.  <br/> |
   

