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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802656"
---
# <a name="sessioncorrelation-table"></a>Tabella SessionCorrelation
 
La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Checksum** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo A/V Conferencing Server.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Le sessioni correlate avranno lo stesso ID correlazione.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Solo per uso interno.  <br/> |
   

