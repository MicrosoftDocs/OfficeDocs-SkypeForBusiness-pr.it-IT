---
title: Opzionale Definire le ore lavorative del gruppo di risposta in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Creare o modificare le ore lavorative del gruppo di risposte in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: f6a7d6bb8154d3113282a603ab39b45cf92d5556
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767299"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="152c7-103">Opzionale Definire le ore lavorative del gruppo di risposta in Skype for business</span><span class="sxs-lookup"><span data-stu-id="152c7-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="152c7-104">Creare o modificare le ore lavorative del gruppo di risposte in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="152c7-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="152c7-105">Definizione di orari di ufficio</span><span class="sxs-lookup"><span data-stu-id="152c7-105">Defining Business Hours</span></span>

<span data-ttu-id="152c7-106">Le impostazioni dell'ora di business definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificare le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="152c7-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="152c7-107">Gli amministratori del gruppo di risposte possono usare il cmdlet **New-CsRgsHoursOfBusiness** per creare pianificazioni predefinite che è possibile usare per qualsiasi numero di Response Group.</span><span class="sxs-lookup"><span data-stu-id="152c7-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="152c7-108">Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="152c7-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="152c7-109">Per informazioni dettagliate, vedere [progettazione e creazione di flussi di lavoro di Response Group in Skype for business](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="152c7-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="152c7-110">Se un flusso di lavoro viene definito come flusso di lavoro gestito, qualsiasi utente a cui viene assegnato il ruolo CsResponseGroupManager può impostare e modificare le ore lavorative personalizzate per i flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="152c7-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="152c7-111">Usare la notazione a 24 ore per i parametri nei cmdlet seguenti, ad esempio 20:00 = 8:00 P.M..</span><span class="sxs-lookup"><span data-stu-id="152c7-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="152c7-112">Per creare una raccolta di orari di ufficio predefiniti</span><span class="sxs-lookup"><span data-stu-id="152c7-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="152c7-113">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="152c7-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="152c7-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="152c7-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="152c7-115">Per ogni intervallo di ore univoco che si vuole definire, eseguire:</span><span class="sxs-lookup"><span data-stu-id="152c7-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="152c7-116">Per creare la raccolta ore lavorative che usa gli intervalli definiti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="152c7-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="152c7-117">L'esempio seguente specifica le ore lavorative di 9:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="152c7-117">The following example specifies business hours of 9:00 A.M.</span></span> <span data-ttu-id="152c7-118">alle 5:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="152c7-118">to 5:00 P.M.</span></span> <span data-ttu-id="152c7-119">per i giorni della settimana, 8:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="152c7-119">for weekdays, 8:00 A.M.</span></span> <span data-ttu-id="152c7-120">alle 10:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="152c7-120">to 10:00 A.M.</span></span> <span data-ttu-id="152c7-121">e di nuovo da 2:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="152c7-121">and again from 2:00 P.M.</span></span> <span data-ttu-id="152c7-122">alle 6:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="152c7-122">to 6:00 P.M.</span></span> <span data-ttu-id="152c7-123">per i sabati e non per le ore lavorative per la domenica:</span><span class="sxs-lookup"><span data-stu-id="152c7-123">for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="152c7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="152c7-124">See also</span></span>

[<span data-ttu-id="152c7-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="152c7-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="152c7-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="152c7-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
