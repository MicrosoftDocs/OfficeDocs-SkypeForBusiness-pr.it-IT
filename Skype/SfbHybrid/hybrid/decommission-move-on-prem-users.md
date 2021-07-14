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
description: Spostare gli utenti prima di rimuovere un Skype for Business locale.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420811"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="7d3bc-103">Spostare gli utenti necessari prima di rimuovere le autorizzazioni dell'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="7d3bc-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="7d3bc-104">In questo articolo viene descritto come spostare gli utenti necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="7d3bc-105">Questo è il passaggio 1 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="7d3bc-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="7d3bc-106">**Passaggio 1. Spostare tutti gli utenti necessari da locale a online.**</span><span class="sxs-lookup"><span data-stu-id="7d3bc-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="7d3bc-107">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="7d3bc-107">(This article)</span></span>

- <span data-ttu-id="7d3bc-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-108">Step 2.</span></span> <span data-ttu-id="7d3bc-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="7d3bc-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="7d3bc-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-110">Step 3.</span></span> <span data-ttu-id="7d3bc-111">[Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="7d3bc-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="7d3bc-112">Tenere presente che tutti gli endpoint di applicazioni ibride esistenti non saranno individuabili tra il momento in cui si esegue il passaggio 2 precedente fino a quando non si completa questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="7d3bc-113">È consigliabile pianificare entrambi i passaggi 2 e 3 nella stessa finestra di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="7d3bc-114">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-114">Step 4.</span></span> <span data-ttu-id="7d3bc-115">[Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="7d3bc-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="7d3bc-116">Spostare tutti gli utenti necessari dall'ambiente locale al cloud</span><span class="sxs-lookup"><span data-stu-id="7d3bc-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="7d3bc-117">Tutti gli utenti che continueranno a utilizzare dopo aver completato la migrazione devono prima essere spostati dall'ambiente locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="7d3bc-118">Gli utenti vengono spostati utilizzando gli strumenti di amministrazione locali.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="7d3bc-119">Per informazioni dettagliate, vedere [Move users between on-premises and cloud.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7d3bc-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="7d3bc-120">Sebbene sia possibile per gli utenti con account di Skype for Business Server locali utilizzare Teams, questi utenti non dispongono della funzionalità completa di Teams.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="7d3bc-121">Questi utenti non possono interagire o federatire con altri utenti che usano ancora Skype for Business (online o locale).</span><span class="sxs-lookup"><span data-stu-id="7d3bc-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="7d3bc-122">Né questi utenti possono ricevere chiamate PSTN nel Teams client.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="7d3bc-123">Pertanto, è necessario spostare questi utenti online.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="7d3bc-124">Questo passaggio garantisce inoltre che tutti i contatti o le riunioni creati in Skype for Business Server siano migrati in Teams.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="7d3bc-125">Per verificare se nella distribuzione locale sono presenti utenti rimanenti, eseguire il cmdlet seguente in una finestra Skype for Business Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="7d3bc-126">Se vengono restituiti utenti, esaminare l'output per determinare se gli account devono essere spostati nel cloud e, per tali utenti, attenersi alla procedura [riportata di seguito.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7d3bc-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="7d3bc-127">Per gli account utente che non sono più necessari, eseguire il cmdlet di PowerShell Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="7d3bc-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="7d3bc-128">L'Disable-CsUser rimuoverà tutti gli Skype for Business per tutti gli utenti che soddisfano i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="7d3bc-129">Prima di procedere, verificare che questi account non siano più necessari in futuro.</span><span class="sxs-lookup"><span data-stu-id="7d3bc-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="7d3bc-130">A questo punto è possibile [disabilitare la configurazione ibrida.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="7d3bc-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d3bc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d3bc-131">See also</span></span>

- [<span data-ttu-id="7d3bc-132">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d3bc-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="7d3bc-133">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="7d3bc-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="7d3bc-134">Spostare gli endpoint dell'applicazione ibrida da locale a online</span><span class="sxs-lookup"><span data-stu-id="7d3bc-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="7d3bc-135">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d3bc-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




