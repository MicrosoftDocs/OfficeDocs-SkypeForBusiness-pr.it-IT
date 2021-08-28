---
title: Tabella SessionCorrelation
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
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni.
ms.openlocfilehash: a0ec0a2e1435aab02ba1733530271b2ad648869e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634120"
---
# <a name="sessioncorrelation-table"></a>Tabella SessionCorrelation
 
La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Checksum** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo A/V Conferencing Server.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Le sessioni correlate avranno lo stesso ID correlazione.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Solo per uso interno.  <br/> |
   

