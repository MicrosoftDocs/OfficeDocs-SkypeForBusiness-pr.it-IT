---
title: Distribuzioni locali a più foreste di Skype Room System
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
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805746"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Distribuzioni locali a più foreste di Skype Room System
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.
  
> [!NOTE]
> Per la distribuzione in più foreste, Skype Room System richiede Exchange Server 2013 CU6 rilasciato il 26 agosto 2014. Evitare di utilizzare di nuovo una cassetta postale esistente per Skype Room System. Usare una nuova cassetta postale (eliminare la vecchia cassetta postale e creare di nuovo) la cassetta postale delle risorse per Skype Room System. Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [Connettere o ripristinare una cassetta postale eliminata.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing per configurare la cassetta postale. Per ulteriori dettagli, vedere i passaggi da 3 a 6 nelle distribuzioni locali a foresta singola. After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opzione 1: creare una nuova cassetta postale per le risorse

Per distribuire Skype Room System in un ambiente a più foreste:
  
1. Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).
    
2. Eseguire i comandi seguenti in Exchange Server Management Shell:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opzione 2: modificare una cassetta postale sala esistente in una cassetta postale delle risorse skype room (collegata)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


