---
title: "Lync Server 2013: (facoltativo) definire l'orario di ufficio di Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891dd05caf5e2ec3411da73c1151ae61c2d0630c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524463"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="bfe9c-102">Optional Definire l'orario di ufficio di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfe9c-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfe9c-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfe9c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="bfe9c-104">Definizione dell'orario di ufficio</span><span class="sxs-lookup"><span data-stu-id="bfe9c-104">Defining Business Hours</span></span>

<span data-ttu-id="bfe9c-105">Le impostazioni relative all'orario di ufficio definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificare le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="bfe9c-106">Gli amministratori Response Group possono utilizzare il cmdlet **New-CsRgsHoursOfBusiness** per creare programmazioni predefinite da utilizzare con qualsiasi numero di Response Group.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="bfe9c-107">Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="bfe9c-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">creare o modificare un flusso di lavoro di un gruppo di risposta in Lync server 2013</A> o <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">creare o modificare un flusso di lavoro interattivo in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bfe9c-109">Se un flusso di lavoro è definito come flusso di lavoro gestito, tutti gli utenti a cui è assegnato il ruolo CsResponseGroupManager possono impostare e modificare l'orario di ufficio personalizzato per i flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bfe9c-110">Utilizzare la notazione di 24 ore per i parametri nei cmdlet seguenti, ad esempio 20:00 = 8:00 P.M..</span><span class="sxs-lookup"><span data-stu-id="bfe9c-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="bfe9c-111">Per creare una raccolta di orari di ufficio predefinita</span><span class="sxs-lookup"><span data-stu-id="bfe9c-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="bfe9c-112">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="bfe9c-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bfe9c-114">Per ogni intervallo univoco di ore che si desidera definire, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bfe9c-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="bfe9c-115">Per creare la raccolta di orari di ufficio che utilizza gli intervalli definiti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bfe9c-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="bfe9c-p103">Nell'esempio seguente viene specificato un orario di ufficio dalle 9.00 alle 17.00 per i giorni feriali e dalle 8.00 alle 10.00 e di nuovo dalle 14.00 alle 18.00 per il sabato, senza nessun orario di ufficio per la domenica:</span><span class="sxs-lookup"><span data-stu-id="bfe9c-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfe9c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe9c-123">See Also</span></span>


[<span data-ttu-id="bfe9c-124">Creare o modificare un flusso di lavoro di un gruppo di risposta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfe9c-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="bfe9c-125">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfe9c-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="bfe9c-126">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="bfe9c-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="bfe9c-127">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="bfe9c-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

