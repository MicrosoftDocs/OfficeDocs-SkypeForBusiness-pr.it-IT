---
title: Distribuzioni locali di più foreste di Skype room System
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
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente a più foreste locale.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805746"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Distribuzioni locali di più foreste di Skype room System
 
Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente a più foreste locale.
  
> [!NOTE]
> Per poter eseguire la distribuzione in più foreste, Skype room System richiede Exchange Server 2013 CU6 rilasciati il 26 agosto 2014. Evitare di riutilizzare una cassetta postale esistente per Skype room System. Utilizzo di una nuova cassetta postale per la risorsa di Skype (Elimina vecchia cassetta postale e ricreata) per il sistema in chat. Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing per configurare la cassetta postale. Per ulteriori informazioni, fare riferimento ai passaggi da 3 a 6 nelle distribuzioni locali di una foresta singola. Dopo aver creato una cassetta postale per le risorse di Exchange per Skype room System, abilitare l'account per Skype for business seguendo i passaggi descritti in Abilitazione degli account di sistema in chat room di Skype for business in distribuzioni locali in una foresta singola.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opzione 1: creare una nuova cassetta postale per la risorsa

Per distribuire Skype room System in un ambiente con più foreste:
  
1. Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).
    
2. Eseguire i seguenti comandi in Exchange Server Management Shell:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opzione 2: modificare una cassetta postale della sala esistente nella cassetta postale delle risorse di Skype room System (collegata)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


