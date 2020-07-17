---
title: Eseguire la migrazione dei dispositivi analogici
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server fornisce supporto per i dispositivi analogici. Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici. È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'ambiente di Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario eseguire la migrazione anche degli oggetti contatto associati ai dispositivi analogici. Utilizzare Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostare tali oggetti nel pool di Skype for Business Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752828"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="a2b29-107">Eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="a2b29-107">Migrate analog devices</span></span>

<span data-ttu-id="a2b29-108">Skype for Business Server fornisce supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="a2b29-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="a2b29-109">Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici.</span><span class="sxs-lookup"><span data-stu-id="a2b29-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="a2b29-110">È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a2b29-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="a2b29-111">Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario eseguire la migrazione anche degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="a2b29-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="a2b29-112">Utilizzare Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostare tali oggetti nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2b29-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="a2b29-113">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="a2b29-113">To migrate analog devices</span></span>

1. <span data-ttu-id="a2b29-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a2b29-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a2b29-115">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a2b29-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="a2b29-116">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2b29-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a2b29-117">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a2b29-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="a2b29-118">Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2b29-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


