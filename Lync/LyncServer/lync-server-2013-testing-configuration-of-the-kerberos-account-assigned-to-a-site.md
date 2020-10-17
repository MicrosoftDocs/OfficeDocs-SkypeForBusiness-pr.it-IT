---
title: Verifica della configurazione dell'account Kerberos assegnato a un sito
description: Verifica della configurazione dell'account Kerberos assegnato a un sito.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560692"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="87e0a-103">Verifica della configurazione dell'account Kerberos assegnato a un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87e0a-103">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87e0a-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="87e0a-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87e0a-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="87e0a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="87e0a-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="87e0a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87e0a-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="87e0a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="87e0a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87e0a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87e0a-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="87e0a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="87e0a-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="87e0a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="87e0a-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="87e0a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="87e0a-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="87e0a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="87e0a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87e0a-113">Description</span></span>

<span data-ttu-id="87e0a-114">Il cmdlet Test-CsKerberosAccountAssignment consente di verificare che un account Kerberos sia associato a un determinato sito, che questo account sia configurato correttamente e che l'account funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="87e0a-114">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="87e0a-115">Gli account Kerberos sono account computer che possono fungere da entità di autenticazione per tutti i computer di un sito in cui è in esecuzione Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="87e0a-115">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="87e0a-116">Poiché tali account utilizzano il protocollo di autenticazione Kerberos, gli account sono noti come account Kerberos e il nuovo processo di autenticazione è noto come autenticazione Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="87e0a-116">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="87e0a-117">In questo modo è possibile gestire tutti i server IIS utilizzando un singolo account.</span><span class="sxs-lookup"><span data-stu-id="87e0a-117">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="87e0a-118">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="87e0a-118">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="87e0a-119">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="87e0a-119">Running the Test</span></span>

<span data-ttu-id="87e0a-120">Per impostazione predefinita, Test-CsKerberosAccountAssignment Visualizza un output molto poco visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="87e0a-120">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="87e0a-121">Al contrario, le informazioni restituite dal cmdlet vengono scritte in un file HTML.</span><span class="sxs-lookup"><span data-stu-id="87e0a-121">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="87e0a-122">Per questo motivo, si consiglia di includere il parametro Verbose e il parametro report ogni volta che si esegue Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="87e0a-122">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="87e0a-123">Il parametro Verbose fornirà un output leggermente più dettagliato sullo schermo durante l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="87e0a-123">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="87e0a-124">Il parametro report consente di specificare un percorso di file e un nome di file per il file HTML generato da Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="87e0a-124">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="87e0a-125">Se non si include il parametro report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="87e0a-125">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="87e0a-126">Quando si esegue il Test-CsKerberosAccountAssignment, è inoltre necessario specificare un'identità del sito.</span><span class="sxs-lookup"><span data-stu-id="87e0a-126">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="87e0a-127">Gli account Kerberos vengono assegnati nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="87e0a-127">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="87e0a-128">Il comando seguente consente di eseguire Test-CsKerberosAccountAssignment e di salvare l'output in un file denominato C: \\ Logs \\KerberosTest.html:</span><span class="sxs-lookup"><span data-stu-id="87e0a-128">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="87e0a-129">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="87e0a-129">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="87e0a-130">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="87e0a-130">Determining Success or Failure</span></span>

<span data-ttu-id="87e0a-131">Il cmdlet Test-CsKerberosAccountAssignment non restituisce una semplice indicazione di esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="87e0a-131">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="87e0a-132">Al contrario, è necessario visualizzare il file HTML generato tramite Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="87e0a-132">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="87e0a-133">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="87e0a-133">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="87e0a-134">Di seguito sono riportate alcune ragioni comuni per cui Test-CsKerberosAccountAssignment potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="87e0a-134">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="87e0a-135">È possibile che sia stata specificata un'identità di sito non corretta.</span><span class="sxs-lookup"><span data-stu-id="87e0a-135">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="87e0a-136">Per restituire un elenco di identità del sito valido, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="87e0a-136">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="87e0a-137">L'identità di un sito in genere è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="87e0a-137">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="87e0a-138">sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="87e0a-138">site:Redmond</span></span>

  - <span data-ttu-id="87e0a-139">Il sito specificato potrebbe non disporre di un account Kerberos assegnato.</span><span class="sxs-lookup"><span data-stu-id="87e0a-139">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="87e0a-140">È possibile determinare se un account Kerberos è assegnato o meno a un sito eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="87e0a-140">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="87e0a-141">È possibile che l'account Kerberos disponga di una password non valida.</span><span class="sxs-lookup"><span data-stu-id="87e0a-141">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="87e0a-142">Se viene visualizzato il messaggio di errore riportato di seguito nel report, è probabile che sia necessario reimpostare la password dell'account Kerberos:</span><span class="sxs-lookup"><span data-stu-id="87e0a-142">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="87e0a-143">InvalidKerberosConfiguration: la configurazione Kerberos non è valida.</span><span class="sxs-lookup"><span data-stu-id="87e0a-143">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="87e0a-144">InvalidKerberosConfiguration: la configurazione Kerberos in atl-cs001.litwareinc.com non è valida.</span><span class="sxs-lookup"><span data-stu-id="87e0a-144">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="87e0a-145">L'account assegnato previsto è litwareinc \\ kerberostest.</span><span class="sxs-lookup"><span data-stu-id="87e0a-145">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="87e0a-146">Assicurarsi che l'account non sia scaduto e che la password configurata sul computer corrisponda alla password di Active Directory dell'account.</span><span class="sxs-lookup"><span data-stu-id="87e0a-146">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="87e0a-147">È possibile impostare la password utilizzando il cmdlet [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="87e0a-147">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

