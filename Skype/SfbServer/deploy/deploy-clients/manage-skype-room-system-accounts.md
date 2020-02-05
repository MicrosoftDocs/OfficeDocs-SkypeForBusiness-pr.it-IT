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
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="1f927-103">Gestire gli account di sistema per Skype room</span><span class="sxs-lookup"><span data-stu-id="1f927-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="1f927-104">Leggi questo argomento per informazioni su come gestire gli account di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="1f927-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="1f927-105">Microsoft teams Rooms è un prodotto diverso con diverse dipendenze e procedure di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f927-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="1f927-106">Per informazioni su Microsoft teams rooms, vedere la panoramica sulla [gestione](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="1f927-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="1f927-107">Trasferire l'account di sistema room Skype tra i pool</span><span class="sxs-lookup"><span data-stu-id="1f927-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="1f927-108">Se è necessario trasferire l'account di sistema della sala Skype da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), usare il comando seguente per trasferire il pool di account di sistema room Skype:</span><span class="sxs-lookup"><span data-stu-id="1f927-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="1f927-109">Disabilitare l'account Skype room System per i servizi Skype for business</span><span class="sxs-lookup"><span data-stu-id="1f927-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="1f927-110">Se devi disabilitare un account di sistema room Skype esistente da Skype for Business Services in un pool di Skype for Business Server, usa il comando seguente per disabilitare l'account:</span><span class="sxs-lookup"><span data-stu-id="1f927-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="1f927-111">Facoltativo: creare un gruppo di amministratori di sistema per Skype room in Active Directory</span><span class="sxs-lookup"><span data-stu-id="1f927-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="1f927-112">Ogni client di sistema room Skype che unisce il dominio può essere completamente gestito da un utente di dominio con diritti di amministratore locale nel PC di Skype room System Appliance.</span><span class="sxs-lookup"><span data-stu-id="1f927-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="1f927-113">È quindi possibile creare un gruppo di amministratori dedicati in Active Directory e assegnare questo gruppo ai diritti amministrativi durante la configurazione del nuovo computer per la sala di Skype.</span><span class="sxs-lookup"><span data-stu-id="1f927-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

