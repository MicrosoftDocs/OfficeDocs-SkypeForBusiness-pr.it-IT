---
title: Tabella MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
---

# <a name="monitoredusersitelink-table"></a>Tabella MonitoredUserSiteLink
 
La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaria, esterna  <br/> |Riferimento dalla [tabella UserSite](usersite.md).  <br/> |
   

