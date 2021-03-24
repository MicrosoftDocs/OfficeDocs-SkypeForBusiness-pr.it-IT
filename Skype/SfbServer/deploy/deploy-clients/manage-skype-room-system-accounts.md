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
description: Leggere questo argomento per informazioni su come gestire gli account di sistema sala Skype.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093294"
---
# <a name="manage-skype-room-system-accounts"></a>Gestire gli account Skype Room System
 
Leggere questo argomento per informazioni su come gestire gli account di sistema sala Skype. 

> [!NOTE]
> Microsoft Teams Rooms è un prodotto diverso con dipendenze e procedure di distribuzione diverse. Per informazioni su Microsoft Teams Rooms, vedere panoramica sulla gestione di Microsoft Teams [Rooms.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Spostare l'account di sistema skype room tra pool

Se è necessario spostare l'account di sistema sala Skype da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), utilizzare il comando seguente per spostare il pool di account di sistema Skype Room: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Disabilitare l'account di sistema sala Skype per i servizi Skype for Business

Se è necessario disabilitare un account di sistema Skype Room esistente dai servizi Skype for Business in un pool di Skype for Business Server, utilizzare il comando seguente per disabilitare l'account: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facoltativo: creare un gruppo di amministratori di Sistema sala Skype in Active Directory

Ogni client di Sistema sala Skype che si aggiunge al dominio può essere gestito completamente da un utente di dominio con diritti di amministratore locale nel PC dell'appliance Skype Room System. Pertanto, puoi creare un gruppo di amministratori dedicato in Active Directory e assegnare a questo gruppo i diritti amministrativi durante la configurazione del nuovo computer Skype Room System.
