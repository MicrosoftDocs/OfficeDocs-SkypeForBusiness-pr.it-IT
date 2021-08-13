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
description: La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.
ms.openlocfilehash: 501736f91073b193f68a22dee8bf54899ee1250373258cf49fb19ed02af5c5e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352075"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabella Mcus in Skype for Business Server 2015
 
La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server per conferenze.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |Tipo di server per conferenze, ad esempio conf:chat (per IMs) o conf:audio-video. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

