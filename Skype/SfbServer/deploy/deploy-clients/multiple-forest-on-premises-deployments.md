---
title: Skype room System più distribuzioni locali della foresta
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più foreste locale.
ms.openlocfilehash: 7de5d285f36ddd1060ba53aa3e142a09a5d421e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234199"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype room System più distribuzioni locali della foresta
 
Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più foreste locale.
  
> [!NOTE]
> Per la distribuzione in più foreste, Skype room System richiede Exchange Server 2013 CU6 rilasciati il 26 agosto 2014. Evitare di riutilizzare una cassetta postale esistente per Skype room System. Usa una nuova cassetta postale delle risorse (Elimina la vecchia cassetta postale e ricrea) per Skype room System. Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Dopo aver creato la cassetta postale, è possibile usare Set-CalendarProcessing per configurare la cassetta postale. Vedere i passaggi da 3 a 6 in distribuzioni locali di una singola foresta per maggiori dettagli. Dopo aver creato una cassetta postale di Exchange per Skype room System, abilitare l'account per Skype for business seguendo la procedura descritta in Abilitazione degli account di sistema per Skype room per Skype for business in distribuzioni locali in una singola foresta.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opzione 1: creare una nuova cassetta postale per le risorse

Per distribuire Skype room System in un ambiente con più foreste:
  
1. Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).
    
2. Eseguire i comandi seguenti in Exchange Server Management Shell:
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opzione 2: cambiare una cassetta postale della sala esistente nella cassetta postale delle risorse di Skype room System (collegata)

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


