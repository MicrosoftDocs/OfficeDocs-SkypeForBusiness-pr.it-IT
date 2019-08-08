---
title: Verificare che la replica degli utenti sia stata completata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando si esegue il cmdlet Move-CsUser, è possibile che si verifichi un errore perché le informazioni degli utenti tra servizi di dominio Active Directory e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per completare correttamente la sincronizzazione iniziale di Skype for Business Server 2019, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospitano Skype for business Pool di server 2019. Il processo di sincronizzazione iniziale di Skype for Business Server 2019 viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta. Successivamente, la sincronizzazione si basa sull'intervallo User Replicator. Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet Move-CsUser.
ms.openlocfilehash: 12bb3c29f703287934358f331dc945830e318afb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244028"
---
# <a name="verify-user-replication-has-completed"></a>Verificare che la replica degli utenti sia stata completata

Quando si esegue il cmdlet **Move-CsUser** , potrebbe verificarsi un errore se le informazioni degli utenti tra servizi di dominio Active Directory e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per completare correttamente la sincronizzazione iniziale di Skype for Business Server 2019, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospitano Skype for business Pool di server 2019. Il processo di sincronizzazione iniziale di Skype for Business Server 2019 viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta. In seguito, la sincronizzazione si basa sull'intervallo User Replicator. Completare la procedura seguente per verificare che la replica dell'utente sia stata completata prima di eseguire il cmdlet **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Per verificare che la replica dell'utente sia stata completata

1. Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Fare clic sul menu **Start** e quindi su **Esegui**. 
    
3. Immettere **eventvwr. exe**e quindi fare clic su **OK**.
    
4. Nel Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Skype for Business Server. 
    
5. Nel riquadro **azioni** fare clic su **Filtra log corrente**.
    
6. Nell'elenco **origini eventi** fare clic su **LS User Replicator**.
    
7. In ** \<tutti gli ID\>evento**immettere **30024**e quindi fare clic su **OK**. 
    
8. Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente. 
    

