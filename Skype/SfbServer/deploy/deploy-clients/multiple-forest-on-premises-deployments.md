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
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="43dc9-103">Distribuzioni locali di più foreste di Skype room System</span><span class="sxs-lookup"><span data-stu-id="43dc9-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="43dc9-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente a più foreste locale.</span><span class="sxs-lookup"><span data-stu-id="43dc9-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43dc9-105">Per poter eseguire la distribuzione in più foreste, Skype room System richiede Exchange Server 2013 CU6 rilasciati il 26 agosto 2014.</span><span class="sxs-lookup"><span data-stu-id="43dc9-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="43dc9-106">Evitare di riutilizzare una cassetta postale esistente per Skype room System.</span><span class="sxs-lookup"><span data-stu-id="43dc9-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="43dc9-107">Utilizzo di una nuova cassetta postale per la risorsa di Skype (Elimina vecchia cassetta postale e ricreata) per il sistema in chat.</span><span class="sxs-lookup"><span data-stu-id="43dc9-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="43dc9-108">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="43dc9-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="43dc9-109">Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="43dc9-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="43dc9-110">Per ulteriori informazioni, fare riferimento ai passaggi da 3 a 6 nelle distribuzioni locali di una foresta singola.</span><span class="sxs-lookup"><span data-stu-id="43dc9-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="43dc9-111">Dopo aver creato una cassetta postale per le risorse di Exchange per Skype room System, abilitare l'account per Skype for business seguendo i passaggi descritti in Abilitazione degli account di sistema in chat room di Skype for business in distribuzioni locali in una foresta singola.</span><span class="sxs-lookup"><span data-stu-id="43dc9-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="43dc9-112">Opzione 1: creare una nuova cassetta postale per la risorsa</span><span class="sxs-lookup"><span data-stu-id="43dc9-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="43dc9-113">Per distribuire Skype room System in un ambiente con più foreste:</span><span class="sxs-lookup"><span data-stu-id="43dc9-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="43dc9-114">Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).</span><span class="sxs-lookup"><span data-stu-id="43dc9-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="43dc9-115">Eseguire i seguenti comandi in Exchange Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="43dc9-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="43dc9-116">Opzione 2: modificare una cassetta postale della sala esistente nella cassetta postale delle risorse di Skype room System (collegata)</span><span class="sxs-lookup"><span data-stu-id="43dc9-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


