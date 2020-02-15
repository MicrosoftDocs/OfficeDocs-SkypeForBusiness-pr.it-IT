---
title: 'Lync Server 2013: testing dei servizi di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd9f2924d2f66e27e3893ccca0502915ee8a3e97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="8c5e4-102">Test dei servizi di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5e4-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c5e4-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8c5e4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5e4-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="8c5e4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8c5e4-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="8c5e4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5e4-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="8c5e4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8c5e4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c5e4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5e4-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="8c5e4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8c5e4-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8c5e4-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="8c5e4-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8c5e4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c5e4-112">Description</span></span>

<span data-ttu-id="8c5e4-113">Test-CsComputer verifica lo stato di tutti i servizi di Lync Server 2013 in esecuzione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="8c5e4-114">(Test-CsComputer può essere eseguito solo localmente, non può essere eseguito da un'istanza remota di Windows PowerShell). Il cmdlet verifica inoltre se le porte del firewall appropriate sono aperte nel computer e determina se i gruppi di Active Directory creati al momento dell'installazione di Lync Server 2013 sono stati aggiunti ai gruppi locali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="8c5e4-115">Ad esempio, Test-CsComputer verificherà che il gruppo di Active Directory RTCUniversalUserAdmins sia stato aggiunto al gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="8c5e4-116">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="8c5e4-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8c5e4-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="8c5e4-117">Running the test</span></span>

<span data-ttu-id="8c5e4-118">Il cmdlet Test-CsComputer può essere eseguito solo nel computer locale, non è possibile chiamare Test-CsComputer da un'istanza remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="8c5e4-119">Per impostazione predefinita, il cmdlet Test-CsComputer consente di visualizzare un output molto poco visualizzato sullo schermo, invece le informazioni restituite dall'opzione vengono scritte in un file HTML.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="8c5e4-120">Per questo motivo, si consiglia di includere il parametro Verbose e il parametro report ogni volta che si esegue Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="8c5e4-121">Il parametro Verbose fornirà un output leggermente più dettagliato sullo schermo durante l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="8c5e4-122">Il parametro report consente di specificare un percorso di file e un nome di file per il file HTML generato da Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="8c5e4-123">Se non si include il parametro report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="8c5e4-124">Nel comando di esempio seguente viene eseguito test-CsComputer e l'output viene salvato in un file denominato C\\:\\logs ComputerTest. html:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="8c5e4-125">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="8c5e4-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8c5e4-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="8c5e4-126">Determining success or failure</span></span>

<span data-ttu-id="8c5e4-127">A causa del numero di verifiche di verifica eseguite, Test-CsComputer non riporta un semplice **Sì, il test ha avuto esito positivo** o **No, il test ha avuto esito negativo**.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="8c5e4-128">Al contrario, è necessario visualizzare il file HTML generato tramite Internet Explorer per determinare l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8c5e4-129">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="8c5e4-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="8c5e4-130">Di seguito sono riportate alcune ragioni comuni per cui Test-CsComputer potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="8c5e4-131">Il computer di testing potrebbe non essere abilitato per l'utilizzo con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="8c5e4-132">Ciò può verificarsi se i servizi Lync Server o i ruoli del server nel computer sono stati modificati e non è stato eseguito il cmdlet Enable-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="8c5e4-133">Per risolvere il problema, eseguire il comando indicato:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="8c5e4-134">La replica potrebbe non essere aggiornata nel computer di test.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="8c5e4-135">È possibile controllare lo stato della replica corrente per un computer eseguendo il cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="8c5e4-136">Se lo stato di replica non è aggiornato, è possibile forzare manualmente la replica a essere eseguita utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="8c5e4-137">Potrebbe essere necessario abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-137">The topology might have to be enabled.</span></span> <span data-ttu-id="8c5e4-138">Se si modifica la topologia di Lync Server (modifiche che potrebbero influire sul computer locale), è necessario abilitare la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="8c5e4-139">È possibile abilitare la topologia in qualsiasi momento eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="8c5e4-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

