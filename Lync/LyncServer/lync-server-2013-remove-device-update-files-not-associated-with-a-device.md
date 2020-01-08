---
title: 'Lync Server 2013: rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea26cd20826ed099e27c7287c53cc7ca79bef9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Ogni volta che vengono caricati nuovi aggiornamenti per dispositivi nel sistema, viene creata una regola di aggiornamento del dispositivo corrispondente. Per impostazione predefinita, le nuove regole di aggiornamento dei dispositivi vengono assegnate allo stato in sospeso. Ciò significa che le regole possono essere scaricate e installate nei dispositivi di test, ma non nei dispositivi di produzione, che consente di testare gli aggiornamenti prima di renderli disponibili per gli utenti. In base ai test, è possibile accettare e distribuire o rifiutare ed eliminare l'aggiornamento. Quando si rifiuta un aggiornamento, l'aggiornamento del dispositivo viene dissociato dalla regola di aggiornamento del dispositivo.

<div>


I file di aggiornamento dei dispositivi non più associati a un dispositivo possono essere rimossi tramite Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateFile** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>


  - Ad esempio, il comando seguente rimuove le regole di aggiornamento dei dispositivi nel server Web atl-cs-001.litwareinc.com che non sono più associate a un dispositivo:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

