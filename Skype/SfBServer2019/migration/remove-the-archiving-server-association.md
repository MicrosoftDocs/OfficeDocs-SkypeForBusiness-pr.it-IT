---
title: Rimuovere l'associazione del server di archiviazione
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
description: Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati. È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza e aver eliminato il server in Generatore di topologie, viene notificato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
ms.openlocfilehash: 6265642a45b891180e53d3b00d39a9053b663a434aaa1a4a26e92b619dfba257
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340332"
---
# <a name="remove-the-archiving-server-association"></a>Rimuovere l'associazione del server di archiviazione

Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati. È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, viene notificato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
  
### <a name="to-remove-the-archiving-server-association"></a>Per rimuovere un'associazione a un server di archiviazione

1. Nel Front End Server Skype for Business Server 2019 aprire Generatore di topologie.
    
2. Passare al nodo di installazione legacy.
    
3. In Generatore di topologie espandere **edizione Enterprise pool Front End,** edizione Standard Front End Server o Siti di succursale, **a** seconda della posizione in cui è definito il server di archiviazione. 
    
4. Se è associato un Survivable Branch Server, espandere **Siti** di succursale, espandere il nome del sito di succursale e quindi **Espandere Survivable Branch Appliance.**
    
    > [!NOTE]
    > **I Survivable Branch Appliance nell'interfaccia** utente si applicano sia al Survivable Branch Server che al Survivable Branch Appliance. 
  
5. Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione e quindi scegliere **Modifica proprietà**.
    
6. In **Modifica proprietà,** in **Associazioni**  >  **generali,** deselezionare la **casella di controllo** Associa server di archiviazione e quindi fare clic su **OK.**
    
7. Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si desidera rimuovere.
    
8. Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina.**
    
9. In **Elimina archivi dipendenti** fare clic su **OK**.
    
10. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Skype for Business Server distribuzione guidata in base alle esigenze. 
    

