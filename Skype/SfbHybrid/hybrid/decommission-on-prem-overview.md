---
title: Rimuovere le autorizzazioni dell'ambiente Skype for Business locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni su come rimuovere le autorizzazioni dell'ambiente Skype for Business locale.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593899"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="36838-103">Rimuovere le autorizzazioni dell'ambiente Skype for Business locale</span><span class="sxs-lookup"><span data-stu-id="36838-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="36838-104">Se l'organizzazione usa Teams o Skype for Business online con una distribuzione locale di Skype for Business Server, è possibile eseguire la migrazione completa di questi ambienti nel cloud e quindi ritirare la distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36838-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="36838-105">Prima di rimuovere le autorizzazioni dell'ambiente [](configure-hybrid-connectivity.md) locale, è necessario configurare la connettività ibrida tra la distribuzione locale e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36838-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="36838-106">Dopo aver configurato la connettività ibrida, è possibile eseguire la migrazione degli utenti nel cloud, durante la migrazione delle riunioni da locale e la migrazione di qualsiasi contatto da Skype for Business Server a Teams.</span><span class="sxs-lookup"><span data-stu-id="36838-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="36838-107">La configurazione della connettività ibrida è un passaggio necessario per eseguire la migrazione degli utenti da locale al cloud e per garantire la funzionalità completa di Teams.</span><span class="sxs-lookup"><span data-stu-id="36838-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="36838-108">Per completare lo spostamento dall'ambiente locale al cloud e rimuovere le autorizzazioni dell'ambiente Skype for Business Server locale, è necessario completare i passaggi seguenti nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="36838-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="36838-109">**Passaggio 1.**</span><span class="sxs-lookup"><span data-stu-id="36838-109">**Step 1.**</span></span> <span data-ttu-id="36838-110">[Spostare tutti gli utenti e gli endpoint dell'applicazione necessari da](decommission-move-on-prem-users.md)locale a online.</span><span class="sxs-lookup"><span data-stu-id="36838-110">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="36838-111">**Passaggio 2.**</span><span class="sxs-lookup"><span data-stu-id="36838-111">**Step 2.**</span></span> <span data-ttu-id="36838-112">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="36838-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="36838-113">**Passaggio 3.**</span><span class="sxs-lookup"><span data-stu-id="36838-113">**Step 3.**</span></span> <span data-ttu-id="36838-114">Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="36838-114">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

