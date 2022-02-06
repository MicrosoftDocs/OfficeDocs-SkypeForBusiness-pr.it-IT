---
title: Tabella Devices in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabella Devices in Skype for Business Server 2015
 
La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questa versione hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |Produttore del dispositivo. Per ulteriori [informazioni, vedere la tabella Manufacturers Skype for Business Server 2015](manufacturers.md). <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |Versione hardware del dispositivo. Per ulteriori informazioni, vedere [la tabella HardwareVersions Skype for Business Server 2015](hardwareversions.md). <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Indirizzo MAC  <br/> |
   

