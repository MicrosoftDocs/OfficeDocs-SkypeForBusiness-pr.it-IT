---
title: Spostare gli oggetti contatto della messaggistica unificata di Exchange
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42abb209eaf59be66c8516401616dcac4f1c94ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500293"
---
# <a name="move-exchange-unified-messaging-contact-objects"></a>Spostare gli oggetti contatto della messaggistica unificata di Exchange

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Per eseguire la migrazione degli oggetti contatto dell'operatore automatico (AA) e dell'accesso sottoscrittore (SA) alla nuova distribuzione di Lync Server 2013, è necessario prima di tutto spostare gli oggetti dalla distribuzione di Office Communications Server 2007 R2 legacy alla nuova distribuzione di Lync Server 2013 utilizzando i cmdlet **Get-CsExUmContact** e **Move-CsExUmContact** . Sul server Exchange, eseguire lo script di Windows PowerShell di **ExchUCUtil** per effettuare le seguenti operazioni per il pool Lync appena distribuito:

  - Aggiungerlo ai gateway IP di messaggistica unificata.

  - Aggiungerlo ai gruppi di risposta di messaggistica unificata.

<div>


> [!NOTE]  
> Per poter utilizzare i cmdlet <STRONG>Get-CsExUmContact</STRONG> e <STRONG>Move-CsExUmContact</STRONG>, è necessario essere membri del gruppo RTCUniversalUserAdmins e disporre dell'autorizzazione per l'unità organizzativa (OU) in cui sono archiviati gli oggetti contatto. Tale autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-OUPermission</STRONG>.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Per spostare gli oggetti contatto utilizzando Lync Server Management Shell

1.  Aprire Lync Server Management Shell.

2.  Per ogni pool registrato con messaggistica unificata di Exchange (dove pool1.contoso.net è un pool della distribuzione di Office Communications Server 2007 R2 e pool2.contoso.net è il pool della distribuzione di Lync Server 2013) dalla riga di comando digitare quanto segue:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Per accertarsi che gli oggetti contatto siano stati spostati, eseguire il cmdlet **Get-CsExumContact** e verificare che **RegistrarPool** ora punti al nuovo pool.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Per eseguire lo script ExchUCUtil di Windows PowerShell

1.  Accedere al server di messaggistica unificata di Exchange come utente con privilegi di amministratore dell'organizzazione di Exchange.

2.  Passare allo script di Windows PowerShell di ExchUCUtil.
    
    In Exchange 2007, ExchUCUtil.ps1 si trova in: **% Program Files% \\ Microsoft \\ Exchange Server \\ Scripts \\ExchUCUtil.ps1**
    
    In Exchange 2010, ExchUCUtil.ps1 si trova in: **% Program Files% \\ Microsoft \\ Exchange Server \\ V14 \\ Scripts \\ExchUCUtil.ps1**

3.  Se Exchange è distribuito in una singola foresta, digitare quanto indicato di seguito:
    
        exchucutil.ps1
    
    In alternativa, se Exchange è distribuito in più foreste, digitare quanto indicato di seguito:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    dove la foresta FQDN Specifica la foresta in cui è distribuito Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Riavviare il servizio <STRONG>Lync Server Front End</STRONG> (rtcsrv.exe) <EM>dopo</EM> aver eseguito exchucutil.ps1. In caso contrario, Lync Server 2013 non rileva la messaggistica unificata nella topologia.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

