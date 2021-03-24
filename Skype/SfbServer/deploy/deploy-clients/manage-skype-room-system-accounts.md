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
description: Leggere questo argomento per informazioni su come gestire gli account di sistema sala Skype.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093294"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="6f679-103">Gestire gli account Skype Room System</span><span class="sxs-lookup"><span data-stu-id="6f679-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="6f679-104">Leggere questo argomento per informazioni su come gestire gli account di sistema sala Skype.</span><span class="sxs-lookup"><span data-stu-id="6f679-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f679-105">Microsoft Teams Rooms è un prodotto diverso con dipendenze e procedure di distribuzione diverse.</span><span class="sxs-lookup"><span data-stu-id="6f679-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="6f679-106">Per informazioni su Microsoft Teams Rooms, vedere panoramica sulla gestione di Microsoft Teams [Rooms.](/microsoftteams/rooms/rooms-manage)</span><span class="sxs-lookup"><span data-stu-id="6f679-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="6f679-107">Spostare l'account di sistema skype room tra pool</span><span class="sxs-lookup"><span data-stu-id="6f679-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="6f679-108">Se è necessario spostare l'account di sistema sala Skype da un pool di Skype for Business Server a un altro (ad esempio, durante gli aggiornamenti), utilizzare il comando seguente per spostare il pool di account di sistema Skype Room:</span><span class="sxs-lookup"><span data-stu-id="6f679-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="6f679-109">Disabilitare l'account di sistema sala Skype per i servizi Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6f679-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="6f679-110">Se è necessario disabilitare un account di sistema Skype Room esistente dai servizi Skype for Business in un pool di Skype for Business Server, utilizzare il comando seguente per disabilitare l'account:</span><span class="sxs-lookup"><span data-stu-id="6f679-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="6f679-111">Facoltativo: creare un gruppo di amministratori di Sistema sala Skype in Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f679-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="6f679-112">Ogni client di Sistema sala Skype che si aggiunge al dominio può essere gestito completamente da un utente di dominio con diritti di amministratore locale nel PC dell'appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="6f679-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="6f679-113">Pertanto, puoi creare un gruppo di amministratori dedicato in Active Directory e assegnare a questo gruppo i diritti amministrativi durante la configurazione del nuovo computer Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="6f679-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
