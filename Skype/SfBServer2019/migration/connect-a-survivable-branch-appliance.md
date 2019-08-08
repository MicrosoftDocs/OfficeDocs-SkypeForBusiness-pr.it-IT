---
title: Connettere un Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Ogni Survivable Branch Appliance (SBA) è associato a un pool Front-end che funge da registrar di backup per l'SBA. Quando viene eseguita la migrazione del pool Front-end a Skype for Business Server 2019, l'SBA deve essere dissociato dal pool Front-end mentre il pool viene aggiornato, dopo la migrazione del pool a Skype for Business Server 2019, l'SBA può essere riassociato all'aggiornamento anteriore E pool ND. Questo comporta l'eliminazione della SBA dalla topologia legacy in Generatore di topologie e l'aggiunta della SBA alla topologia di Skype for Business Server 2019. Gli utenti residenti nell'ASB legacy devono prima essere spostati in un altro pool Front end prima di rimuovere l'SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Skype for Business Server 2019, questi utenti possono quindi essere spostati di nuovo nella SBA. Questi passaggi sono riepilogati di seguito:"
ms.openlocfilehash: e5545a2de4eddd65790f425ab888b8fd07faf970
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239549"
---
# <a name="connect-a-survivable-branch-appliance"></a>Connettere un Survivable Branch Appliance

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per l'SBA. Quando il pool Front-end viene migrato in Skype for Business Server 2019, l'SBA deve essere dissociato dal pool Front-end mentre il pool viene aggiornato. Dopo la migrazione del pool a Skype for Business Server 2019, l'SBA può essere riassociato al pool Front-end aggiornato. Questo comporta l'eliminazione della SBA dalla topologia legacy in Generatore di topologie e l'aggiunta della SBA alla topologia di Skype for Business Server 2019. Gli utenti residenti nell'ASB legacy devono prima essere spostati in un altro pool Front end prima di rimuovere l'SBA dalla topologia. Dopo l'aggiunta della SBA alla topologia di Skype for Business Server 2019, gli utenti possono essere spostati di nuovo nella SBA. Questi passaggi sono riepilogati di seguito:
  
1. Sposta gli utenti della filiale nella SBA legacy in un altro pool Front-end.
    
2. Rimuovi SBA dalla topologia legacy per disconnettere il pool Front end esistente come registrar di backup.
    
3. Aggiungere SBA alla topologia di Skype for Business Server 2019 e configurare il nuovo pool Front-end come registrar di backup. 
    
4. Trasferire gli utenti della filiale nel nuovo SBA di Skype for Business Server 2019.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Aggiungere il sito della filiale SBA legacy alla topologia

1. Aprire **Generatore**di topologie.
    
2. Nel riquadro sinistro fare clic con il pulsante destro del mouse su **siti**di succursale e quindi scegliere **nuovo sito filiale**.
    
3. Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare il nome del sito della filiale.
    
4. Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.
    
5. Fare clic su **Avanti**.
    
6. Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti: 
    
    1. Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.
    
    2. Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.
    
    3. Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.
    
7. Fare clic su **Avanti**e quindi, se si usa un Survivable Branch Appliance o un server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata** per la procedura guidata. Fare clic su **fine**.
    
8. Per associare la SBA legacy al pool di front end di Skype for Business Server 2019:
    
    1. Espandere il sito della filiale che è stato creato. 
    
    2. Fare clic con il pulsante destro del mouse sulla versione legacy e quindi scegliere **nuovo**.
    
    3. Fare clic su **Survivable Branch Appliance**.
    
9. Seguire le indicazioni della procedura guidata visualizzata. Per informazioni sugli elementi della procedura guidata, vedere    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un Survivable Branch Appliance può essere associato solo a un archivio di monitoraggio. 
  
10. Se non si usa un Survivable Branch Appliance o un server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata e quindi fare clic su **fine**.
    
11. Ripetere i passaggi precedenti per ogni sito di filiale che si vuole aggiungere alla topologia.
    

