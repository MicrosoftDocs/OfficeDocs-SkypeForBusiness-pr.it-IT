---
title: 'Lync Server 2013: convalida della query Web della Rubrica'
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
ms.openlocfilehash: 2db1e1e0a94a73c520a3beb0ea1375688b106cfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="a6812-102">Convalida della query Web della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6812-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6812-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a6812-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6812-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="a6812-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a6812-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="a6812-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6812-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="a6812-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a6812-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6812-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6812-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="a6812-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a6812-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a6812-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a6812-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="a6812-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="a6812-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6812-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a6812-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6812-112">Description</span></span>

<span data-ttu-id="a6812-113">Il cmdlet Test-CsAddressBookWebQuery consente agli amministratori di verificare che gli utenti possano utilizzare il servizio query Web della Rubrica per cercare un contatto specifico.</span><span class="sxs-lookup"><span data-stu-id="a6812-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="a6812-114">Quando si esegue il cmdlet, Test-CsAddressBookWebQuery si connetterà per la prima volta al servizio ticket web per essere autenticato.</span><span class="sxs-lookup"><span data-stu-id="a6812-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="a6812-115">Se l'autenticazione ha esito positivo, il cmdlet verrà quindi connesso al servizio query Web della Rubrica e cercherà il contatto specificato.</span><span class="sxs-lookup"><span data-stu-id="a6812-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="a6812-116">Se tale contatto viene individuato, il cmdlet tenta di restituire tale informazione al computer locale.</span><span class="sxs-lookup"><span data-stu-id="a6812-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="a6812-117">Il test verrà contrassegnato come esito positivo solo se tutti i passaggi possono essere completati.</span><span class="sxs-lookup"><span data-stu-id="a6812-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="a6812-118">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="a6812-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a6812-119">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="a6812-119">Running the test</span></span>

<span data-ttu-id="a6812-120">È possibile eseguire il cmdlet Test-CsAddressBookWebQuery utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6812-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="a6812-121">Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server e l'indirizzo SIP dell'utente che funge da destinazione della ricerca.</span><span class="sxs-lookup"><span data-stu-id="a6812-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="a6812-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6812-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="a6812-123">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario creare un oggetto credenziali di Windows PowerShell che contenga un nome utente e una password validi.</span><span class="sxs-lookup"><span data-stu-id="a6812-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="a6812-124">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando il codice chiama Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="a6812-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a6812-125">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="a6812-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a6812-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="a6812-126">Determining success or failure</span></span>

<span data-ttu-id="a6812-127">Se l'utente specificato è in grado di connettersi al servizio Rubrica e recuperare l'indirizzo utente di destinazione, verrà restituito un output simile al seguente, con la proprietà Result contrassegnata come operazione riuscita:</span><span class="sxs-lookup"><span data-stu-id="a6812-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="a6812-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a6812-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="a6812-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a6812-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a6812-130">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="a6812-130">Result : Success</span></span>

<span data-ttu-id="a6812-131">Latenza: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="a6812-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="a6812-132">Errore</span><span class="sxs-lookup"><span data-stu-id="a6812-132">Error :</span></span>

<span data-ttu-id="a6812-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="a6812-133">Diagnosis :</span></span>

<span data-ttu-id="a6812-134">Se l'utente specificato non è in grado di connettersi o se non è possibile recuperare l'indirizzo dell'utente di destinazione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="a6812-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a6812-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a6812-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="a6812-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a6812-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a6812-137">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="a6812-137">Result : Failure</span></span>

<span data-ttu-id="a6812-138">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a6812-138">Latency : 00:00:00</span></span>

<span data-ttu-id="a6812-139">Errore: la richiesta del servizio Web della Rubrica non è riuscita con il codice di risposta</span><span class="sxs-lookup"><span data-stu-id="a6812-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="a6812-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="a6812-140">NoEntryFound.</span></span>

<span data-ttu-id="a6812-141">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="a6812-141">Diagnosis :</span></span>

<span data-ttu-id="a6812-142">L'output precedente dichiara che il test ha avuto esito negativo perché l'utente di destinazione non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="a6812-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="a6812-143">È possibile determinare se un indirizzo SIP valido è stato passato a Test-CsAddressBookWebQuery eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a6812-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="a6812-144">Se Test-CsAddressBookWebQuery ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="a6812-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="a6812-145">Quando viene incluso il parametro Verbose, Test-CsAddressBookWebQuery restituirà un account dettagliato di ogni azione tentata durante il controllo della capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6812-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a6812-146">Ad esempio, questo output indica che Test-CsAddressBookWebQuery è stato in grado di connettersi al servizio Rubrica, ma non è stato in grado di individuare l'indirizzo SIP di destinazione:</span><span class="sxs-lookup"><span data-stu-id="a6812-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="a6812-147">Attività' QueryAddressBookWebService ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="a6812-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="a6812-148">Servizio query Web della rubrica chiamante.</span><span class="sxs-lookup"><span data-stu-id="a6812-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="a6812-149">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="a6812-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="a6812-150">Eccezione della query della Rubrica: la richiesta del servizio Web della Rubrica non è riuscita con il codice di risposta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="a6812-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a6812-151">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="a6812-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="a6812-152">Di seguito sono riportate alcune ragioni comuni per cui Test-CsAddressBookWebQuery potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="a6812-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="a6812-153">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="a6812-153">You specified an invalid user account.</span></span> <span data-ttu-id="a6812-154">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a6812-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a6812-155">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6812-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="a6812-156">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a6812-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a6812-157">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6812-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="a6812-158">L'utente di destinazione potrebbe non trovarsi nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="a6812-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="a6812-159">La Rubrica potrebbe non essere completamente aggiornata e replicata.</span><span class="sxs-lookup"><span data-stu-id="a6812-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="a6812-160">È possibile forzare un aggiornamento di tutti i server della Rubrica nell'organizzazione eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a6812-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

