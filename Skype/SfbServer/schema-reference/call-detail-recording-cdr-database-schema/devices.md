---
title: Tabella Devices in Skype for Business Server 2015
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831816"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabella Devices in Skype for Business Server 2015
 
La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questa versione hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Stranieri  <br/> |Produttore del dispositivo. Per ulteriori informazioni, vedere la [tabella Manufacturers in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Stranieri  <br/> |Versione hardware del dispositivo. Per ulteriori informazioni, vedere la [tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Indirizzo MAC  <br/> |
   

