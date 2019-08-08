---
title: Rimuovere l'associazione del server di archiviazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Per rimuovere un server di archiviazione, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene visualizzato un avviso che l'oggetto archivio di database associato in Generatore di topologia verrà eliminata.
ms.openlocfilehash: d6d7b7f53f9997b17893db079090e1837ce77f4d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244428"
---
# <a name="remove-the-archiving-server-association"></a>Rimuovere l'associazione del server di archiviazione

Per rimuovere un server di archiviazione, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.
  
### <a name="to-remove-the-archiving-server-association"></a>Per rimuovere l'associazione del server di archiviazione

1. Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.
    
2. Passare al nodo di installazione legacy.
    
3. In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti**di succursale, a seconda della posizione in cui è definito il server di archiviazione.
    
4. Se si ha un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.
    
    > [!NOTE]
    > Gli **elettrodomestici Survivable Branch** nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance. 
  
5. Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione e quindi scegliere **modifica proprietà**.
    
6. In **modifica proprietà**, in **** > **associazioni**generali, deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.
    
7. Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si vuole rimuovere.
    
8. Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.
    
9. In **eliminare gli archivi dipendenti**fare clic su **OK**.
    
10. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze. 
    

