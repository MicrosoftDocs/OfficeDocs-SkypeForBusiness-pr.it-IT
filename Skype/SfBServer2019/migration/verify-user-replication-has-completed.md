---
title: Verificare il completamento della replica utente
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
description: Quando si esegue il cmdlet Move-CsUser, è possibile che si verifichi un errore perché le informazioni utente tra servizi di dominio Active Directory (AD DS) e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Skype for Business Server 2019 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Skype for Business Server 2019. Il processo di sincronizzazione iniziale di Skype for Business Server 2019 User Replicator viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta. Successivamente la sincronizzazione viene basata sull'intervallo di User Replicator. Eseguire la procedura seguente per verificare che la replica degli utenti sia completata prima di eseguire il cmdlet Move-CsUser.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751648"
---
# <a name="verify-user-replication-has-completed"></a>Verificare il completamento della replica utente

Quando si esegue il cmdlet **Move-CsUser** , è possibile che si verifichi un errore se le informazioni utente tra servizi di dominio Active Directory (ad DS) e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Skype for Business Server 2019 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Skype for Business Server 2019. Il processo di sincronizzazione iniziale di Skype for Business Server 2019 User Replicator viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta. Successivamente, la sincronizzazione si basa sull'intervallo User Replicator. Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Per verificare che la replica degli utenti sia stata completata

1. Accedere al computer in cui è installato il Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Fare clic su **Start** e scegliere **Esegui**. 
    
3. Immettere **eventvwr.exe** e quindi fare clic su **OK**.
    
4. In Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Skype for Business Server. 
    
5. Nel riquadro **Azioni** fare clic su **Filtro registro corrente**.
    
6. Nell'elenco **Origini eventi** fare clic su **LS User Replicator**.
    
7. In **\<All Event IDs\>** immettere **30024**e quindi fare clic su **OK**. 
    
8. Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente. 
    

