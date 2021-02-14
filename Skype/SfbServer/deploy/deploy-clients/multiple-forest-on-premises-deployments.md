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
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="aafdc-103">Distribuzioni locali a più foreste di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="aafdc-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="aafdc-104">Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.</span><span class="sxs-lookup"><span data-stu-id="aafdc-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aafdc-105">Per la distribuzione in più foreste, Skype Room System richiede Exchange Server 2013 CU6 rilasciato il 26 agosto 2014.</span><span class="sxs-lookup"><span data-stu-id="aafdc-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="aafdc-106">Evitare di utilizzare di nuovo una cassetta postale esistente per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="aafdc-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="aafdc-107">Usare una nuova cassetta postale (eliminare la vecchia cassetta postale e creare di nuovo) la cassetta postale delle risorse per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="aafdc-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="aafdc-108">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [Connettere o ripristinare una cassetta postale eliminata.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aafdc-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="aafdc-109">Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="aafdc-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="aafdc-110">Per ulteriori dettagli, vedere i passaggi da 3 a 6 nelle distribuzioni locali a foresta singola.</span><span class="sxs-lookup"><span data-stu-id="aafdc-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="aafdc-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span><span class="sxs-lookup"><span data-stu-id="aafdc-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="aafdc-112">Opzione 1: creare una nuova cassetta postale per le risorse</span><span class="sxs-lookup"><span data-stu-id="aafdc-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="aafdc-113">Per distribuire Skype Room System in un ambiente a più foreste:</span><span class="sxs-lookup"><span data-stu-id="aafdc-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="aafdc-114">Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).</span><span class="sxs-lookup"><span data-stu-id="aafdc-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="aafdc-115">Eseguire i comandi seguenti in Exchange Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="aafdc-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="aafdc-116">Opzione 2: modificare una cassetta postale sala esistente in una cassetta postale delle risorse skype room (collegata)</span><span class="sxs-lookup"><span data-stu-id="aafdc-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


