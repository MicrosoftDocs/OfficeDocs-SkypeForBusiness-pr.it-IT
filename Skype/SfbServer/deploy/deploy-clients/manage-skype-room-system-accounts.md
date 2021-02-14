---
title: Gestire gli account Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leggi questo argomento per informazioni su come gestire gli account di Skype Room System.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805556"
---
# <a name="manage-skype-room-system-accounts"></a>Gestire gli account Skype Room System
 
Leggi questo argomento per informazioni su come gestire gli account di Skype Room System. 

> [!NOTE]
> Microsoft Teams Rooms è un prodotto diverso con dipendenze e procedure di distribuzione diverse. Per informazioni su Microsoft Teams Rooms, vedere la panoramica sulla gestione di Microsoft Teams [Rooms.](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Spostare l'account skype room system tra pool

Se è necessario spostare l'account di Skype Room System da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), utilizzare il comando seguente per spostare il pool di account di Skype Room System: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Disabilitare l'account skype room system per i servizi Skype for Business

Se è necessario disabilitare un account Skype Room System esistente dai servizi Skype for Business in un pool di Skype for Business Server, utilizzare il seguente comando per disabilitare l'account: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facoltativo: creare un gruppo di amministratori di Skype Room System in Active Directory

Ogni client Skype Room System che si unisce al dominio può essere gestito completamente da un utente di dominio con diritti di amministratore locale sul PC dell'appliance Skype Room System. Pertanto, è possibile creare un gruppo di amministratori dedicato in Active Directory e assegnare a questo gruppo i diritti amministrativi durante la configurazione del nuovo computer Skype Room System.
  

