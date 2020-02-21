---
title: 'Lync Server 2013: importazione delle regole di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5436be837af75045d75b8feee31886aaaf324f0b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Importare le regole di aggiornamento del dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Le regole di aggiornamento dei dispositivi possono essere importate solo utilizzando Windows PowerShell e il cmdlet **Import-CsDeviceUpdate** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>Per importare le regole di aggiornamento del dispositivo in un singolo server Web

  - Con il comando seguente vengono importate le regole di aggiornamento dei dispositivi nel server Web atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>Per importare le regole di aggiornamento dei dispositivi in tutti i server Web

  - In questo esempio le regole di aggiornamento dei dispositivi vengono importate in tutti i server Web distribuiti nell'organizzazione. Affinché questo comando funzioni, è necessario che \\ \\gli\\aggiornamenti della cartella ATL-FS-001.litwareinc.com siano condivisi e disponibili per tutti i server Web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

