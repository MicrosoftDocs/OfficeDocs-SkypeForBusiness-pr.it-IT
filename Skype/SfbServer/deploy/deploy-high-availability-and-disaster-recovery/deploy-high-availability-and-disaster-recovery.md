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
description: Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con l'abbinamento del pool e diverse modalità di disponibilità elevata del server back-end, inclusi i gruppi di disponibilità AlwaysOn, il mirroring del database e il clustering di failover SQL.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830616"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Distribuire disponibilità elevata e ripristino di emergenza
 
Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con l'abbinamento del pool e diverse modalità di disponibilità elevata del server back-end, inclusi i gruppi di disponibilità AlwaysOn, il mirroring del database e il clustering di failover SQL. 
  
La disponibilità elevata si riferisce al fare in modo che i servizi di Skype for Business Server siano disponibili anche se uno o più server sono inattivi. Il ripristino di emergenza si riferisce alla conservazione dei servizi in caso di emergenza naturale o causata da un ambiente umano e alla conservazione del maggior quantità possibile di dati prima del verificarsi del disastro.
  
In questa sezione viene descritto come distribuire queste funzionalità e vengono illustrati i passaggi che è possibile eseguire per la disponibilità elevata e il ripristino di emergenza per alcuni degli altri ruoli del server.

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
  
## <a name="related-sections"></a>Sezioni correlate

[Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Vedere anche

[Distribuire un gruppo di disponibilità AlwaysOn su un server back-end in Skype for Business Server](alwayson-availability-group.md)

[Distribuire pool Front End abbinati per il ripristino di emergenza in Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Distribuire il mirroring di SQL per la disponibilità elevata del server back-end in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
