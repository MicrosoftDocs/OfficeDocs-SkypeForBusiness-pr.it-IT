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

# <a name="move-conference-directories"></a><span data-ttu-id="87112-102">Trasferire le directory conferenza</span><span class="sxs-lookup"><span data-stu-id="87112-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87112-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="87112-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="87112-104">Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory di conferenza nel pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="87112-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="87112-105">Per trasferire una directory di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87112-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="87112-106">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="87112-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="87112-107">Per ottenere l'identità delle directory conferenza nell'organizzazione, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="87112-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="87112-108">Poiché questo cmdlet restituisce tutte le directory conferenza dell'organizzazione, è consigliabile limitare i risultati solo al pool che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="87112-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="87112-109">Ad esempio, se vuoi rimuovere un pool con il nome di dominio completo (FQDN) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="87112-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="87112-110">Questo cmdlet restituisce tutte le directory conferenza in cui l'ID servizio contiene l'FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="87112-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="87112-111">Per trasferire le directory conferenza, eseguire le operazioni seguenti per ogni directory di conferenza nel pool:</span><span class="sxs-lookup"><span data-stu-id="87112-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="87112-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="87112-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="87112-113">Potrebbe verificarsi un errore, illustrato di seguito, causato da Lync Server Management Shell che richiede un set di autorizzazioni aggiornato da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="87112-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="87112-114">Per risolvere l'errore, chiudere la finestra corrente e aprire un nuovo Lync Server Management Shell ed eseguire di nuovo il comando.</span><span class="sxs-lookup"><span data-stu-id="87112-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="87112-115">![Output dell'errore di Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Output dell'errore di Move-CsConferenceDirectory")</span><span class="sxs-lookup"><span data-stu-id="87112-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

