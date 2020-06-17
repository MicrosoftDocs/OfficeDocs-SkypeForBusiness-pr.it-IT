---
title: Connettere un Survivable Branch Appliance
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
description: Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per la SBA. Quando si esegue la migrazione del pool Front end su Skype for Business Server 2019, è necessario che l'SBA sia dissociata dal pool Front end quando il pool viene aggiornato, una volta che il pool è stato migrato su Skype for Business Server 2019, l'SBA può essere riassociato al pool Front end aggiornato. Questo implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019. Gli utenti ospitati nell'ASB legacy devono essere prima spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Skype for Business Server 2019, gli utenti possono quindi essere spostati di nuovo nell'ASB. La procedura è sintetizzata sotto.
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751548"
---
# <a name="connect-a-survivable-branch-appliance"></a>Connettere un Survivable Branch Appliance

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per la SBA. Quando si esegue la migrazione del pool Front end in Skype for Business Server 2019, è necessario che l'SBA sia dissociata dal pool Front end mentre il pool viene aggiornato. Dopo la migrazione del pool a Skype for Business Server 2019, l'SBA può essere riassociato al pool Front end aggiornato. Questo implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019. Gli utenti ospitati nell'ASB legacy devono essere prima spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia. Dopo aver aggiunto la SBA alla topologia di Skype for Business Server 2019, gli utenti possono essere spostati di nuovo nell'ASB. La procedura è sintetizzata sotto.
  
1. Spostare gli utenti di succursale nell'ASB legacy in un altro pool Front end.
    
2. Rimuovere SBA dalla topologia legacy per disconnettere il pool Front end esistente come un servizio di registrazione di backup.
    
3. Aggiungere SBA alla topologia di Skype for Business Server 2019 e configurare questo nuovo pool Front end come registrazione di backup. 
    
4. Spostare gli utenti di succursale nel nuovo SBA di Skype for Business Server 2019.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Aggiungere un sito di succursale SBA legacy alla topologia

1. Aprire **Generatore di topologie**.
    
2. Nel riquadro sinistro fare clic con il pulsante destro del mouse su **siti di succursale**e quindi scegliere **nuovo sito di succursale**.
    
3. Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.
    
4. (Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.
    
5. Fare clic su **Avanti**.
    
6. (Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti: 
    
    1. Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.
    
    2. Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.
    
    3. Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.
    
7. Fare clic su **Avanti**e quindi, se si utilizza un Survivable Branch Appliance o server in questo sito, deselezionare la casella di controllo **aprire la procedura guidata nuovo Survivable Wizard quando la procedura guidata viene chiusa** . Fare clic su **Fine**.
    
8. Per associare l'ASB legacy al pool Front End di Skype for Business Server 2019:
    
    1. Espandere il sito di succursale che è stato creato. 
    
    2. Fare clic con il pulsante destro del mouse sulla versione legacy e quindi scegliere **nuovo**.
    
    3. Fare clic su **Survivable Branch Appliance**.
    
9. Seguire le istruzioni nella procedura guidata visualizzata. Per informazioni sugli elementi della procedura guidata, vedere    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un Survivable Branch Appliance può essere associato solo a un archivio di monitoraggio. 
  
10. Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.
    
11. Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.
    

