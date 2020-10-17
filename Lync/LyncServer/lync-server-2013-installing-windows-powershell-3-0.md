---
title: 'Lync Server 2013: installazione di Windows PowerShell 3,0'
description: 'Lync Server 2013: installazione di Windows PowerShell 3,0.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4605231f4e73f6aada4fb34de895cdeb883d82b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550652"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Installazione di Windows PowerShell 3,0 per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-27_

Per distribuire Lync Server 2013 con esito positivo, è necessario utilizzare Windows PowerShell 3,0 su ogni computer che fa parte della topologia di Lync Server.

A questo punto, per i sistemi che eseguono Windows Server 2012 o Windows Server 2012 R2, non è necessario eseguire alcuna operazione e procedere alla fase successiva della distribuzione, poiché PowerShell 3,0 è incluso in tali sistemi operativi.

<div>


> [!IMPORTANT]  
> Tuttavia, per i sistemi che eseguono Windows Server 2008 R2 SP1, è necessario installare PowerShell 3,0 come prerequisito prima di installare Lync Server 2013 o le cose non funzionano. Per installare PowerShell 3,0, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Si tratta di un collegamento diretto alla pagina di download di PowerShell 3,0, insieme a informazioni relative all'installazione con esito positivo.



</div>

Dopo aver effettuato l'installazione, o se si desidera controllare e assicurarsi che prima di continuare con la distribuzione di Lync Server, confermando che PowerShell 3,0 è su un server è piuttosto semplice se si esegue questa operazione:

1.  Nel server che si desidera controllare, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, **Windows PowerShell**e quindi fare clic su **Windows PowerShell**.

2.  Nella console di Windows PowerShell, digitare il comando seguente al prompt dei comandi e quindi premere INVIO:
    
        Get-Host | Select-Object Version

3.  Se Windows PowerShell 3,0 è installato, verrà visualizzato un output simile al seguente:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

