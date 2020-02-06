---
title: Rimuovere l'associazione del server di monitoraggio
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
description: Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.
ms.openlocfilehash: aed16d60fbdae2413cb7890e38895bf6930cd4fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812864"
---
# <a name="remove-the-monitoring-server-association"></a>Rimuovere l'associazione del server di monitoraggio

Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.
  
### <a name="to-remove-the-monitoring-server-association"></a>Per rimuovere l'associazione del server di monitoraggio

1. Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.
    
2. Passare al nodo installazioni legacy.
    
3. In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti di succursale**, a seconda di dove è definito il server di monitoraggio.
    
4. Se si ha un Survivable Branch Server associato, espandere **siti di succursale**, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.
    
    > [!NOTE]
    > Gli **elettrodomestici Survivable Branch** nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance. 
  
5. Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di monitoraggio e quindi scegliere **modifica proprietà**.
    
6. In **modifica proprietà**, in **** > **associazioni**generali, deselezionare la casella di controllo **Associa server di monitoraggio** e quindi fare clic su **OK**.
    
7. Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di monitoraggio.
    
8. Fare clic con il pulsante destro del mouse sul server di monitoraggio e quindi scegliere **Elimina**. 
    
9. In **eliminare gli archivi dipendenti**fare clic su **OK**.
    
10. Pubblicare la topologia, controllare lo stato di replica ed eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze. 
    

