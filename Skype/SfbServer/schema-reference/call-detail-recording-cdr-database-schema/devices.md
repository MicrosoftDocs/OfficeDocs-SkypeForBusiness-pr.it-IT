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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabella dispositivi è una tabella di supporto. Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815284"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabella dispositivi in Skype for Business Server 2015
 
La tabella dispositivi è una tabella di supporto. Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questa versione hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Esterna  <br/> |Fabbricante di questo dispositivo. Per altre informazioni, vedere la [tabella produttori in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Esterna  <br/> |Versione hardware di questo dispositivo. Per altre informazioni, vedere la [tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Indirizzo MAC  <br/> |
   

