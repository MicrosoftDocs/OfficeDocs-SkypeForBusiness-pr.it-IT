---
title: 'Lync Server 2013: (facoltativo) definire le ore lavorative del gruppo di risposte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8ddd2bde582c66cf337deb9aa78178d3e22d1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="ef9eb-102">Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9eb-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef9eb-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ef9eb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="ef9eb-104">Definizione di orari di ufficio</span><span class="sxs-lookup"><span data-stu-id="ef9eb-104">Defining Business Hours</span></span>

<span data-ttu-id="ef9eb-105">Le impostazioni dell'ora di business definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificare le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="ef9eb-106">Gli amministratori del gruppo di risposte possono usare il cmdlet **New-CsRgsHoursOfBusiness** per creare pianificazioni predefinite che è possibile usare per qualsiasi numero di Response Group.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ef9eb-107">Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="ef9eb-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">creare o modificare un flusso di lavoro di gruppo di ricerca in Lync server 2013</A> o <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">creare o modificare un flusso di lavoro interattivo in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ef9eb-109">Se un flusso di lavoro viene definito come flusso di lavoro gestito, qualsiasi utente a cui viene assegnato il ruolo CsResponseGroupManager può impostare e modificare le ore lavorative personalizzate per i flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ef9eb-110">Usare la notazione a 24 ore per i parametri nei cmdlet seguenti, ad esempio 20:00 = 8:00 P.M..</span><span class="sxs-lookup"><span data-stu-id="ef9eb-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="ef9eb-111">Per creare una raccolta di orari di ufficio predefiniti</span><span class="sxs-lookup"><span data-stu-id="ef9eb-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="ef9eb-112">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ef9eb-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ef9eb-114">Per ogni intervallo di ore univoco che si vuole definire, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ef9eb-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="ef9eb-115">Per creare la raccolta ore lavorative che usa gli intervalli definiti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ef9eb-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="ef9eb-116">L'esempio seguente specifica le ore lavorative di 9:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-116">The following example specifies business hours of 9:00 A.M.</span></span> <span data-ttu-id="ef9eb-117">alle 5:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-117">to 5:00 P.M.</span></span> <span data-ttu-id="ef9eb-118">per i giorni della settimana, 8:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-118">for weekdays, 8:00 A.M.</span></span> <span data-ttu-id="ef9eb-119">alle 10:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-119">to 10:00 A.M.</span></span> <span data-ttu-id="ef9eb-120">e di nuovo da 2:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-120">and again from 2:00 P.M.</span></span> <span data-ttu-id="ef9eb-121">alle 6:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="ef9eb-121">to 6:00 P.M.</span></span> <span data-ttu-id="ef9eb-122">per i sabati e non per le ore lavorative per la domenica:</span><span class="sxs-lookup"><span data-stu-id="ef9eb-122">for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef9eb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef9eb-123">See Also</span></span>


[<span data-ttu-id="ef9eb-124">Creare o modificare un flusso di lavoro di gruppo di ricerca in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9eb-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="ef9eb-125">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9eb-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="ef9eb-126">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="ef9eb-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="ef9eb-127">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="ef9eb-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

