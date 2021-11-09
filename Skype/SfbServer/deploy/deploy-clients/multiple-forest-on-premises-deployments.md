---
title: Skype Sistema sala distribuzioni locali a più foreste
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.
ms.openlocfilehash: 34b52f32ec3f1c611d8560c8f053e7fbe16b53bf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857044"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Sistema sala distribuzioni locali a più foreste
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.
  
> [!NOTE]
> Per la distribuzione in più foreste, Skype Room System richiede Exchange Server 2013 CU6 rilasciato il 26 agosto 2014. Evitare di utilizzare di nuovo una cassetta postale esistente per Skype Room System. Utilizzare una nuova cassetta postale (eliminare la cassetta postale precedente e ri-creare) per Skype room system. Per ripristinare le riunioni perse eliminando la cassetta postale, vedere Connessione [o ripristinare una cassetta postale eliminata.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing per configurare la cassetta postale. Per ulteriori dettagli, vedere i passaggi da 3 a 6 in Distribuzioni locali a foresta singola. Dopo aver creato una cassetta postale risorsa Exchange per Skype Room System, abilitare l'account per Skype for Business seguendo la procedura descritta in Enabling Skype Room System Accounts for Skype for Business in Single forest on-premises deployments.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opzione 1: creare una nuova cassetta postale per le risorse

Per distribuire Skype Room System in un ambiente a più foreste:
  
1. Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).
    
2. Eseguire i comandi seguenti in Exchange Server Management Shell:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opzione 2: modificare una cassetta postale sala esistente Skype cassetta postale della risorsa (collegata) del sistema room

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```