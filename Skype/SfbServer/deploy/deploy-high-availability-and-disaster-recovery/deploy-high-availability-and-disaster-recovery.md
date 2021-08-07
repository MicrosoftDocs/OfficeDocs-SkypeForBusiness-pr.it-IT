---
title: Distribuire disponibilità elevata e ripristino di emergenza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con associazione di pool e diverse modalità di disponibilità elevata del server back-end, tra cui gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: bb9a4428a1655308ca97fc837a20da799c8c09702c9cb906cf7d0157cda90c15
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305878"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Distribuire disponibilità elevata e ripristino di emergenza
 
Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con associazione di pool e diverse modalità di disponibilità elevata del server back-end, tra cui gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL. 
  
Per disponibilità elevata si intende verificare che i Skype for Business Server siano disponibili anche se uno o più server non sono disponibili. Per ripristino di emergenza si intende mantenere i servizi in esecuzione in caso di emergenza naturale o causata dall'uomo e conservare il maggior numero possibile di dati prima della emergenza.
  
In questa sezione viene illustrato come distribuire queste funzionalità e vengono inoltre illustrati i passaggi che è possibile eseguire per la disponibilità elevata e il ripristino di emergenza per alcuni degli altri ruoli del server.

> [!NOTE]
> SQL Il mirroring è disponibile Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
  
## <a name="related-sections"></a>Sezioni correlate

[Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Vedere anche

[Distribuire un gruppo di disponibilità AlwaysOn in un server back-end in Skype for Business Server](alwayson-availability-group.md)

[Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Distribuire SQL mirroring per la disponibilità elevata del server back-end in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
