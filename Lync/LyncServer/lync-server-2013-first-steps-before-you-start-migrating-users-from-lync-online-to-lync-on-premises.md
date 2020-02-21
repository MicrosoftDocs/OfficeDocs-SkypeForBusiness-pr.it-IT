---
title: 'Lync Server 2013: primi passaggi prima di avviare la migrazione degli utenti da Lync Online a Lync in locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4165df6829818b90a22eff4f90ac8072876b4831
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Primi passaggi prima di avviare la migrazione degli utenti da Lync Online a Lync locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-08_

Prima di avviare lo spostamento degli utenti di Lync Online nell'ambiente locale, verificare che siano soddisfatte tutte le condizioni seguenti:

  - L'ambiente locale di Lync Server deve essere completamente distribuito e convalidato. Per ulteriori informazioni, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Il tenant di Lync Online deve essere configurato per l'accesso a Remote PowerShell.
    
    A tale scopo, installare innanzitutto il modulo di Lync Online per Windows PowerShell, che è possibile ottenere qui [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911):.
    
    Dopo aver installato il modulo, è possibile stabilire una sessione remota digitando i seguenti cmdlet in Lync Server Management Shell:
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Lync Online, vedere [connessione a Lync Online tramite Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Per ulteriori informazioni sull'utilizzo del modulo di Lync Online PowerShell, vedere [using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Lync Online deve essere configurato per lo spazio di indirizzi SIP condiviso. A tale scopo, avviare innanzitutto una sessione remota di PowerShell con Lync Online. Eseguire quindi il cmdlet seguente:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Dopo aver completato questi passaggi, è possibile passare alla [migrazione degli utenti di Lync Online a Lync in locale in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

