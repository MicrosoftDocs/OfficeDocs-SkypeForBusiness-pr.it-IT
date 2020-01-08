---
title: "Lync Server 2013: verificare l'attivazione del servizio e le autorizzazioni di gruppo"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="41bb5-102">Test dell'attivazione del servizio e delle autorizzazioni di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41bb5-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41bb5-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="41bb5-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41bb5-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="41bb5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="41bb5-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="41bb5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41bb5-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="41bb5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="41bb5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41bb5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41bb5-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="41bb5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="41bb5-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="41bb5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="41bb5-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="41bb5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="41bb5-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41bb5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="41bb5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41bb5-112">Description</span></span>

<span data-ttu-id="41bb5-113">Il cmdlet Test-CsTopology consente di verificare che Lync Server 2013 funzioni correttamente in un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="41bb5-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="41bb5-114">Per impostazione predefinita, il cmdlet controlla l'intera infrastruttura Lync Server, verificando che i servizi necessari siano in corso e che siano impostate le autorizzazioni appropriate per questi servizi e per i gruppi di sicurezza universale creati durante l'installazione di Lync Server .</span><span class="sxs-lookup"><span data-stu-id="41bb5-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="41bb5-115">Oltre a verificare la validità dell'installazione di Lync Server, Test-CsTopology consente anche di verificare la validità di un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="41bb5-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="41bb5-116">Questo comando, ad esempio, controlla lo stato di un/V Conferencing Server nel pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="41bb5-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="41bb5-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="41bb5-117">Running the test</span></span>

<span data-ttu-id="41bb5-118">Per impostazione predefinita, Test-CsTopology Visualizza un output molto piccolo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="41bb5-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="41bb5-119">Le informazioni restituite dal cmdlet vengono invece scritte in un file HTML.</span><span class="sxs-lookup"><span data-stu-id="41bb5-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="41bb5-120">Il parametro report consente di specificare un percorso file e un nome file per il file HTML generato da Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="41bb5-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="41bb5-121">Se non si include il parametro di report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="41bb5-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="41bb5-122">Il comando di esempio seguente esegue Test-CsTopology e salva l'output in un file denominato C:\\logs\\ComputerTest. html:</span><span class="sxs-lookup"><span data-stu-id="41bb5-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="41bb5-123">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="41bb5-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="41bb5-124">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="41bb5-124">Determining success or failure</span></span>

<span data-ttu-id="41bb5-125">A differenza della maggior parte dei cmdlet di test, Test-CsTopology non riporta l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="41bb5-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="41bb5-126">In parte, questo è dovuto al numero elevato di controlli di verifica che il cmdlet deve apportare ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="41bb5-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="41bb5-127">I dati vengono invece salvati in un report HTML che può essere visualizzato tramite Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="41bb5-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="41bb5-128">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="41bb5-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="41bb5-129">Ecco alcuni motivi comuni per cui Test-CsTopology potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="41bb5-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="41bb5-130">La replica potrebbe non essere aggiornata nel computer di test.</span><span class="sxs-lookup"><span data-stu-id="41bb5-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="41bb5-131">Per controllare lo stato di replica corrente di un computer, è possibile eseguire il cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="41bb5-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="41bb5-132">Se lo stato di replica non è aggiornato, è possibile forzare manualmente la replica in modo che venga eseguita usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="41bb5-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="41bb5-133">Potrebbe essere necessario abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="41bb5-133">The topology might have to be enabled.</span></span> <span data-ttu-id="41bb5-134">Se si modifica la topologia di Lync Server (modifiche che potrebbero influire sul computer locale), è necessario abilitare la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="41bb5-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="41bb5-135">È possibile abilitare la topologia in qualsiasi momento eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="41bb5-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

