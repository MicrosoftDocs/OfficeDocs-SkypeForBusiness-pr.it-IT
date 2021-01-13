---
title: Tabella Device
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814746"
---
# <a name="device-table"></a>Tabella Device
 
La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar (256)  <br/> |DeviceName + DeviceType è univoco  <br/> |Nome del dispositivo.  <br/> |
|**DeviceType** <br/> |po'  <br/> |DeviceName + DeviceType è univoco  <br/> |Tipo di dispositivo. 1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.  <br/> |
   

