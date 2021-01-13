---
title: Gestire gli account Skype Room System
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
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leggere questo argomento per informazioni su come gestire gli account di sistema di Skype room.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805556"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="96019-103">Gestire gli account Skype Room System</span><span class="sxs-lookup"><span data-stu-id="96019-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="96019-104">Leggere questo argomento per informazioni su come gestire gli account di sistema di Skype room.</span><span class="sxs-lookup"><span data-stu-id="96019-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="96019-105">Microsoft teams Rooms è un prodotto diverso con diverse dipendenze e procedure di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="96019-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="96019-106">Per informazioni sulle sale di Microsoft teams, vedere la [panoramica sulla gestione](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="96019-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="96019-107">Spostare l'account di sistema della sala Skype tra pool</span><span class="sxs-lookup"><span data-stu-id="96019-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="96019-108">Se è necessario spostare l'account del sistema di chat room Skype da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), utilizzare il seguente comando per spostare il pool di account di sistema di Skype room System:</span><span class="sxs-lookup"><span data-stu-id="96019-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="96019-109">Disabilitare l'account di sistema della sala Skype per i servizi Skype for business</span><span class="sxs-lookup"><span data-stu-id="96019-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="96019-110">Se è necessario disabilitare un account Skype for business per il sistema di chat room esistente su un pool di Skype for Business Server, utilizzare il seguente comando per disabilitare l'account:</span><span class="sxs-lookup"><span data-stu-id="96019-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="96019-111">Facoltativo: creare un gruppo di amministratori di sistema di Skype room in Active Directory</span><span class="sxs-lookup"><span data-stu-id="96019-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="96019-112">Ogni client del sistema Skype room che unisce il dominio può essere completamente gestito da un utente di dominio con diritti di amministratore locale sul PC di Skype room System Appliance.</span><span class="sxs-lookup"><span data-stu-id="96019-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="96019-113">Pertanto, è possibile creare un gruppo di amministratori dedicato in Active Directory e concedere a questo gruppo i diritti amministrativi durante la configurazione del nuovo computer del sistema Skype room.</span><span class="sxs-lookup"><span data-stu-id="96019-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

