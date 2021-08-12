---
title: Tabella dei dispositivi
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
description: La tabella Device è una tabella di supporto che archivia informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
ms.openlocfilehash: d060ec010cc67ea45fb2f7c58ccc574a7bdbc4ea566342943f7a8f587a9676f5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347731"
---
# <a name="device-table"></a>Tabella dei dispositivi
 
La tabella Device è una tabella di supporto che archivia informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType è univoco  <br/> |Nome del dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType è univoco  <br/> |Tipo di dispositivo. 1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.  <br/> |
   

