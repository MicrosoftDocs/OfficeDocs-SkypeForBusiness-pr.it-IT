---
title: (Facoltativo) Definire i set di festività di Response Group in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Creare o modificare i set di festività di Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 8978789a5ac5b050123bad619c093ec4e895c36e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773266"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(Facoltativo) Definire i set di festività di Response Group in Skype for Business
 
Creare o modificare i set di festività di Response Group in Skype for Business Server VoIP aziendale.
  
Le impostazioni delle festività consentono di definire i giorni in cui il Response Group non è operativo e di specificare l'azione da effettuare in questi giorni. Un set di festività è la raccolta delle festività che si applicano a un Response Group.
  
> [!NOTE]
> Se un flusso di lavoro è definito come flusso di lavoro gestito, tutti gli utenti con il ruolo CsResponseGroupManager possono impostare e modificare le festività per i flussi di lavoro che gestiscono. 
  
### <a name="to-create-a-holiday-set"></a>Per creare un set di festività

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Per ogni festività che si desidera definire, eseguire:
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Per creare l'insieme di festività che contiene le festività definite, eseguire:
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    Nell'esempio seguente viene illustrato un insieme di festività che include due festività:
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Vedere anche

[Progettazione e creazione di flussi di lavoro di Response Group in Skype for Business](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)