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
description: Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. È possibile modificare le proprietà del pool Front End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza e aver eliminato il server in Generatore di topologie, viene notificato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752138"
---
# <a name="remove-the-archiving-server-association"></a>Rimuovere l'associazione del server di archiviazione

Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. È possibile modificare le proprietà del pool Front End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
  
### <a name="to-remove-the-archiving-server-association"></a>Per rimuovere un'associazione a un server di archiviazione

1. Nel server front end di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. Passare al nodo di installazione legacy.
    
3. In Generatore di topologie espandere **pool Enterprise Edition front end**, **Standard Edition Front End Server**o **siti di succursale**a seconda di dove è definito il server di archiviazione.
    
4. Se è presente un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito di succursale e quindi espandere **Survivable Branch Appliance**.
    
    > [!NOTE]
    > **Survivable Branch Appliance** nell'interfaccia utente si applica sia a Survivable Branch Server che a Survivable Branch Appliance. 
  
5. Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione, quindi scegliere **modifica proprietà**.
    
6. In **modifica proprietà**, in **General**  >  **associazioni**generali, deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.
    
7. Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si desidera rimuovere.
    
8. Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.
    
9. In **Elimina archivi dipendenti** fare clic su **OK**.
    
10. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze. 
    

