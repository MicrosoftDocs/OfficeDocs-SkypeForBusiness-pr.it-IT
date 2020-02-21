---
title: 'Lync Server 2013: rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1376e82ac29efbe2fcbf996445a75fc3bea1492d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

Ogni volta che sul sistema vengono caricati degli aggiornamenti dei dispositivi, viene creata una corrispondente regola di aggiornamento dei dispositivi. Per impostazione predefinita, queste nuove regole di aggiornamento dei dispositivi vengono assegnate allo stato in sospeso. Questo significa che le regole possono essere scaricate e installate nei dispositivi di test, ma non nei dispositivi di produzione, che consentono di testare gli aggiornamenti prima di renderli disponibili agli utenti. In base ai test, è possibile accettare e distribuire o rifiutare ed eliminare l'aggiornamento. Quando si rifiuta un aggiornamento, l'aggiornamento del dispositivo è disassociato dalla regola di aggiornamento dei dispositivi.

<div>


I file di aggiornamento dei dispositivi che non sono più associati a un dispositivo possono essere rimossi utilizzando Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateFile** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>


  - Ad esempio, il comando seguente rimuove tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com che non sono più associate a un dispositivo:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

