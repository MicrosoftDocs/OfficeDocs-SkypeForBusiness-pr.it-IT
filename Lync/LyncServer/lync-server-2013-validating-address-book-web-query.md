---
title: 'Lync Server 2013: convalida della query Web Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d6a38c0c1d8a67977f9dd66da2a94b51a4f9ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="c75ad-102">Convalida della query Web della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c75ad-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c75ad-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c75ad-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c75ad-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="c75ad-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c75ad-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="c75ad-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c75ad-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="c75ad-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c75ad-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c75ad-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c75ad-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="c75ad-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c75ad-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c75ad-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c75ad-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="c75ad-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="c75ad-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c75ad-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c75ad-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c75ad-112">Description</span></span>

<span data-ttu-id="c75ad-113">Il cmdlet Test-CsAddressBookWebQuery consente agli amministratori di verificare che gli utenti possano usare il servizio query Web Rubrica per cercare un contatto specifico.</span><span class="sxs-lookup"><span data-stu-id="c75ad-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="c75ad-114">Quando si esegue il cmdlet, Test-CsAddressBookWebQuery si connette prima al servizio ticket web per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c75ad-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="c75ad-115">Se l'autenticazione ha esito positivo, il cmdlet si connetterà al servizio query Web della Rubrica e cercherà il contatto specificato.</span><span class="sxs-lookup"><span data-stu-id="c75ad-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="c75ad-116">Se tale contatto viene trovato, il cmdlet tenterà di restituire tali informazioni al computer locale.</span><span class="sxs-lookup"><span data-stu-id="c75ad-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="c75ad-117">Il test verrà contrassegnato come successo solo se tutti questi passaggi possono essere completati.</span><span class="sxs-lookup"><span data-stu-id="c75ad-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="c75ad-118">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="c75ad-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c75ad-119">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="c75ad-119">Running the test</span></span>

<span data-ttu-id="c75ad-120">Il cmdlet Test-CsAddressBookWebQuery può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c75ad-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="c75ad-121">Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server e l'indirizzo SIP dell'utente che funge da destinazione della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c75ad-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="c75ad-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c75ad-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="c75ad-123">Per eseguire questo controllo usando un account utente effettivo, devi creare un oggetto credenziali di Windows PowerShell che contiene un nome utente e una password validi.</span><span class="sxs-lookup"><span data-stu-id="c75ad-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="c75ad-124">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando il codice chiama Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="c75ad-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="c75ad-125">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="c75ad-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c75ad-126">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="c75ad-126">Determining success or failure</span></span>

<span data-ttu-id="c75ad-127">Se l'utente specificato può connettersi al servizio Rubrica e recuperare l'indirizzo utente di destinazione, si restituirà l'output simile a quello con la proprietà Result contrassegnata come riuscita:</span><span class="sxs-lookup"><span data-stu-id="c75ad-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="c75ad-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="c75ad-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="c75ad-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c75ad-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c75ad-130">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="c75ad-130">Result : Success</span></span>

<span data-ttu-id="c75ad-131">Latenza: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="c75ad-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="c75ad-132">Errore</span><span class="sxs-lookup"><span data-stu-id="c75ad-132">Error :</span></span>

<span data-ttu-id="c75ad-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="c75ad-133">Diagnosis :</span></span>

<span data-ttu-id="c75ad-134">Se l'utente specificato non riesce a connettersi o se l'indirizzo utente di destinazione non può essere recuperato, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="c75ad-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c75ad-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="c75ad-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="c75ad-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c75ad-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c75ad-137">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="c75ad-137">Result : Failure</span></span>

<span data-ttu-id="c75ad-138">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c75ad-138">Latency : 00:00:00</span></span>

<span data-ttu-id="c75ad-139">Errore: la richiesta di un servizio Web della Rubrica non è riuscita con il codice di risposta</span><span class="sxs-lookup"><span data-stu-id="c75ad-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="c75ad-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="c75ad-140">NoEntryFound.</span></span>

<span data-ttu-id="c75ad-141">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="c75ad-141">Diagnosis :</span></span>

<span data-ttu-id="c75ad-142">L'output precedente dichiara che il test non è riuscito perché l'utente di destinazione non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="c75ad-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="c75ad-143">È possibile determinare se un indirizzo SIP valido è stato passato a Test-CsAddressBookWebQuery eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c75ad-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="c75ad-144">Se Test-CsAddressBookWebQuery non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="c75ad-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="c75ad-145">Quando viene incluso il parametro Verbose, Test-CsAddressBookWebQuery restituirà un account dettagliato di ogni azione provata durante il controllo della capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c75ad-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="c75ad-146">Ad esempio, questo output indica che Test-CsAddressBookWebQuery è stato in grado di connettersi al servizio Rubrica, ma non è stato in grado di individuare l'indirizzo SIP di destinazione:</span><span class="sxs-lookup"><span data-stu-id="c75ad-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="c75ad-147">Attività' QueryAddressBookWebService ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="c75ad-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="c75ad-148">Servizio query Web della rubrica chiamate.</span><span class="sxs-lookup"><span data-stu-id="c75ad-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="c75ad-149">URL ABWS =</span><span class="sxs-lookup"><span data-stu-id="c75ad-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="c75ad-150">Eccezione query Rubrica: la richiesta di servizio Web della Rubrica non è riuscita con il codice di risposta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="c75ad-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c75ad-151">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="c75ad-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="c75ad-152">Ecco alcuni motivi comuni per cui Test-CsAddressBookWebQuery potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="c75ad-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="c75ad-153">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="c75ad-153">You specified an invalid user account.</span></span> <span data-ttu-id="c75ad-154">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c75ad-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="c75ad-155">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c75ad-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="c75ad-156">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c75ad-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="c75ad-157">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c75ad-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="c75ad-158">L'utente di destinazione potrebbe non essere presente nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="c75ad-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="c75ad-159">La Rubrica potrebbe non essere completamente aggiornata e replicata.</span><span class="sxs-lookup"><span data-stu-id="c75ad-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="c75ad-160">È possibile forzare l'aggiornamento di tutti i server della rubrica dell'organizzazione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c75ad-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

