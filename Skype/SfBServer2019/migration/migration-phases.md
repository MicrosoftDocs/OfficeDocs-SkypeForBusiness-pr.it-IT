---
title: Fasi di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype for Business Server 2019 si definiscono i siti della rete che contengono componenti di Skype for Business Server 2019. Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità.
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195007"
---
# <a name="migration-phases"></a>Fasi di migrazione

In Skype for Business Server 2019 si definiscono i siti della rete che contengono componenti di Skype for Business Server 2019. Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità. 
  
Un pool Front-End è un set di server front-end configurati in modo identico e collaborano per creare servizi per un gruppo di utenti comune. Un pool offre funzionalità di scalabilità e failover per gli utenti. Ogni server in un pool deve eseguire un ruolo o ruoli del server identico. Un server Standard Edition, progettato per le piccole organizzazioni, definisce anche un pool ed è in esecuzione su un singolo server. In questo modo è possibile avere una funzionalità di Skype for Business Server 2019 per un costo minore, ma non offre una vera soluzione a elevata disponibilità. 
  
Le fasi seguenti descrivono il processo di migrazione del pool a Skype for Business Server 2019. Per più siti che contengono più pool, ogni singolo pool deve seguire questo approccio graduale.
  
1. [Fase 1: pianificare la migrazione](phase-1-plan-your-migration.md)
    
2. [Fase 2: preparare la migrazione](phase-2-prepare-for-migration.md)
    
3. [Fase 3: distribuire Skype for Business Server 2019 Pilot pool](phase-3-deploy-pilot-pool.md)
    
4. [Fase 4: trasferire gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Fase 5: aggiungere Skype for Business Server 2019 Edge Server al pool pilota](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Fase 6: passaggio dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)
    
8. [Fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md)
    

