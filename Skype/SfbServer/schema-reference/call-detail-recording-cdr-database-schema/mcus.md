---
title: Tabella MCU in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Tali servizi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di telefonia (che viene eseguito come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821426"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabella MCU in Skype for Business Server 2015
 
La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Tali servizi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di telefonia (che viene eseguito come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server per conferenze.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Stranieri <br/> |Tipo di Server Conferencing, ad esempio conf: chat (per IMs) o conf: audio-video. Per ulteriori informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
   

