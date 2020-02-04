---
title: 'Lync Server 2013: (facoltativo) definire le ore lavorative del gruppo di risposte'
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
ms.openlocfilehash: 5829ca56c2a06f54ba19064a5b24caad2aa7ed25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a>Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

<div>

## <a name="defining-business-hours"></a>Definizione di orari di ufficio

Le impostazioni dell'ora di business definiscono quando il flusso di lavoro è disponibile per rispondere alle chiamate e specificare le azioni da eseguire per le chiamate al di fuori dell'orario di ufficio. Gli amministratori del gruppo di risposte possono usare il cmdlet **New-CsRgsHoursOfBusiness** per creare pianificazioni predefinite che è possibile usare per qualsiasi numero di Response Group.

<div>


> [!TIP]  
> Quando si crea o si modifica un flusso di lavoro, è possibile specificare una pianificazione personalizzata che si applica solo al flusso di lavoro. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">creare o modificare un flusso di lavoro di gruppo di ricerca in Lync server 2013</A> o <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">creare o modificare un flusso di lavoro interattivo in Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Se un flusso di lavoro viene definito come flusso di lavoro gestito, qualsiasi utente a cui viene assegnato il ruolo CsResponseGroupManager può impostare e modificare le ore lavorative personalizzate per i flussi di lavoro gestiti.



</div>

<div>


> [!IMPORTANT]  
> Usare la notazione a 24 ore per i parametri nei cmdlet seguenti, ad esempio 20:00 = 8:00 P.M..



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a>Per creare una raccolta di orari di ufficio predefiniti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per ogni intervallo di ore univoco che si vuole definire, eseguire:
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    Per creare la raccolta ore lavorative che usa gli intervalli definiti, eseguire:
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    L'esempio seguente specifica le ore lavorative di 9:00 A.M. alle 5:00 P.M. per i giorni della settimana, 8:00 A.M. alle 10:00 A.M. e di nuovo da 2:00 P.M. alle 6:00 P.M. per i sabati e non per le ore lavorative per la domenica:
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare un flusso di lavoro di gruppo di ricerca in Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Creare o modificare un flusso di lavoro interattivo in Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

