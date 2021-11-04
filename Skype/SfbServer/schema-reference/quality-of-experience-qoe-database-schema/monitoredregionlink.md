---
title: Tabella MonitoredRegionLink
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
ms.openlocfilehash: 39add4c7ba3fc67c68645498772b06715967aa39
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763124"
---
# <a name="monitoredregionlink-table"></a>Tabella MonitoredRegionLink
 
La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
   

