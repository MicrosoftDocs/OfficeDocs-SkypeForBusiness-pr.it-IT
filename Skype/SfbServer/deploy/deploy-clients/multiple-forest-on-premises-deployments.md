---
title: Skype Sistema sala distribuzioni locali a più foreste
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
ms.openlocfilehash: dc1d7fa3a3ca7cbcf62f7c038fb8fd6b4fcedc84319452ec8eaf02781f311bf3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310065"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Sistema sala distribuzioni locali a più foreste
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.
  
> [!NOTE]
> Per la distribuzione in più foreste, Skype Room System richiede Exchange Server 2013 CU6 rilasciato il 26 agosto 2014. Evitare di utilizzare nuovamente una cassetta postale esistente per Skype Room System. Utilizzare una nuova cassetta postale (eliminare la cassetta postale precedente e ri-creare) per Skype Room System. Per ripristinare le riunioni perse eliminando la cassetta postale, vedere Connessione [o ripristinare una cassetta postale eliminata.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
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