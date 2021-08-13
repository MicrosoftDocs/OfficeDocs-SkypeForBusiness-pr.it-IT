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
description: Quando si esegue il cmdlet Move-CsUser, è possibile che si verifichi un errore perché le informazioni utente tra Servizi di dominio Active Directory e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio User Replicator di Skype for Business Server 2019 dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Skype for Business Server 2019. Il Skype for Business Server di sincronizzazione iniziale del servizio User Replicator 2019 si verifica quando il Front End Server Skype for Business Server 2019 viene avviato per la prima volta. Successivamente la sincronizzazione viene basata sull'intervallo di User Replicator. Eseguire la procedura seguente per verificare che la replica degli utenti sia completata prima di eseguire il cmdlet Move-CsUser.
ms.openlocfilehash: 0fe1c205b04ed32f5ac4281e555d5a44262905aa23b74eb69148d447337b59f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325683"
---
# <a name="verify-user-replication-has-completed"></a>Verificare il completamento della replica utente

Quando si esegue il cmdlet **Move-CsUser,** è possibile che si verifichi un errore se le informazioni utente tra Servizi di dominio Active Directory e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio User Replicator di Skype for Business Server 2019 dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Skype for Business Server 2019. Il Skype for Business Server di sincronizzazione iniziale del servizio User Replicator 2019 si verifica quando il Front End Server Skype for Business Server 2019 viene avviato per la prima volta. Successivamente, la sincronizzazione si basa sull'intervallo di User Replicator. Completare i passaggi seguenti per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet **Move-CsUser.** 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Per verificare che la replica degli utenti sia stata completata

1. Accedere al computer in cui è installato il Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Fare clic su **Start** e scegliere **Esegui**. 
    
3. Immettere **eventvwr.exe** e quindi fare clic su **OK**.
    
4. Nel Visualizzatore eventi fare **clic su Registri applicazioni** e servizi per espanderlo e quindi selezionare Skype for Business Server. 
    
5. Nel riquadro **Azioni** fare clic su **Filtro registro corrente**.
    
6. Nell'elenco **Origini eventi** fare clic su **LS User Replicator**.
    
7. In **\<All Event IDs\>** immettere **30024** e quindi fare clic su **OK.** 
    
8. Nella scheda Generale dell'elenco  degli eventi filtrati cercare una voce che indica che la replica degli utenti è stata completata correttamente. 
    

