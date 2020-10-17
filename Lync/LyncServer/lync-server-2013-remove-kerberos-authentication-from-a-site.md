---
title: "Lync Server 2013: rimuovere l'autenticazione Kerberos da un sito"
description: "Lync Server 2013: rimuovere l'autenticazione Kerberos da un sito."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553532"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>In Lync Server 2013 rimuovere l'autenticazione Kerberos da un sito

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-01-16_

Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.

Per rimuovere l'autenticazione Kerberos da un sito o ritirare un sito, è necessario rimuovere l'assegnazione dell'account di autenticazione Kerberos dal sito utilizzando il cmdlet **Remove-CsKerberosAccountAssignment**. Utilizzare la procedura seguente per rimuovere l'assegnazione dell'account di autenticazione Kerberos, rimuovendo così l'assegnazione da tutti i computer del sito.

<div class=" ">


> [!WARNING]  
> Se si sta definitivamente ritirando l'account abilitato per Kerberos, è necessario utilizzare utenti e computer di Active Directory per eliminarlo da servizi di dominio Active Directory dopo che è stata rimossa l'assegnazione. Se al contrario si prevede di utilizzare l'oggetto in futuro, è possibile conservare l'oggetto Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Rimuovere l'autenticazione Kerberos da un sito

1.  Come membri del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Nella riga di comando eseguire i due comandi seguenti:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Ad esempio:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

