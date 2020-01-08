---
title: 'Lync Server 2013: Installazione di Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Installazione di Windows PowerShell 3.0 per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-27_

Per distribuire Lync Server 2013 correttamente, è necessario Windows PowerShell 3,0 in ogni computer che fa parte della topologia di Lync Server.

A questo punto, per i sistemi che eseguono Windows Server 2012 o Windows Server 2012 R2, non è necessario eseguire alcuna operazione e procedere con la fase successiva della distribuzione, perché PowerShell 3,0 è incluso in tali sistemi operativi.

<div>


> [!IMPORTANT]  
> Ma per i sistemi che utilizzano Windows Server 2008 R2 SP1, è necessario installare PowerShell 3,0 come prerequisito prima di installare Lync Server 2013 o le cose non funzionano. Per installare PowerShell 3,0, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Si tratta di un collegamento diretto alla pagina di download di PowerShell 3,0, insieme alle informazioni relative all'installazione con successo.



</div>

Dopo aver eseguito l'installazione o se si vuole semplicemente verificare ed essere sicuri prima di continuare con la distribuzione di Lync Server, verificare che PowerShell 3,0 si trovi in un server sia piuttosto semplice se si esegue questa operazione:

1.  Nel server che si vuole controllare scegliere **Start**, fare clic su **tutti i programmi**, su **Accessori**, su **Windows PowerShell**e quindi su **Windows PowerShell**.

2.  Nella console di Windows PowerShell digitare il comando seguente al prompt dei comandi e quindi premere INVIO:
    
        Get-Host | Select-Object Version

3.  Se Windows PowerShell 3,0 è installato, verrà visualizzato l'output simile al seguente:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

