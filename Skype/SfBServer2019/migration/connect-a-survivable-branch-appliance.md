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
description: Ogni Survivable Branch Appliance (SBA) è associato a un pool Front End che funge da registrar di backup per l'SBA. Quando il pool Front End viene migrato a Skype for Business Server 2019, l'SBA deve essere disassociato dal pool Front End durante l'aggiornamento del pool, Dopo aver eseguito la migrazione del pool a Skype for Business Server 2019, l'SBA può essere nuovamente associato al pool Front End aggiornato. Ciò implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e quindi l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019. Gli utenti ospitati nell'SBA legacy devono prima essere spostati in un altro pool Front End prima di rimuovere l'SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Skype for Business Server 2019, questi utenti possono essere spostati di nuovo nell'SBA. La procedura è sintetizzata sotto.
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113342"
---
# <a name="connect-a-survivable-branch-appliance"></a>Connettere un Survivable Branch Appliance

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front End che funge da registrar di backup per l'SBA. Quando il pool Front End viene migrato a Skype for Business Server 2019, l'SBA deve essere disassociato dal pool Front End durante l'aggiornamento del pool. Dopo la migrazione del pool a Skype for Business Server 2019, l'SBA può essere nuovamente associato al pool Front End aggiornato. Ciò implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e quindi l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019. Gli utenti ospitati nell'SBA legacy devono prima essere spostati in un altro pool Front End prima di rimuovere l'SBA dalla topologia. Dopo l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019, tali utenti possono essere spostati di nuovo nell'SBA. La procedura è sintetizzata sotto.
  
1. Spostare gli utenti di succursale ospitati nell'SBA legacy in un altro pool Front End.
    
2. Rimuovere SBA dalla topologia legacy per disconnettere il pool Front End esistente come registrar di backup.
    
3. Aggiungere SBA alla topologia di Skype for Business Server 2019 e configurare questo nuovo pool Front End come registrar di backup. 
    
4. Spostare gli utenti di succursale nel nuovo Skype for Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Aggiungere un sito di succursale SBA legacy alla topologia

1. Aprire **Generatore di topologie**.
    
2. Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Siti di succursale** e quindi scegliere **Nuovo sito di succursale.**
    
3. Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.
    
4. (Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.
    
5. Fare clic su **Avanti**.
    
6. (Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti: 
    
    1. Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.
    
    2. Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.
    
    3. Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.
    
7. Fare **clic** su Avanti e quindi, se si utilizza un Survivable Branch Appliance o un Server in questo sito, deselezionare la casella di controllo Apri il Nuovo **Survivable Wizard** alla chiusura della procedura guidata. Fare clic su **Fine**.
    
8. Per associare l'SBA legacy al pool Front End di Skype for Business Server 2019:
    
    1. Espandere il sito di succursale che è stato creato. 
    
    2. Fare clic con il pulsante destro del mouse sulla versione legacy e quindi scegliere **Nuovo**.
    
    3. Fare **clic su Survivable Branch Appliance.**
    
9. Seguire le istruzioni nella procedura guidata visualizzata. Per informazioni sugli elementi della procedura guidata, vedere    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un Survivable Branch Appliance può essere associato solo a un archivio di monitoraggio. 
  
10. Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.
    
11. Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.
