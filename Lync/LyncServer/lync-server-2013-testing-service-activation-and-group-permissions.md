---
title: "Lync Server 2013: testare l'attivazione del servizio e le autorizzazioni di gruppo"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e29cafcfac7a74e43617841a174653f6072c5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530523"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="7b4dc-102">Test dell'attivazione del servizio e delle autorizzazioni di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b4dc-102">Testing service activation and group permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b4dc-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7b4dc-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b4dc-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="7b4dc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7b4dc-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="7b4dc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b4dc-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="7b4dc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7b4dc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b4dc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b4dc-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="7b4dc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7b4dc-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7b4dc-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="7b4dc-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7b4dc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b4dc-112">Description</span></span>

<span data-ttu-id="7b4dc-113">Il cmdlet Test-CsTopology consente di verificare che Lync Server 2013 funzioni correttamente in un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="7b4dc-114">Per impostazione predefinita, il cmdlet controlla l'intera infrastruttura di Lync Server, verificando che i servizi necessari siano in esecuzione e che siano impostate le autorizzazioni appropriate per questi servizi e per i gruppi di protezione universali creati durante l'installazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="7b4dc-115">Oltre a verificare la validità dell'installazione di Lync Server, Test-CsTopology consente inoltre di controllare la validità di un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="7b4dc-116">Questo comando consente, ad esempio, di controllare lo stato di A/V Conferencing Server nel pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7b4dc-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="7b4dc-117">Running the test</span></span>

<span data-ttu-id="7b4dc-118">Per impostazione predefinita, Test-CsTopology Visualizza un output molto poco visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="7b4dc-119">Al contrario, le informazioni restituite dal cmdlet vengono scritte in un file HTML.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7b4dc-120">Il parametro report consente di specificare un percorso di file e un nome di file per il file HTML generato da Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="7b4dc-121">Se non si include il parametro report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7b4dc-122">Il comando di esempio seguente esegue Test-CsTopology e salva l'output in un file denominato C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="7b4dc-123">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="7b4dc-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7b4dc-124">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="7b4dc-124">Determining success or failure</span></span>

<span data-ttu-id="7b4dc-125">A differenza della maggior parte dei cmdlet di test, Test-CsTopology segnala l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="7b4dc-126">In parte, a causa del numero elevato di verifiche di verifica che il cmdlet deve eseguire ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="7b4dc-127">Al contrario, i dati vengono salvati in un report HTML che può quindi essere visualizzato utilizzando Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7b4dc-128">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b4dc-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="7b4dc-129">Di seguito sono riportate alcune ragioni comuni per cui Test-CsTopology potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="7b4dc-130">La replica potrebbe non essere aggiornata nel computer di test.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="7b4dc-131">È possibile controllare lo stato della replica corrente per un computer eseguendo il cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="7b4dc-132">Se lo stato di replica non è aggiornato, è possibile forzare manualmente la replica a essere eseguita utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="7b4dc-133">Potrebbe essere necessario abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-133">The topology might have to be enabled.</span></span> <span data-ttu-id="7b4dc-134">Se si modifica la topologia di Lync Server (modifiche che potrebbero influire sul computer locale), è necessario abilitare la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="7b4dc-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="7b4dc-135">È possibile abilitare la topologia in qualsiasi momento eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="7b4dc-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

