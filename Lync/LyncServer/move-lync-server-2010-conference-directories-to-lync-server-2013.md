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
ms.openlocfilehash: 6712e22ffcdc2eaea9ae39be961bb50316beed5b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Spostare le directory conferenze

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-28_

Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool di Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Per spostare una directory conferenze in Lync Server 2013

1.  Aprire Lync Server Management Shell.

2.  Per ottenere l'identità delle directory conferenze nell'organizzazione, eseguire il comando riportato di seguito:
    
        Get-CsConferenceDirectory
    
    Il comando precedente restituisce tutte le directory conferenze nell'organizzazione. Per questo motivo, è possibile che si desideri limitare i risultati al pool di cui è stata eseguita la rimozione. Ad esempio, se si sta rimuovendo il pool con il nome di dominio completo (FQDN) pool01.contoso.net, utilizzare questo comando per limitare i dati restituiti alle directory conferenze del pool:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Questo comando restituisce solo le directory conferenze in cui la proprietà ServiceID contiene il nome di dominio completo pool01.contoso.net.

3.  Per spostare le directory conferenze, eseguire il comando riportato di seguito per ogni directory conferenze nel pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Ad esempio, per spostare la directory conferenze 3, utilizzare questo comando, specificando un pool di Lync Server 2013 come TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Se si desidera spostare tutte le directory conferenze in un pool, utilizzare un comando simile al seguente:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Consultare il documento "disinstallazione di Microsoft Lync Server 2010 e rimozione dei ruoli del server" (che può essere scaricato [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)da) per istruzioni dettagliate su come rimuovere i pool di Lync 2010.

Quando si spostano le directory conferenze, è possibile che venga visualizzato l'errore seguente:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Questo errore si verifica in genere quando Lync Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività. Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza di Shell ed eseguire di nuovo il comando per spostare la directory conferenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

