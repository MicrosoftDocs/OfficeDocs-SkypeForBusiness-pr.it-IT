---
title: Spostare le directory conferenze di Lync Server 2010 in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Spostare le directory conferenze

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-28_

Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory di conferenza nel pool di Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Per trasferire una directory di conferenza in Lync Server 2013

1.  Aprire Lync Server Management Shell.

2.  Per ottenere l'identità delle directory conferenza nell'organizzazione, eseguire il comando seguente:
    
        Get-CsConferenceDirectory
    
    Il comando precedente restituisce tutte le directory conferenza dell'organizzazione. Per questo motivo, potresti voler limitare i risultati al pool da rimuovere. Se ad esempio si sta disattivando il pool con il nome di dominio completo (FQDN) pool01.contoso.net, usare questo comando per limitare i dati restituiti alle directory della conferenza da tale pool:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Questo comando restituisce solo le directory della conferenza in cui la proprietà ServiceID contiene il nome FQDN pool01.contoso.net.

3.  Per trasferire le directory conferenza, eseguire il comando seguente per ogni directory di conferenza nel pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Ad esempio, per trasferire la directory della conferenza 3, usare questo comando specificando un pool di Lync Server 2013 come TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Se si vuole trasferire tutte le directory conferenza in un pool, usare un comando simile al seguente:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Vedere il documento "disinstallazione di Microsoft Lync Server 2010 e rimozione dei ruoli del server" (da [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)cui è possibile scaricare) per istruzioni dettagliate su come rimuovere i pool di Lync 2010.

Quando si spostano le directory conferenza, è possibile che venga visualizzato l'errore seguente:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Questo errore si verifica in genere quando Lync Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività. Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza della shell ed eseguire di nuovo il comando per passare alla directory della conferenza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

