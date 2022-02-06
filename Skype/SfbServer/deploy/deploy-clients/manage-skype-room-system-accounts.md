---
title: Gestire gli account Skype Room System
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leggere questo argomento per informazioni su come gestire Skype di sistema room.
---

# <a name="manage-skype-room-system-accounts"></a>Gestire gli account Skype Room System
 
Leggere questo argomento per informazioni su come gestire Skype di sistema room. 

> [!NOTE]
> Microsoft Teams Rooms è un prodotto diverso con dipendenze e procedure di distribuzione diverse. Per informazioni sulle Microsoft Teams Rooms, vedere panoramica Microsoft Teams Rooms [gestione dei dati](/microsoftteams/rooms/rooms-manage).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Spostare l'account Skype room tra pool

Se è necessario spostare l'account di Skype Room System da un pool di Skype for Business Server Skype for Business Server a un altro , ad esempio durante gli aggiornamenti, utilizzare il comando seguente per spostare il pool di account di Skype Room System: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Disabilitare l'account Skype Room System per Skype for Business servizi

Se è necessario disabilitare un account Skype Room System esistente dai servizi Skype for Business in un pool di Skype for Business Server, utilizzare il comando seguente per disabilitare l'account: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facoltativo: creare un Skype amministratore del sistema room in Active Directory

Ogni Skype del sistema room che si aggiunge al dominio può essere gestito completamente da un utente di dominio con diritti di amministratore locale nel PC dell'appliance Skype Room System. Pertanto, è possibile creare un gruppo di amministratori dedicato in Active Directory e assegnare a questo gruppo i diritti amministrativi durante la configurazione del nuovo computer Skype Room System.
