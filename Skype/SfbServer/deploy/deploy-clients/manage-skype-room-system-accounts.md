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
description: Leggere questo argomento per informazioni su come gestire gli account di sistema di Skype room.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805556"
---
# <a name="manage-skype-room-system-accounts"></a>Gestire gli account Skype Room System
 
Leggere questo argomento per informazioni su come gestire gli account di sistema di Skype room. 

> [!NOTE]
> Microsoft teams Rooms è un prodotto diverso con diverse dipendenze e procedure di distribuzione. Per informazioni sulle sale di Microsoft teams, vedere la [panoramica sulla gestione](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)di Microsoft teams rooms.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Spostare l'account di sistema della sala Skype tra pool

Se è necessario spostare l'account del sistema di chat room Skype da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), utilizzare il seguente comando per spostare il pool di account di sistema di Skype room System: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Disabilitare l'account di sistema della sala Skype per i servizi Skype for business

Se è necessario disabilitare un account Skype for business per il sistema di chat room esistente su un pool di Skype for Business Server, utilizzare il seguente comando per disabilitare l'account: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facoltativo: creare un gruppo di amministratori di sistema di Skype room in Active Directory

Ogni client del sistema Skype room che unisce il dominio può essere completamente gestito da un utente di dominio con diritti di amministratore locale sul PC di Skype room System Appliance. Pertanto, è possibile creare un gruppo di amministratori dedicato in Active Directory e concedere a questo gruppo i diritti amministrativi durante la configurazione del nuovo computer del sistema Skype room.
  

