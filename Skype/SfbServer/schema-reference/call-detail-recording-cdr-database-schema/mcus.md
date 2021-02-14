---
title: Tabella Mcus in Skype for Business Server 2015
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
description: La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio Im Conferencing e il servizio Di telefonia (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821426"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabella Mcus in Skype for Business Server 2015
 
La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio Im Conferencing e il servizio Di telefonia (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server per conferenze.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Esterna <br/> |Tipo di server per conferenze, ad esempio conf:chat (per IMs) o conf:audio-video. Per altre [informazioni, vedi la tabella UriTypes.](uritypes.md) <br/> |
   

