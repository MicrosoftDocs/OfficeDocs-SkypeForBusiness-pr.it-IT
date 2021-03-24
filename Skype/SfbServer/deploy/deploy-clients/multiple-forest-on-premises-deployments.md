---
title: Skype Room System distribuzioni locali a più foreste
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
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093530"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="413ed-103">Skype Room System distribuzioni locali a più foreste</span><span class="sxs-lookup"><span data-stu-id="413ed-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="413ed-104">Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a più foreste.</span><span class="sxs-lookup"><span data-stu-id="413ed-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="413ed-105">Per la distribuzione in più foreste, Skype Room System richiede Exchange Server 2013 CU6 rilasciato il 26 agosto 2014.</span><span class="sxs-lookup"><span data-stu-id="413ed-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="413ed-106">Evitare di utilizzare di nuovo una cassetta postale esistente per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="413ed-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="413ed-107">Usa una nuova cassetta postale (elimina la vecchia cassetta postale e ri-crea) per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="413ed-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="413ed-108">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="413ed-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="413ed-109">Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="413ed-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="413ed-110">Per ulteriori dettagli, vedere i passaggi da 3 a 6 in Distribuzioni locali a foresta singola.</span><span class="sxs-lookup"><span data-stu-id="413ed-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="413ed-111">Dopo aver creato una cassetta postale delle risorse di Exchange per Skype Room System, abilitare l'account per Skype for Business seguendo la procedura descritta in Enabling Skype Room System Accounts for Skype for Business in Single forest on-premises deployments.</span><span class="sxs-lookup"><span data-stu-id="413ed-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="413ed-112">Opzione 1: creare una nuova cassetta postale per le risorse</span><span class="sxs-lookup"><span data-stu-id="413ed-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="413ed-113">Per distribuire Skype Room System in un ambiente a più foreste:</span><span class="sxs-lookup"><span data-stu-id="413ed-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="413ed-114">Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).</span><span class="sxs-lookup"><span data-stu-id="413ed-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="413ed-115">Eseguire i comandi seguenti in Exchange Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="413ed-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="413ed-116">Opzione 2: modificare una cassetta postale sala esistente in Cassetta postale delle risorse di Sistema sala Skype (collegato)</span><span class="sxs-lookup"><span data-stu-id="413ed-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```