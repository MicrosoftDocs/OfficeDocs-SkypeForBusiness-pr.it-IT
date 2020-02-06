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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807794"
---
# <a name="monitoredusersitelink-table"></a>Tabella MonitoredUserSiteLink
 
La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaria, straniera  <br/> |A cui si fa riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaria, straniera  <br/> |Riferimento dalla [tabella UserSite](usersite.md).  <br/> |
   

