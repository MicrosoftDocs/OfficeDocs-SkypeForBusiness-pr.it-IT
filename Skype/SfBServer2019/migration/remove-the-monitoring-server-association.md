---
title: Rimuovere l'associazione del server di monitoraggio
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
description: Per rimuovere il Monitoring Server, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati. È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, si riceve una notifica che indica che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753418"
---
# <a name="remove-the-monitoring-server-association"></a>Rimuovere l'associazione del server di monitoraggio

Per rimuovere il Monitoring Server, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati. È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, si riceve una notifica che indica che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
  
### <a name="to-remove-the-monitoring-server-association"></a>Per rimuovere l'associazione del Monitoring Server

1. Nel Front End Server di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. Passare al nodo delle installazioni legacy.
    
3. In Generatore di topologie espandere Pool **Enterprise Edition Front End,** **Standard Edition Front End Server** o siti di succursale, a seconda della posizione in cui è definito il Monitoring Server.
    
4. Se è associato un Survivable Branch Server, espandere Siti di succursale, espandere il nome del sito di succursale e quindi **espandere Survivable Branch Appliance.**
    
    > [!NOTE]
    > **I Survivable Branch Appliance nell'interfaccia** utente si applicano sia al Survivable Branch Server che al Survivable Branch Appliance. 
  
5. Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al Monitoring Server e quindi scegliere **Modifica proprietà.**
    
6. In **Modifica proprietà,** in **Associazioni**  >  **generali,** deselezionare la **casella di** controllo Associa Monitoring Server e quindi fare clic su **OK.**
    
7. Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al Monitoring Server.
    
8. Fare clic con il pulsante destro del mouse sul Monitoring Server e quindi scegliere **Elimina.** 
    
9. In **Elimina archivi dipendenti** fare clic su **OK**.
    
10. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata di Skype for Business Server in base alle esigenze. 
    

