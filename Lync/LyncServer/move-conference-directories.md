---
title: Spostare le directory conferenze
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2de2b588d880600a4a7d8365f20423d3faf2653e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Spostare le directory conferenze

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Prima di rimuovere il pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool di Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Per spostare una directory conferenze in Lync Server 2013

1.  Aprire Lync Server Management Shell.

2.  Per ottenere l'identità delle directory conferenze nell'organizzazione, eseguire i comandi seguenti:
    
        Get-CsConferenceDirectory
    
    Dato che il cmdlet restituisce tutte le directory conferenze nell'organizzazione, può essere utile limitare i risultati solo al pool per cui si desidera rimuovere le autorizzazioni. Se si desidera rimuovere le autorizzazioni per un pool con il nome di dominio completo (FQDN) pool01.contoso.net, ad esempio, utilizzare il comando seguente:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Questo cmdlet restituisce tutte le directory conferenze in cui l'ID di servizio contiene l'FQDN pool01.contoso.net.

3.  Per spostare le directory conferenze, eseguire il comando seguente per ogni directory conferenze nel pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Ad esempio:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> È possibile che si verifichi un errore, riportato di seguito, causato da Lync Server Management Shell che richiede un set di autorizzazioni aggiornato da Active Directory. Per risolvere l'errore, chiudere la finestra corrente e aprire una nuova shell di gestione di Lync Server ed eseguire di nuovo il comando.



</div>

![Output degli errori di Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Output degli errori di Move-CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

