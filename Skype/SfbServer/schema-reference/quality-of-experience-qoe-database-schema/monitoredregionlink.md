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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
ms.openlocfilehash: 991cc3b6ce2f442ad13c350d2e37cc7c9d592d40d16da51932975a4907040569
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321628"
---
# <a name="monitoredregionlink-table"></a>Tabella MonitoredRegionLink
 
La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
   

