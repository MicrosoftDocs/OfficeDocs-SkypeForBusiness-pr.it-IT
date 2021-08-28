---
title: Tabella MonitoredRegionLink
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
ms.localizationpriority: medium
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
ms.openlocfilehash: f026e35dfd0c0cfd0b7a43d62089754b6824cfa8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604615"
---
# <a name="monitoredregionlink-table"></a>Tabella MonitoredRegionLink
 
La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
   

