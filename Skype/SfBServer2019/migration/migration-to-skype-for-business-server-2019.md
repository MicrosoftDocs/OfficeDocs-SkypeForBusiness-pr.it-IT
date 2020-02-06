---
title: Migrazione a Skype for Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Gli argomenti di questa sezione illustrano il processo di migrazione a Skype for Business Server 2019.
ms.openlocfilehash: 51c3be10b90198e1abe24172aa35ab167e871739
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813404"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migrazione a Skype for Business Server 2019

Gli argomenti di questa sezione illustrano il processo di migrazione a Skype for Business Server 2019. Questo articolo illustra la migrazione di Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.

> [!IMPORTANT]
> In tutto il contenuto viene usato il termine *legacy* per fare riferimento all'legacy Lync Server 2013 o Skype for business server 2015 che si sta eseguendo la migrazione a Skype for business server 2019.
  
> [!IMPORTANT]
> Questa guida descrive i passaggi in genere necessari per completare ogni fase della migrazione. Non affronta tutte le possibili topologie di distribuzione legacy o ogni possibile scenario di migrazione. Di conseguenza, potrebbe non essere necessario eseguire ogni passaggio descritto oppure potrebbe essere necessario eseguire passaggi aggiuntivi, a seconda della distribuzione. Questa guida contiene anche esempi di passaggi di verifica. Questi passaggi di verifica vengono forniti per aiutarti a capire cosa è necessario cercare per verificare che ogni fase venga completata correttamente durante la migrazione. Adattare questi passaggi di verifica al processo di migrazione specifico. 
  
Questa guida fornisce informazioni specifiche per l'aggiornamento della distribuzione esistente. Non spiega come cambiare la topologia esistente. Questa guida non riguarda l'implementazione delle nuove caratteristiche. Quando una procedura dettagliata è documentata altrove, questa guida indica la sezione articolo o articolo. 
  
Questo articolo definisce i termini specificati nell'elenco seguente.
  
**migrazione:** Spostamento della distribuzione della produzione da Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.
    
**coesistenza:** L'ambiente temporaneo che esiste durante la migrazione quando alcune funzionalità sono state migrate in Skype for Business Server 2019 e altre funzionalità restano ancora in una versione precedente.
    
**interoperabilità:** La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.

**legacy:** Il sistema a cui si sta eseguendo la migrazione, ovvero Lync Server 2013 o Skype for Business Server 2015.
    
## <a name="in-this-section"></a>In questa sezione

- [Operazioni preliminari alla migrazione](before-you-begin-the-migration.md)
    
- [Fase 1: pianificare la migrazione](phase-1-plan-your-migration.md)
    
- [Fase 2: preparare la migrazione](phase-2-prepare-for-migration.md)
    
- [Fase 3: distribuire il pool pilota](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: trasferire gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Fase 5: aggiungere Edge Server al pool pilota](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: rimuovere le autorizzazioni dei pool legacy](phase-8-decommission-legacy-pools.md)
    

