---
title: Trasferire le directory conferenza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Trasferire le directory conferenza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory di conferenza nel pool di Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Per trasferire una directory di conferenza in Lync Server 2013

1.  Aprire Lync Server Management Shell.

2.  Per ottenere l'identità delle directory conferenza nell'organizzazione, eseguire i comandi seguenti:
    
        Get-CsConferenceDirectory
    
    Poiché questo cmdlet restituisce tutte le directory conferenza dell'organizzazione, è consigliabile limitare i risultati solo al pool che si vuole rimuovere. Ad esempio, se vuoi rimuovere un pool con il nome di dominio completo (FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Questo cmdlet restituisce tutte le directory conferenza in cui l'ID servizio contiene l'FQDN pool01.contoso.net.

3.  Per trasferire le directory conferenza, eseguire le operazioni seguenti per ogni directory di conferenza nel pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Ad esempio:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Potrebbe verificarsi un errore, illustrato di seguito, causato da Lync Server Management Shell che richiede un set di autorizzazioni aggiornato da Active Directory. Per risolvere l'errore, chiudere la finestra corrente e aprire un nuovo Lync Server Management Shell ed eseguire di nuovo il comando.



</div>

![Output dell'errore di Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Output dell'errore di Move-CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

