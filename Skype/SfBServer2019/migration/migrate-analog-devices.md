---
title: Eseguire la migrazione dei dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server offre il supporto per i dispositivi analogici. In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici. Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189086"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="94569-107">Eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="94569-107">Migrate analog devices</span></span>

<span data-ttu-id="94569-108">Skype for Business Server offre il supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="94569-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="94569-109">In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici.</span><span class="sxs-lookup"><span data-stu-id="94569-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="94569-110">Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94569-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="94569-111">Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="94569-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="94569-112">Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="94569-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="94569-113">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="94569-113">To migrate analog devices</span></span>

1. <span data-ttu-id="94569-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="94569-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="94569-115">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="94569-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="94569-116">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="94569-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="94569-117">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="94569-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="94569-118">Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="94569-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


