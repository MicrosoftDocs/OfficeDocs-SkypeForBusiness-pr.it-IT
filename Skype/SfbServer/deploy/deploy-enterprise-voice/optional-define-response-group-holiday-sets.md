---
title: Opzionale Definire set di festività di Response Group in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Creare o modificare set di festività di Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 617966828e39aae1ffbbfe10a7452d9d40117a84
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240409"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>Opzionale Definire set di festività di Response Group in Skype for business
 
Creare o modificare set di festività di Response Group in Skype for Business Server VoIP aziendale.
  
Le impostazioni per le festività definiscono i giorni in cui un Response Group viene chiuso per le aziende e specifica l'azione da eseguire in questi giorni. Un set di festività è la raccolta di festività che si applicano a un Response Group.
  
> [!NOTE]
> Se un flusso di lavoro viene definito come flusso di lavoro gestito, a qualsiasi utente viene assegnato il ruolo CsResponseGroupManager può impostare e modificare le festività per i flussi di lavoro gestiti. 
  
### <a name="to-create-a-holiday-set"></a>Per creare un set di festività

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per ogni festività che si vuole definire, eseguire:
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Per creare il set di festività che contiene le festività definite, eseguire:
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    L'esempio seguente mostra un set di festività che include due festività:
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Vedere anche

[Progettazione e creazione di flussi di lavoro di Response Group in Skype for business](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
