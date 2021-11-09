---
title: Tabella DeviceDriver
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La tabella DeviceDriver è una tabella di supporto. Ogni record rappresenta un driver utilizzato da un dispositivo di acquisizione o di rendering.
ms.openlocfilehash: 3ca0a88e90b0183bf35c4c84675db5b3327d52ee
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857173"
---
# <a name="devicedriver-table"></a>Tabella DeviceDriver
 
La tabella DeviceDriver è una tabella di supporto. Ogni record rappresenta un driver utilizzato da un dispositivo di acquisizione o di rendering.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo record del driver di dispositivo.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |Nome del driver di dispositivo.  <br/> |
   

