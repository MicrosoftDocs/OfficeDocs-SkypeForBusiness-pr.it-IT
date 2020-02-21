---
title: 'Lync Server 2013: (facoltativo) definire i set di festività di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0680d59cb591e193f90bec16e19079dde8600b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="fd69a-102">Optional Definire i set di festività di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd69a-102">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd69a-103">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="fd69a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="fd69a-p101">Le impostazioni delle festività consentono di definire i giorni in cui il Response Group non è operativo e di specificare l'azione da effettuare in questi giorni. Un set di festività è la raccolta delle festività che si applicano a un Response Group.</span><span class="sxs-lookup"><span data-stu-id="fd69a-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd69a-106">Se un flusso di lavoro è definito come flusso di lavoro gestito, tutti gli utenti con il ruolo CsResponseGroupManager possono impostare e modificare le festività per i flussi di lavoro che gestiscono.</span><span class="sxs-lookup"><span data-stu-id="fd69a-106">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="fd69a-107">Per creare un set di festività</span><span class="sxs-lookup"><span data-stu-id="fd69a-107">To create a holiday set</span></span>

1.  <span data-ttu-id="fd69a-108">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="fd69a-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="fd69a-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fd69a-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fd69a-110">Per ogni festività che si desidera definire, eseguire:</span><span class="sxs-lookup"><span data-stu-id="fd69a-110">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="fd69a-111">Per creare l'insieme di festività che contiene le festività definite, eseguire:</span><span class="sxs-lookup"><span data-stu-id="fd69a-111">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="fd69a-112">Nell'esempio seguente viene illustrato un insieme di festività che include due festività:</span><span class="sxs-lookup"><span data-stu-id="fd69a-112">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd69a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd69a-113">See Also</span></span>


[<span data-ttu-id="fd69a-114">Creare o modificare un flusso di lavoro di un gruppo di risposta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd69a-114">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="fd69a-115">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd69a-115">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="fd69a-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="fd69a-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="fd69a-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="fd69a-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

