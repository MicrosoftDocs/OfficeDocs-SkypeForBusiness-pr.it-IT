---
title: Tabella dispositivi in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabella dispositivi è una tabella di supporto. Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194820"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabella dispositivi in Skype for Business Server 2015
 
La tabella dispositivi è una tabella di supporto. Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questa versione hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Esterna  <br/> |Fabbricante di questo dispositivo. Per altre informazioni, vedere la [tabella produttori in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Esterna  <br/> |Versione hardware di questo dispositivo. Per altre informazioni, vedere la [tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Indirizzo MAC  <br/> |
   

