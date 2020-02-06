---
title: Eseguire la migrazione dei dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server offre il supporto per i dispositivi analogici. In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici. Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813594"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="c7f0f-107">Eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c7f0f-107">Migrate analog devices</span></span>

<span data-ttu-id="c7f0f-108">Skype for Business Server offre il supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="c7f0f-109">In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c7f0f-110">Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="c7f0f-111">Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c7f0f-112">Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="c7f0f-113">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c7f0f-113">To migrate analog devices</span></span>

1. <span data-ttu-id="c7f0f-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c7f0f-115">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c7f0f-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="c7f0f-116">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c7f0f-117">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c7f0f-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="c7f0f-118">Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c7f0f-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


