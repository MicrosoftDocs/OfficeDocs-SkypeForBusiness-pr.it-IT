---
title: Tabella Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194628"
---
# <a name="device-table"></a>Tabella Device
 
La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar (256)  <br/> |DeviceName + DeviceType è univoco  <br/> |Nome dispositivo.  <br/> |
|**DeviceType** <br/> |po'  <br/> |DeviceName + DeviceType è univoco  <br/> |Tipo di dispositivo. 1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.  <br/> |
   

