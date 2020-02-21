---
title: 'Lync Server 2013: testare i diritti relativi alla topologia di amministratore'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="77ac3-102">Testare i diritti relativi alla topologia di amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ac3-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77ac3-103">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="77ac3-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77ac3-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="77ac3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="77ac3-105">Dopo la distribuzione iniziale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77ac3-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="77ac3-106">Se necessario, se si verificano problemi relativi alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="77ac3-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77ac3-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="77ac3-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="77ac3-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77ac3-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77ac3-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="77ac3-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="77ac3-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="77ac3-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="77ac3-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="77ac3-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="77ac3-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="77ac3-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="77ac3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77ac3-113">Description</span></span>

<span data-ttu-id="77ac3-114">Per impostazione predefinita, solo gli amministratori di dominio possono abilitare una topologia di Lync Server e apportare modifiche importanti all'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77ac3-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="77ac3-115">Non si tratta di un problema a condizione che gli amministratori di dominio e gli amministratori di Lync Server siano identici. In molte organizzazioni gli amministratori di Lync Server non contengono diritti amministrativi per l'intero dominio.</span><span class="sxs-lookup"><span data-stu-id="77ac3-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="77ac3-116">Per impostazione predefinita, questo significa che tali amministratori (definiti come membri del gruppo RTCUniversalServerAdmins) non possono apportare modifiche alla topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77ac3-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="77ac3-117">Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di apportare modifiche alla topologia, è necessario assegnare le autorizzazioni di Active Directory necessarie utilizzando il cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="77ac3-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="77ac3-118">Il cmdlet Test-CsSetupPermission verifica che le autorizzazioni necessarie per l'installazione di Lync Server o di uno dei relativi componenti siano configurate nel contenitore di Active Directory specificato.</span><span class="sxs-lookup"><span data-stu-id="77ac3-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="77ac3-119">Se le autorizzazioni non sono assegnate, è possibile eseguire il cmdlet Grant-CsSetupPermission per assegnare ai membri del gruppo RTCUniversalServerAdmins il diritto di installare e abilitare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77ac3-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77ac3-120">Per un elenco dettagliato delle autorizzazioni assegnate da Grant-CsSetupPermission, vedere il post di Blog <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission e Grant-CsOUPermission</A>.</span><span class="sxs-lookup"><span data-stu-id="77ac3-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="77ac3-121">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="77ac3-121">Running the test</span></span>

<span data-ttu-id="77ac3-122">Per determinare se le autorizzazioni di installazione sono assegnate a un contenitore di Active Directory, chiamare il cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="77ac3-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="77ac3-123">Specificare il nome distinto del contenitore da controllare.</span><span class="sxs-lookup"><span data-stu-id="77ac3-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="77ac3-124">Ad esempio, questo comando consente di verificare le autorizzazioni di installazione sul contenitore ou = CsServers, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="77ac3-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="77ac3-125">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="77ac3-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="77ac3-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="77ac3-126">Determining success or failure</span></span>

<span data-ttu-id="77ac3-127">Se Test-CsSetupPermission determina che le autorizzazioni necessarie sono già state impostate su un contenitore di Active Directory, il cmdlet restituirà il valore true:</span><span class="sxs-lookup"><span data-stu-id="77ac3-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="77ac3-128">True</span><span class="sxs-lookup"><span data-stu-id="77ac3-128">True</span></span>

<span data-ttu-id="77ac3-129">Se le autorizzazioni non sono impostate, Test-CsSetupPermission restituirà il valore false.</span><span class="sxs-lookup"><span data-stu-id="77ac3-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="77ac3-130">Si noti che questo valore verrà in genere racchiuso in molti messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="77ac3-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="77ac3-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="77ac3-131">For example:</span></span>

<span data-ttu-id="77ac3-132">AVVISO: voce di controllo di accesso (ACE) atl-cs\\-001 RTCUniversalServerAdmins; Consentire ExtendedRight; Nessuno Nessuno 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="77ac3-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="77ac3-133">AVVISO: le voci di controllo di accesso (ACE) dell'oggetto "CN = Computers, DC = litwareinc, DC = com" non sono pronte.</span><span class="sxs-lookup"><span data-stu-id="77ac3-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="77ac3-134">False</span><span class="sxs-lookup"><span data-stu-id="77ac3-134">False</span></span>

<span data-ttu-id="77ac3-135">AVVISO: l'elaborazione di "Test-CsSetupPermission" è stata completata con gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="77ac3-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="77ac3-136">gli avvisi "2" sono stati registrati durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="77ac3-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="77ac3-137">AVVISO: i risultati dettagliati sono disponibili in "C\\:\\Users\\admin\\\\AppData\\local Temp Test-CsSetupPermission-1da99ba6-Abe2-45e4-8b16-dfd244763118. html".</span><span class="sxs-lookup"><span data-stu-id="77ac3-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="77ac3-138">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="77ac3-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="77ac3-139">Sebbene esistano eccezioni rare, se Test-CsSetupPermission ha esito negativo che in genere significa che le autorizzazioni di installazione non sono assegnate per il contenitore di Active Directory specificato.</span><span class="sxs-lookup"><span data-stu-id="77ac3-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="77ac3-140">Tali autorizzazioni possono essere assegnate utilizzando il cmdlet Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="77ac3-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="77ac3-141">Ad esempio, questo comando concede le autorizzazioni di installazione al contenitore computer nel dominio litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="77ac3-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="77ac3-142">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="77ac3-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

