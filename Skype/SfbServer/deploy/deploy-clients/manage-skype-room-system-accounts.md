---
title: Gestire gli account di sistema per Skype room
ms.author: v-lanac
author: lanachin
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
description: Leggi questo argomento per informazioni su come gestire gli account di Skype room System.
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768659"
---
# <a name="manage-skype-room-system-accounts"></a>Gestire gli account di sistema per Skype room
 
Leggi questo argomento per informazioni su come gestire gli account di Skype room System. 

> [!NOTE]
> Microsoft teams Rooms è un prodotto diverso con diverse dipendenze e procedure di distribuzione. Per informazioni su Microsoft teams rooms, vedere la panoramica sulla [gestione](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)di Microsoft teams rooms.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Trasferire l'account di sistema room Skype tra i pool

Se è necessario trasferire l'account di sistema della sala Skype da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), usare il comando seguente per trasferire il pool di account di sistema room Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Disabilitare l'account Skype room System per i servizi Skype for business

Se devi disabilitare un account di sistema room Skype esistente da Skype for Business Services in un pool di Skype for Business Server, usa il comando seguente per disabilitare l'account: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facoltativo: creare un gruppo di amministratori di sistema per Skype room in Active Directory

Ogni client di sistema room Skype che unisce il dominio può essere completamente gestito da un utente di dominio con diritti di amministratore locale nel PC di Skype room System Appliance. È quindi possibile creare un gruppo di amministratori dedicati in Active Directory e assegnare questo gruppo ai diritti amministrativi durante la configurazione del nuovo computer per la sala di Skype.
  

