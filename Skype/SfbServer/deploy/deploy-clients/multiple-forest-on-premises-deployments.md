---
title: Skype room System più distribuzioni locali della foresta
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più foreste locale.
ms.openlocfilehash: ae51ac035ef618464f408cb3f068e142eb67f2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194439"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="09a56-103">Skype room System più distribuzioni locali della foresta</span><span class="sxs-lookup"><span data-stu-id="09a56-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="09a56-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più foreste locale.</span><span class="sxs-lookup"><span data-stu-id="09a56-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09a56-105">Per la distribuzione in più foreste, Skype room System richiede Exchange Server 2013 CU6 rilasciati il 26 agosto 2014.</span><span class="sxs-lookup"><span data-stu-id="09a56-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="09a56-106">Evitare di riutilizzare una cassetta postale esistente per Skype room System.</span><span class="sxs-lookup"><span data-stu-id="09a56-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="09a56-107">Usa una nuova cassetta postale delle risorse (Elimina la vecchia cassetta postale e ricrea) per Skype room System.</span><span class="sxs-lookup"><span data-stu-id="09a56-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="09a56-108">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="09a56-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="09a56-109">Dopo aver creato la cassetta postale, è possibile usare Set-CalendarProcessing per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="09a56-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="09a56-110">Vedere i passaggi da 3 a 6 in distribuzioni locali di una singola foresta per maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="09a56-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="09a56-111">Dopo aver creato una cassetta postale di Exchange per Skype room System, abilitare l'account per Skype for business seguendo la procedura descritta in Abilitazione degli account di sistema per Skype room per Skype for business in distribuzioni locali in una singola foresta.</span><span class="sxs-lookup"><span data-stu-id="09a56-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="09a56-112">Opzione 1: creare una nuova cassetta postale per le risorse</span><span class="sxs-lookup"><span data-stu-id="09a56-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="09a56-113">Per distribuire Skype room System in un ambiente con più foreste:</span><span class="sxs-lookup"><span data-stu-id="09a56-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="09a56-114">Creare un utente collegato (LinkedRoomTest) in Active Directory (foresta di autenticazione).</span><span class="sxs-lookup"><span data-stu-id="09a56-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="09a56-115">Eseguire i comandi seguenti in Exchange Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="09a56-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="09a56-116">Opzione 2: cambiare una cassetta postale della sala esistente nella cassetta postale delle risorse di Skype room System (collegata)</span><span class="sxs-lookup"><span data-stu-id="09a56-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


