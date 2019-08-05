---
title: Tabella MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194603"
---
# <a name="monitoredusersitelink-table"></a>Tabella MonitoredUserSiteLink
 
La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaria, straniera  <br/> |A cui si fa riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaria, straniera  <br/> |Riferimento dalla [tabella UserSite](usersite.md).  <br/> |
   

