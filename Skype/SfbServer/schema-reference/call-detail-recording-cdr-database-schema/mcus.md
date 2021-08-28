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
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.
ms.openlocfilehash: 79585600d417d51172cc9365cb5f8be1f27b8fa3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592480"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabella Mcus in Skype for Business Server 2015
 
La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server per conferenze.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |Tipo di server per conferenze, ad esempio conf:chat (per IMs) o conf:audio-video. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

