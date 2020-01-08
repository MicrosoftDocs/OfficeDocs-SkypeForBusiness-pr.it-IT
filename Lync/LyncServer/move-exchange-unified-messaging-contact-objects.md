---
title: Trasferire oggetti contatto di messaggistica unificata di Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Trasferire oggetti contatto di messaggistica unificata di Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Per eseguire la migrazione degli oggetti di contatto AutoAttendant (AA) e di accesso sottoscrittore (SA) alla nuova distribuzione di Lync Server 2013, prima di tutto spostare gli oggetti dalla distribuzione legacy di Office Communications Server 2007 R2 alla nuova distribuzione di Lync Server 2013 usando i cmdlet **Get-CsExUmContact** e **Move-CsExUmContact** . Sul server Exchange viene quindi eseguito lo script di Windows PowerShell di **ExchUCUtil** per eseguire le operazioni seguenti per il pool di Lync appena distribuito:

  - Aggiungerlo ai gateway IP di messaggistica unificata.

  - Aggiungerlo ai gruppi di caccia alla messaggistica unificata.

<div>


> [!NOTE]  
> Per usare i cmdlet <STRONG>Get-CsExUmContact</STRONG> e <STRONG>Move-CsExUmContact</STRONG> , è necessario essere un membro del gruppo RTCUniversalUserAdmins e disporre dell'autorizzazione unità organizzativa (OU) per l'unità organizzativa in cui sono archiviati gli oggetti contatti. L'autorizzazione dell'unità organizzativa può essere concessa usando il cmdlet <STRONG>Grant-OUPermission</STRONG> .



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Per trasferire oggetti contatto tramite Lync Server Management Shell

1.  Aprire Lync Server Management Shell.

2.  Per ogni pool registrato con la messaggistica unificata di Exchange (dove pool1.contoso.net è un pool della distribuzione di Office Communications Server 2007 R2 e pool2.contoso.net è il pool della distribuzione di Lync Server 2013) nella riga di comando, digitare quanto segue:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Per verificare che gli oggetti contatto vengano spostati, eseguire il cmdlet **Get-CsExUmContact** e verificare che **RegistrarPool** ora faccia riferimento al nuovo pool.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Per eseguire lo script di Windows PowerShell di ExchUCUtil

1.  Accedere al server Messaggistica unificata di Exchange come utente con privilegi di amministratore dell'organizzazione di Exchange.

2.  Passare allo script di Windows PowerShell di ExchUCUtil.
    
    In Exchange 2007, ExchUCUtil. ps1 si trova in: **% Program Files%\\Microsoft\\Exchange Server\\Scripts\\exchucutil. ps1**
    
    In Exchange 2010, ExchUCUtil. ps1 si trova in: **% Program Files%\\Microsoft\\Exchange Server\\V14\\script\\exchucutil. ps1**

3.  Se Exchange viene distribuito in una singola foresta, digitare:
    
        exchucutil.ps1
    
    In alternativa, se Exchange è distribuito in più foreste, digitare:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    dove FQDN foresta specifica la foresta in cui è distribuito Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Assicurarsi di riavviare il servizio <STRONG>front-end di Lync Server</STRONG> (RtcSrv. exe) <EM>dopo</EM> l'esecuzione di exchucutil. ps1. In caso contrario, Lync Server 2013 non rileverà la messaggistica unificata nella topologia.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

