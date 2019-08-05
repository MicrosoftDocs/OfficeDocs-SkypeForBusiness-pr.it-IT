---
title: Tabella MCU in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194776"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabella MCU in Skype for Business Server 2015
 
La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo server di conferenza.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Esterna <br/> |Tipo di server di conferenza, ad esempio conf: chat (per IMs) o conf: audio-video. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
   

