---
title: Pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695971"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server
 
Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL. 
  
L'elevata disponibilità fa riferimento a garantire che i servizi di Skype for Business Server siano disponibili anche se uno o più server vengono abbattuti. Il ripristino di emergenza si riferisce a mantenere i servizi in corso in caso di un disastro naturale o causato dall'uomo e a preservare il maggior quantità possibile di dati prima del disastro.
  
Come nelle versioni precedenti di Lync Server, la caratteristica di elevata disponibilità principale per la maggior parte dei ruoli del server in Skype for Business Server è la ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server. Questo vale per i server front-end, Edge Server, Mediation Server e direttori.
  
Skype for Business Server offre anche le opzioni di ripristino di emergenza per i pool Front-end. È possibile configurare due pool in aree geografiche diverse per fungere da backup. Quindi, se si ha un intero pool o un sito, il pool di backup può continuare a prestare servizio agli utenti in entrambi i siti.
  
Skype for Business Server supporta anche quattro modalità di disponibilità elevata per i server back-end: mirroring SQL, gruppi di disponibilità AlwaysOn, istanze del cluster di failover AlwaysOn (FCI) e clustering di failover SQL.
  
> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.

> [!NOTE]
> I gruppi di disponibilità AlwaysOn non sono supportati con i server di chat permanenti. 
  
In questa sezione vengono illustrate queste funzionalità e vengono descritte anche le procedure che è possibile eseguire per l'elevata disponibilità e il ripristino di emergenza per alcuni altri ruoli del server. 
  
## <a name="see-also"></a>Vedere anche

[Disponibilità elevata e gestione del pool Front-End](high-availability.md)
  
[Ripristino di emergenza del pool di front-end in Skype for Business Server](disaster-recovery.md)
  
[Esperienza utente durante l'errore del pool in Skype for Business Server](user-experience.md)
  
[Disponibilità elevata del server back-end in Skype for Business Server](back-end-server.md)
  
[Condivisione di file con disponibilità elevata in Skype for Business Server](file-sharing.md)
