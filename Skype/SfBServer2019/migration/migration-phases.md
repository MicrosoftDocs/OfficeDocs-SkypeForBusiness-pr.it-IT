---
title: Fasi della migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server 2019, si definiscono i siti nella rete che contengono componenti di Skype for Business Server 2019. Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752628"
---
# <a name="migration-phases"></a>Fasi della migrazione

In Skype for Business Server 2019, si definiscono i siti nella rete che contengono componenti di Skype for Business Server 2019. Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità. 
  
Un pool Front End è un gruppo di Front End Server configurati in modo identico che collaborano per offrire servizi a un gruppo comune di utenti. Un pool garantisce scalabilità e funzionalità di failover per gli utenti. Ogni server in un pool deve eseguire uno o più ruoli del server identici. Un server Standard Edition, progettato per le organizzazioni di piccole dimensioni, definisce inoltre un pool e viene eseguito in un singolo server. Ciò consente di disporre delle funzionalità di Skype for Business Server 2019 a costi inferiori, ma non offre una vera soluzione a disponibilità elevata. 
  
Le fasi seguenti descrivono il processo di migrazione di un pool a Skype for Business Server 2019. Nel caso di più siti che includono più pool, per ogni singolo pool sarà necessario adottare questo approccio in più fasi.
  
1. [Fase 1: pianificare la migrazione](phase-1-plan-your-migration.md)
    
2. [Fase 2: preparare la migrazione](phase-2-prepare-for-migration.md)
    
3. [Fase 3: distribuire il pool pilota di Skype for Business Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Fase 5: Aggiungere il server perimetrale di Skype for Business Server 2019 al pool pilota](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)
    
8. [Fase 8: rimuovere le autorizzazioni dei pool legacy](phase-8-decommission-legacy-pools.md)
    

