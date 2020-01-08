---
title: Spostare le directory conferenze di Lync Server 2010 in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa32bb5be86d72d4f18d11bb85d5ce0b57a96725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="9241e-102">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="9241e-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9241e-103">_**Argomento Ultima modifica:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="9241e-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="9241e-104">Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory di conferenza nel pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9241e-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="9241e-105">Per trasferire una directory di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9241e-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="9241e-106">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9241e-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="9241e-107">Per ottenere l'identità delle directory conferenza nell'organizzazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="9241e-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="9241e-108">Il comando precedente restituisce tutte le directory conferenza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9241e-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="9241e-109">Per questo motivo, potresti voler limitare i risultati al pool da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9241e-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="9241e-110">Se ad esempio si sta disattivando il pool con il nome di dominio completo (FQDN) pool01.contoso.net, usare questo comando per limitare i dati restituiti alle directory della conferenza da tale pool:</span><span class="sxs-lookup"><span data-stu-id="9241e-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="9241e-111">Questo comando restituisce solo le directory della conferenza in cui la proprietà ServiceID contiene il nome FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="9241e-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="9241e-112">Per trasferire le directory conferenza, eseguire il comando seguente per ogni directory di conferenza nel pool:</span><span class="sxs-lookup"><span data-stu-id="9241e-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="9241e-113">Ad esempio, per trasferire la directory della conferenza 3, usare questo comando specificando un pool di Lync Server 2013 come TargetPool:</span><span class="sxs-lookup"><span data-stu-id="9241e-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="9241e-114">Se si vuole trasferire tutte le directory conferenza in un pool, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9241e-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="9241e-115">Vedere il documento "disinstallazione di Microsoft Lync Server 2010 e rimozione dei ruoli del server" (da [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)cui è possibile scaricare) per istruzioni dettagliate su come rimuovere i pool di Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="9241e-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="9241e-116">Quando si spostano le directory conferenza, è possibile che venga visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="9241e-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="9241e-117">Questo errore si verifica in genere quando Lync Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività.</span><span class="sxs-lookup"><span data-stu-id="9241e-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="9241e-118">Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza della shell ed eseguire di nuovo il comando per passare alla directory della conferenza.</span><span class="sxs-lookup"><span data-stu-id="9241e-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

