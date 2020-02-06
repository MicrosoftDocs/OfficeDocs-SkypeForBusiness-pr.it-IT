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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815064"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabella MCU in Skype for Business Server 2015
 
La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo server di conferenza.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Esterna <br/> |Tipo di server di conferenza, ad esempio conf: chat (per IMs) o conf: audio-video. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
   

