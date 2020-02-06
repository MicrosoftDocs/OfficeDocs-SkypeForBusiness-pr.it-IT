---
title: Distribuire disponibilità elevata e ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790124"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Distribuire disponibilità elevata e ripristino di emergenza
 
Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL. 
  
L'elevata disponibilità fa riferimento a garantire che i servizi di Skype for Business Server siano disponibili anche se uno o più server vengono abbattuti. Il ripristino di emergenza si riferisce a mantenere i servizi in corso in caso di un disastro naturale o causato dall'uomo e a preservare il maggior quantità possibile di dati prima del disastro.
  
Questa sezione spiega come distribuire queste funzionalità e copre anche i passaggi che è possibile eseguire per l'elevata disponibilità e il ripristino di emergenza per alcuni altri ruoli del server.

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
  
## <a name="related-sections"></a>Sezioni correlate

[Pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Vedere anche

[Distribuire un gruppo di disponibilità AlwaysOn in un server back-end in Skype for Business Server](alwayson-availability-group.md)

[Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Distribuire il mirroring SQL per l'elevata disponibilità del server back-end in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
