---
title: Tabella SessionCorrelation
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni.
ms.openlocfilehash: 3b0e3208ec019d205ab74fec8318e0221b70b8ea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771852"
---
# <a name="sessioncorrelation-table"></a>Tabella SessionCorrelation
 
La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Checksum** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo A/V Conferencing Server.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Le sessioni correlate avranno lo stesso ID correlazione.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Solo per uso interno.  <br/> |
   

