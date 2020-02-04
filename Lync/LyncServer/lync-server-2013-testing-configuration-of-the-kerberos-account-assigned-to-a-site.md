---
title: Verifica della configurazione dell'account Kerberos assegnato a un sito
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
ms.openlocfilehash: c096edc0267501bb17870a5c018e4b6b0c513422
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="fd6a8-102">Verifica della configurazione dell'account Kerberos assegnato a un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd6a8-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd6a8-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fd6a8-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd6a8-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="fd6a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fd6a8-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="fd6a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd6a8-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="fd6a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fd6a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd6a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd6a8-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="fd6a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fd6a8-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fd6a8-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="fd6a8-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fd6a8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd6a8-112">Description</span></span>

<span data-ttu-id="fd6a8-113">Il cmdlet Test-CsKerberosAccountAssignment consente di verificare che un account Kerberos sia associato a un sito specifico, che l'account sia configurato correttamente e che l'account funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="fd6a8-114">Gli account Kerberos sono account computer che possono fungere da entità di autenticazione per tutti i computer di un sito che eseguono Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="fd6a8-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="fd6a8-115">Poiché questi account usano il protocollo di autenticazione Kerberos, gli account sono noti come account Kerberos e il nuovo processo di autenticazione è noto come autenticazione Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="fd6a8-116">In questo modo è possibile gestire tutti i server IIS con un solo account.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="fd6a8-117">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="fd6a8-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fd6a8-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="fd6a8-118">Running the Test</span></span>

<span data-ttu-id="fd6a8-119">Per impostazione predefinita, Test-CsKerberosAccountAssignment Visualizza un output molto piccolo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="fd6a8-120">Le informazioni restituite dal cmdlet vengono invece scritte in un file HTML.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="fd6a8-121">Per questo motivo, è consigliabile includere il parametro Verbose e il parametro report ogni volta che si esegue Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="fd6a8-122">Il parametro Verbose fornirà un output leggermente più dettagliato sullo schermo durante l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="fd6a8-123">Il parametro report consente di specificare un percorso file e un nome file per il file HTML generato da Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="fd6a8-124">Se non si include il parametro di report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="fd6a8-125">Quando si esegue Test-CsKerberosAccountAssignment, è necessario specificare anche un'identità del sito.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="fd6a8-126">Gli account Kerberos vengono assegnati nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="fd6a8-127">Il comando seguente esegue Test-CsKerberosAccountAssignment e salva l'output in un file denominato C:\\logs\\KerberosTest. html:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="fd6a8-128">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="fd6a8-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fd6a8-129">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="fd6a8-129">Determining Success or Failure</span></span>

<span data-ttu-id="fd6a8-130">Il cmdlet Test-CsKerberosAccountAssignment non restituisce una semplice indicazione di esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="fd6a8-131">È invece necessario visualizzare il file HTML generato usando Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fd6a8-132">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="fd6a8-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="fd6a8-133">Ecco alcuni motivi comuni per cui Test-CsKerberosAccountAssignment potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="fd6a8-134">Potrebbe essere stata specificata un'identità di sito non corretta.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="fd6a8-135">Per restituire un elenco di identità del sito valido, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="fd6a8-136">L'identità di un sito in genere è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="fd6a8-137">sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="fd6a8-137">site:Redmond</span></span>

  - <span data-ttu-id="fd6a8-138">Al sito specificato potrebbe non essere assegnato un account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="fd6a8-139">Per determinare se un account Kerberos viene assegnato o meno a un sito, è possibile eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="fd6a8-140">L'account Kerberos potrebbe avere una password non valida.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="fd6a8-141">Se viene visualizzato il messaggio di errore seguente nel report, è probabile che sia necessario reimpostare la password dell'account Kerberos:</span><span class="sxs-lookup"><span data-stu-id="fd6a8-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="fd6a8-142">InvalidKerberosConfiguration: la configurazione Kerberos non è valida.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="fd6a8-143">InvalidKerberosConfiguration: la configurazione Kerberos in atl-cs001.litwareinc.com non è valida.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="fd6a8-144">L'account assegnato previsto è litwareinc\\kerberostest.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="fd6a8-145">Verificare che l'account non sia scaduto e che la password configurata nel computer corrisponda alla password di Active Directory dell'account.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="fd6a8-146">Puoi impostare la password usando il cmdlet [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="fd6a8-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

