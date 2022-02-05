---
title: Tabella MonitoredRegionLink
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
---

# <a name="monitoredregionlink-table"></a>Tabella MonitoredRegionLink
 
La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
   

