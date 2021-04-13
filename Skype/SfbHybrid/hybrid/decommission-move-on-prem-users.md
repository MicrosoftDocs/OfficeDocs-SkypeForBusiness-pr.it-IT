---
title: Spostare gli utenti nel cloud
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
description: Spostare gli utenti prima di rimuovere le autorizzazioni di un ambiente locale di Skype for Business.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656672"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="3ef52-103">Spostare gli utenti necessari prima di rimuovere le autorizzazioni dell'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="3ef52-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="3ef52-104">Questo articolo descrive come spostare gli utenti necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="3ef52-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3ef52-105">Questo è il passaggio 1 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="3ef52-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3ef52-106">**Passaggio 1. Spostare tutti gli utenti necessari da locale a online.**</span><span class="sxs-lookup"><span data-stu-id="3ef52-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="3ef52-107">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="3ef52-107">(This article)</span></span>

- <span data-ttu-id="3ef52-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="3ef52-108">Step 2.</span></span> <span data-ttu-id="3ef52-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="3ef52-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="3ef52-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="3ef52-110">Step 3.</span></span> <span data-ttu-id="3ef52-111">[Spostare gli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3ef52-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3ef52-112">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="3ef52-112">Step 4.</span></span> <span data-ttu-id="3ef52-113">Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3ef52-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="3ef52-114">Spostare tutti gli utenti necessari dall'ambiente locale al cloud</span><span class="sxs-lookup"><span data-stu-id="3ef52-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="3ef52-115">Tutti gli utenti che continueranno a utilizzare dopo aver completato la migrazione devono prima essere spostati dall'ambiente locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="3ef52-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="3ef52-116">Gli utenti vengono spostati utilizzando gli strumenti di amministrazione locali.</span><span class="sxs-lookup"><span data-stu-id="3ef52-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="3ef52-117">Per informazioni dettagliate, vedere [Move users between on-premises and cloud.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="3ef52-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="3ef52-118">Sebbene sia possibile per gli utenti con account Skype for Business Server locali utilizzare Teams, questi utenti non dispongono delle funzionalità complete di Teams.</span><span class="sxs-lookup"><span data-stu-id="3ef52-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="3ef52-119">Questi utenti non possono interagire o federatire con altri utenti che usano ancora Skype for Business (online o locale).</span><span class="sxs-lookup"><span data-stu-id="3ef52-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="3ef52-120">Né questi utenti possono ricevere chiamate PSTN nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="3ef52-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="3ef52-121">Pertanto, è necessario spostare questi utenti online.</span><span class="sxs-lookup"><span data-stu-id="3ef52-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="3ef52-122">Questo passaggio garantisce inoltre che tutti i contatti o le riunioni creati in Skype for Business Server siano migrati in Teams.</span><span class="sxs-lookup"><span data-stu-id="3ef52-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="3ef52-123">Per verificare se nella distribuzione locale sono presenti utenti rimanenti, eseguire il cmdlet seguente in una finestra di PowerShell di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ef52-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="3ef52-124">Se vengono restituiti utenti, esaminare l'output per determinare se gli account devono essere spostati nel cloud e, per tali utenti, attenersi alla procedura [riportata di seguito.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="3ef52-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="3ef52-125">Per gli account utente che non sono più necessari, eseguire il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="3ef52-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="3ef52-126">L'Disable-CsUser rimuoverà tutti gli attributi di Skype for Business per tutti gli utenti che soddisfano i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="3ef52-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="3ef52-127">Prima di procedere, verificare che questi account non siano più necessari in futuro.</span><span class="sxs-lookup"><span data-stu-id="3ef52-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="3ef52-128">A questo punto è possibile [disabilitare la configurazione ibrida.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="3ef52-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ef52-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ef52-129">See also</span></span>

- [<span data-ttu-id="3ef52-130">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3ef52-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="3ef52-131">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="3ef52-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="3ef52-132">Spostare gli endpoint dell'applicazione ibrida da locale a online</span><span class="sxs-lookup"><span data-stu-id="3ef52-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="3ef52-133">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3ef52-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




