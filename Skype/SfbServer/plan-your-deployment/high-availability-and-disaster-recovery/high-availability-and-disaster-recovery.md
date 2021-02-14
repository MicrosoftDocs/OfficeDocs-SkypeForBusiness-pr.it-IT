---
title: Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con associazione di pool e diverse modalità di disponibilità elevata del server back-end, tra cui gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802816"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server
 
Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con associazione di pool e diverse modalità di disponibilità elevata del server back-end, tra cui gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL. 
  
Per disponibilità elevata si intende verificare che i servizi di Skype for Business Server siano disponibili anche se uno o più server non sono disponibili. Per ripristino di emergenza si intende mantenere i servizi in esecuzione in caso di un'emergenza naturale o causata dall'uomo e conservare la maggior quantità possibile di dati prima della situazione di emergenza.
  
Come nelle versioni precedenti di Lync Server, la funzionalità di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server è la ridondanza dei server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore. Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.
  
Skype for Business Server offre anche opzioni di ripristino di emergenza per i pool Front End. È possibile configurare due pool in aree geografiche diverse per fungere da backup l'uno per l'altro. Se quindi si verifica un errore in un intero pool o sito, il pool di backup può continuare a fornire il servizio agli utenti di entrambi i siti.
  
Skype for Business Server supporta anche quattro modalità di disponibilità elevata per i server back-end: mirroring SQL, gruppi di disponibilità AlwaysOn, istanze del cluster di failover AlwaysOn e clustering di failover SQL.
  
> [!NOTE]
> SQL mirroring è disponibile in Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.

> [!NOTE]
> I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente. 
  
In questa sezione vengono illustrate queste funzionalità e vengono inoltre illustrati i passaggi che è possibile eseguire per la disponibilità elevata e il ripristino di emergenza per alcuni degli altri ruoli del server. 
  
## <a name="see-also"></a>Vedere anche

[Disponibilità elevata e gestione del pool Front End](high-availability.md)
  
[Ripristino di emergenza del pool Front End in Skype for Business Server](disaster-recovery.md)
  
[Esperienza utente durante un errore del pool in Skype for Business Server](user-experience.md)
  
[Disponibilità elevata del server back-end in Skype for Business Server](back-end-server.md)
  
[Disponibilità elevata per la condivisione di file in Skype for Business Server](file-sharing.md)
