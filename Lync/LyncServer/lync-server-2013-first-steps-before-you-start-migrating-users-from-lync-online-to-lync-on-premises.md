---
title: 'Lync Server 2013: primi passaggi prima di avviare la migrazione degli utenti da Lync Online a Lync locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e278fcb1e63c1db1334e625765d65d5d556e934
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Primi passaggi prima di iniziare la migrazione degli utenti da Lync Online a Lync locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-08_

Prima di iniziare a spostare gli utenti di Lync Online nell'ambiente locale, verificare che tutte le condizioni seguenti siano vere:

  - L'ambiente locale di Lync Server deve essere completamente distribuito e convalidato. Per altre informazioni, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Il tenant di Lync Online deve essere configurato per l'accesso remoto a PowerShell.
    
    A questo scopo, installare prima di tutto il modulo Lync Online per Windows PowerShell, che è possibile ottenere [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)qui:.
    
    Dopo aver installato il modulo, è possibile stabilire una sessione remota digitando i cmdlet seguenti in Lync Server Management Shell:
    
       ```
        Import-Module LyncOnlineConnector
       ```  
    
       ```
        $cred = Get-Credential
       ``` 
    
       ```
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Per altre informazioni su come stabilire una sessione di PowerShell remota con Lync Online, vedere [connessione a Lync Online tramite Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Per altre informazioni sull'uso del modulo PowerShell di Lync Online, vedere [uso di Windows PowerShell per gestire Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - La configurazione di Lync Online deve essere configurata per lo spazio di indirizzi SIP condiviso. Per eseguire questa operazione, avviare prima di tutto una sessione remota di PowerShell con Lync Online. Eseguire quindi il cmdlet seguente:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Dopo aver completato questi passaggi, è possibile procedere alla [migrazione degli utenti di Lync Online a Lync locale in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

