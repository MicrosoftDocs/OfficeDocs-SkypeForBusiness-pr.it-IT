---
title: (Facoltativo) Definire i set di festività di Response Group in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Creare o modificare i set di festività di Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3a8173964cf32c148146ffc4c501861b35bf6077
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103682"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="52783-103">(Facoltativo) Definire i set di festività di Response Group in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="52783-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="52783-104">Creare o modificare i set di festività di Response Group in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="52783-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="52783-p101">Le impostazioni delle festività consentono di definire i giorni in cui il Response Group non è operativo e di specificare l'azione da effettuare in questi giorni. Un set di festività è la raccolta delle festività che si applicano a un Response Group.</span><span class="sxs-lookup"><span data-stu-id="52783-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52783-107">Se un flusso di lavoro è definito come flusso di lavoro gestito, tutti gli utenti con il ruolo CsResponseGroupManager possono impostare e modificare le festività per i flussi di lavoro che gestiscono.</span><span class="sxs-lookup"><span data-stu-id="52783-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="52783-108">Per creare un set di festività</span><span class="sxs-lookup"><span data-stu-id="52783-108">To create a holiday set</span></span>

1. <span data-ttu-id="52783-109">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="52783-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="52783-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="52783-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="52783-111">Per ogni festività che si desidera definire, eseguire:</span><span class="sxs-lookup"><span data-stu-id="52783-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="52783-112">Per creare l'insieme di festività che contiene le festività definite, eseguire:</span><span class="sxs-lookup"><span data-stu-id="52783-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="52783-113">Nell'esempio seguente viene illustrato un insieme di festività che include due festività:</span><span class="sxs-lookup"><span data-stu-id="52783-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="52783-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52783-114">See also</span></span>

[<span data-ttu-id="52783-115">Progettazione e creazione di flussi di lavoro di Response Group in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="52783-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="52783-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="52783-116">New-CsRgsHoliday</span></span>](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="52783-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="52783-117">New-CsRgsHolidaySet</span></span>](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)