---
title: Optional Definire l'orario di ufficio di Response Group in Skype for business
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
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Creare o modificare l'orario di ufficio di Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: dcd2f7174a75eb68ef8d35759a1e454ede976bde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830996"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="7ef81-103">Optional Definire l'orario di ufficio di Response Group in Skype for business</span><span class="sxs-lookup"><span data-stu-id="7ef81-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="7ef81-104">Creare o modificare l'orario di ufficio di Response Group in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7ef81-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="7ef81-105">Definizione dell'orario di ufficio</span><span class="sxs-lookup"><span data-stu-id="7ef81-105">Defining Business Hours</span></span>

<span data-ttu-id="7ef81-106">Le impostazioni relative all'orario di ufficio definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificare le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="7ef81-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="7ef81-107">Gli amministratori Response Group possono utilizzare il cmdlet **New-CsRgsHoursOfBusiness** per creare programmazioni predefinite da utilizzare con qualsiasi numero di Response Group.</span><span class="sxs-lookup"><span data-stu-id="7ef81-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="7ef81-108">Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7ef81-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="7ef81-109">Per informazioni dettagliate, vedere [progettazione e creazione di flussi di lavoro di Response Group in Skype for business](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="7ef81-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7ef81-110">Se un flusso di lavoro è definito come flusso di lavoro gestito, tutti gli utenti a cui è assegnato il ruolo CsResponseGroupManager possono impostare e modificare l'orario di ufficio personalizzato per i flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="7ef81-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7ef81-111">Utilizzare la notazione di 24 ore per i parametri nei cmdlet seguenti, ad esempio 20:00 = 8:00 P.M..</span><span class="sxs-lookup"><span data-stu-id="7ef81-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="7ef81-112">Per creare una raccolta di orari di ufficio predefinita</span><span class="sxs-lookup"><span data-stu-id="7ef81-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="7ef81-113">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="7ef81-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="7ef81-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7ef81-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7ef81-115">Per ogni intervallo univoco di ore che si desidera definire, eseguire:</span><span class="sxs-lookup"><span data-stu-id="7ef81-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="7ef81-116">Per creare la raccolta di orari di ufficio che utilizza gli intervalli definiti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="7ef81-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="7ef81-p103">Nell'esempio seguente viene specificato un orario di ufficio dalle 9.00 alle 17.00 per i giorni feriali e dalle 8.00 alle 10.00 e di nuovo dalle 14.00 alle 18.00 per il sabato, senza nessun orario di ufficio per la domenica:</span><span class="sxs-lookup"><span data-stu-id="7ef81-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="7ef81-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef81-124">See also</span></span>

[<span data-ttu-id="7ef81-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="7ef81-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="7ef81-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="7ef81-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
