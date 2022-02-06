---
title: (Facoltativo) Definire l'orario di ufficio di Response Group in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 'Creare o modificare l''orario di ufficio di Response Group, in Skype for Business Server VoIP aziendale.'
---

# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Facoltativo) Definire l'orario di ufficio di Response Group in Skype for Business 
 
Creare o modificare l'orario di ufficio di Response Group, in Skype for Business Server VoIP aziendale.
  
## <a name="defining-business-hours"></a>Definizione dell'orario di ufficio

Le impostazioni dell'orario di ufficio definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificano le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio. Gli amministratori Response Group possono utilizzare il cmdlet **New-CsRgsHoursOfBusiness** per creare programmazioni predefinite da utilizzare con qualsiasi numero di Response Group.
  
> [!TIP]
> Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo a tale flusso di lavoro. Per informazioni dettagliate, vedere [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Se un flusso di lavoro è definito come flusso di lavoro gestito, qualsiasi utente a cui è assegnato il ruolo CsResponseGroupManager può impostare e modificare l'orario di ufficio personalizzato per i flussi di lavoro gestiti. 
  
> [!IMPORTANT]
> Utilizzare la notazione 24 ore per i parametri nei cmdlet seguenti(ad esempio, 20:00=8:00 P.M.). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Per creare una raccolta orari di ufficio predefinita

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per ogni intervallo univoco di ore che si desidera definire, eseguire:
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Per creare la raccolta di orari di ufficio che utilizza gli intervalli definiti, eseguire:
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    Nell'esempio seguente viene specificato un orario di ufficio dalle 9.00 alle 17.00 per i giorni feriali e dalle 8.00 alle 10.00 e di nuovo dalle 14.00 alle 18.00 per il sabato, senza nessun orario di ufficio per la domenica:
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Vedere anche

[New-CsRgsTimeRange](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)