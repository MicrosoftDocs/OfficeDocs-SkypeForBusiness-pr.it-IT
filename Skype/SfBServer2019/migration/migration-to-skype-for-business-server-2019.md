---
title: Migrazione a Skype for Business Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Gli argomenti di questa sezione guidano l'utente nel processo di migrazione a Skype for Business Server 2019.
ms.openlocfilehash: 6eb192c11ec8d1f44539e3bd5180249d85180d2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587978"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migrazione a Skype for Business Server 2019

Gli argomenti di questa sezione guidano l'utente nel processo di migrazione a Skype for Business Server 2019. In questo articolo viene illustrata la migrazione di Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.

> [!IMPORTANT]
> In tutto il contenuto viene utilizzato il termine *legacy* per fare riferimento all'legacy di Lync Server 2013 o Skype for Business Server 2015 di cui si esegue la migrazione a Skype for Business Server 2019.
  
> [!IMPORTANT]
> In questa guida vengono descritti i passaggi generalmente necessari per eseguire ogni fase della migrazione. Non tratta tutte le possibili topologie di distribuzione legacy o ogni possibile scenario di migrazione. Di conseguenza, potrebbe non essere necessario eseguire ogni passaggio descritto oppure potrebbe essere necessario eseguire passaggi aggiuntivi, a seconda della distribuzione. Questa guida fornisce anche esempi di passaggi di verifica. Questi passaggi di verifica vengono forniti per comprendere cosa è necessario cercare per assicurarsi che ogni fase sia completata correttamente man mano che si procede con la migrazione. Adattare questi passaggi di verifica al processo di migrazione specifico. 
  
In questa guida vengono fornite informazioni specifiche per l'aggiornamento della distribuzione esistente. Non viene spiegato come modificare la topologia esistente. In questa guida non viene illustrata l'implementazione di nuove funzionalità. Quando una procedura dettagliata viene documentata altrove, questa guida indirizza l'utente all'articolo o alla sezione dell'articolo. 
  
Questo articolo definisce i termini come specificato nell'elenco seguente.
  
**migrazione:** Spostamento della distribuzione di produzione da Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.
    
**coesistenza:** L'ambiente temporaneo esistente durante la migrazione quando è stata eseguita la migrazione di alcune funzionalità a Skype for Business Server 2019 e altre funzionalità rimangono ancora in una versione precedente.
    
**interoperabilità:** La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.

**legacy:** Il sistema da cui si sta eseguendo la migrazione, ovvero Lync Server 2013 o Skype for Business Server 2015.
    
## <a name="in-this-section"></a>Contenuto della sezione

- [Operazioni preliminari alla migrazione](before-you-begin-the-migration.md)
    
- [Fase 1: pianificare la migrazione](phase-1-plan-your-migration.md)
    
- [Fase 2: preparare la migrazione](phase-2-prepare-for-migration.md)
    
- [Fase 3: distribuire il pool pilota](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Fase 5: aggiungere Edge Server al pool pilota](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: rimuovere le autorizzazioni dei pool legacy](phase-8-decommission-legacy-pools.md)
    

