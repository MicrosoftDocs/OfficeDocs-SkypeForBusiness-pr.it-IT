---
title: Opzionale Definire le ore lavorative del gruppo di risposta in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Creare o modificare le ore lavorative del gruppo di risposte in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e492715e32b60858176f0034ef4978d0f333dc09
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240388"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>Opzionale Definire le ore lavorative del gruppo di risposta in Skype for business 
 
Creare o modificare le ore lavorative del gruppo di risposte in Skype for Business Server VoIP aziendale.
  
## <a name="defining-business-hours"></a>Definizione di orari di ufficio

Le impostazioni dell'ora di business definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificare le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio. Gli amministratori del gruppo di risposte possono usare il cmdlet **New-CsRgsHoursOfBusiness** per creare pianificazioni predefinite che è possibile usare per qualsiasi numero di Response Group.
  
> [!TIP]
> Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo al flusso di lavoro. Per informazioni dettagliate, vedere [progettazione e creazione di flussi di lavoro di Response Group in Skype for business](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Se un flusso di lavoro viene definito come flusso di lavoro gestito, qualsiasi utente a cui viene assegnato il ruolo CsResponseGroupManager può impostare e modificare le ore lavorative personalizzate per i flussi di lavoro gestiti. 
  
> [!IMPORTANT]
> Usare la notazione a 24 ore per i parametri nei cmdlet seguenti, ad esempio 20:00 = 8:00 P.M.. 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Per creare una raccolta di orari di ufficio predefiniti

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per ogni intervallo di ore univoco che si vuole definire, eseguire:
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Per creare la raccolta ore lavorative che usa gli intervalli definiti, eseguire:
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    L'esempio seguente specifica le ore lavorative di 9:00 A.M. alle 5:00 P.M. per i giorni della settimana, 8:00 A.M. alle 10:00 A.M. e di nuovo da 2:00 P.M. alle 6:00 P.M. per i sabati e non per le ore lavorative per la domenica:
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Vedere anche

[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
