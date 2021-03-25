---
title: Provisioning degli account Skype Room System Exchange e Skype
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
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: Leggere questi argomenti per informazioni su come effettuare il provisioning degli account di Exchange e Skype per Skype Room System.
ms.openlocfilehash: 0e8c73bc83a62465dc711b4a6f2725f1d9c576f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113062"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="c207c-103">Provisioning degli account Skype Room System Exchange e Skype</span><span class="sxs-lookup"><span data-stu-id="c207c-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="c207c-104">Leggere questi argomenti per informazioni su come effettuare il provisioning degli account di Exchange e Skype per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="c207c-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="c207c-105">Microsoft Teams Rooms è un prodotto diverso con dipendenze e procedure di distribuzione diverse.</span><span class="sxs-lookup"><span data-stu-id="c207c-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="c207c-106">Per informazioni su Microsoft Teams Rooms, vedere panoramica della distribuzione di Microsoft Teams [Rooms.](/MicrosoftTeams/rooms/rooms-deploy)</span><span class="sxs-lookup"><span data-stu-id="c207c-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](/MicrosoftTeams/rooms/rooms-deploy).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c207c-107">Il provisioning dell'account di sistema sala Skype dipende dal tipo di topologia dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c207c-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="c207c-108">Per ulteriori informazioni sulle topologie di Active Directory, vedere [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c207c-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="c207c-109">Provisioning degli account Skype Room System di Exchange &amp; Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c207c-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="c207c-110">Gli argomenti seguenti descrivono come effettuare il provisioning e gestire gli account di Skype Room System Exchange e Skype for Business per:</span><span class="sxs-lookup"><span data-stu-id="c207c-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="c207c-111">Distribuzioni locali della singola foresta</span><span class="sxs-lookup"><span data-stu-id="c207c-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="c207c-112">Distribuzioni locali di più foreste</span><span class="sxs-lookup"><span data-stu-id="c207c-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="c207c-113">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c207c-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="c207c-114">Distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="c207c-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="c207c-115">Skype Room System e partner federati Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c207c-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="c207c-116">Gestire gli account Skype Room System</span><span class="sxs-lookup"><span data-stu-id="c207c-116">Manage Skype Room System accounts</span></span>
