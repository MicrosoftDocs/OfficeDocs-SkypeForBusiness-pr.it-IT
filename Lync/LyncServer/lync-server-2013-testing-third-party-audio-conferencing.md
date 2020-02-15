---
title: 'Lync Server 2013: testing di servizi di audioconferenza di terze parti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2897e085ea35e17d65719874ecf103ed7f1475d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="843ef-102">Verifica di servizi di audioconferenza di terze parti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="843ef-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="843ef-103">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="843ef-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="843ef-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="843ef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="843ef-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="843ef-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="843ef-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="843ef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="843ef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="843ef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="843ef-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="843ef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="843ef-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="843ef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="843ef-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="843ef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="843ef-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="843ef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="843ef-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="843ef-112">Description</span></span>

<span data-ttu-id="843ef-113">Un provider di servizi di audioconferenza è una società di terze parti che fornisce servizi di conferenza alle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="843ef-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="843ef-114">Tra le altre cose, i provider di servizi di audioconferenza consentono agli utenti che si trovano fuori sede, e non sono connessi alla rete aziendale o Internet, di partecipare alla parte audio di una conferenza o di una riunione.</span><span class="sxs-lookup"><span data-stu-id="843ef-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="843ef-115">Tali provider offrono spesso servizi di qualità elevata quali traduzione immediata, trascrizione e assistenza diretta di un operatore durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="843ef-116">Il cmdlet **test-CsAudioConferencingProvider** viene utilizzato per verificare che un utente sia in grado di effettuare una connessione al proprio provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="843ef-117">Si noti che questo cmdlet può essere eseguito in uno dei due modi.</span><span class="sxs-lookup"><span data-stu-id="843ef-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="843ef-118">Molti amministratori utilizzeranno i cmdlet CsHealthMonitoringConfiguration per configurare utenti di test per ciascuno dei propri pool di registrazione.</span><span class="sxs-lookup"><span data-stu-id="843ef-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="843ef-119">Questi utenti di test sono costituiti da una coppia di account utente preconfigurati per l'utilizzo con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="843ef-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="843ef-120">In genere si tratta di account di prova e non di account che appartengono a utenti effettivi. Se gli utenti di test sono configurati per un pool, gli amministratori possono eseguire il cmdlet **test-CsAudioConferencingProvider** su tale pool senza dover specificare l'identità (e fornire le credenziali per) dell'account utente coinvolto nel test.</span><span class="sxs-lookup"><span data-stu-id="843ef-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="843ef-121">In alternativa, gli amministratori possono eseguire il cmdlet **test-CsAudioConferencingProvider** utilizzando un account utente effettivo.</span><span class="sxs-lookup"><span data-stu-id="843ef-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="843ef-122">In questo caso, è necessario specificare nome di accesso e password per l'account.</span><span class="sxs-lookup"><span data-stu-id="843ef-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="843ef-123">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="843ef-123">Running the test</span></span>

<span data-ttu-id="843ef-124">Nell'esempio 1 viene verificato se un utente di prova definito per il pool atl-cs-001.litwareinc.com è in grado di connettersi al proprio provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="843ef-125">Questo comando richiede che almeno un utente di test sia definito per il pool.</span><span class="sxs-lookup"><span data-stu-id="843ef-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="843ef-126">Se non sono stati definiti utenti di test per atl-cs-001.litwareinc.com, il comando avrà esito negativo. Ciò è dovuto al fatto che il cmdlet **test-CsAudioConferencingProvider** non è in grado di riconoscere l'utente da utilizzare nel test.</span><span class="sxs-lookup"><span data-stu-id="843ef-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="843ef-127">Se non sono stati definiti utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'account utente da utilizzare per la verifica della connessione a un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="843ef-128">I comandi mostrati nell'esempio 2 consentono di verificare la possibilità di un utente\\specifico (litwareinc kenmyer) di connettersi al proprio provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="843ef-129">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet Get-Credential per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Ken di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="843ef-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="843ef-130">Poiché il nome di accesso litwareinc\\kenmyer è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Ken. L'oggetto credentials risultante viene archiviato in una variabile denominata $credential.</span><span class="sxs-lookup"><span data-stu-id="843ef-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="843ef-131">Nel secondo comando viene quindi verificato se l'utente può connettersi al proprio provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="843ef-132">Per eseguire questa attività, viene chiamato il cmdlet test-CsAudioConferencingProvider, insieme a tre parametri: TargetFqdn (il nome di dominio completo del pool di registrazione). UserCredential (l'oggetto Windows PowerShell contenente le credenziali utente di Ken di Microsoft); e UserSipAddress (l'indirizzo SIP corrispondente alle credenziali utente fornite).</span><span class="sxs-lookup"><span data-stu-id="843ef-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="843ef-133">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="843ef-133">Determining success or failure</span></span>

<span data-ttu-id="843ef-134">Se il provider di servizi di audioconferenza è configurato correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="843ef-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="843ef-135">FQDN di destinazione: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="843ef-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="843ef-136">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="843ef-136">Result : Success</span></span>

<span data-ttu-id="843ef-137">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="843ef-137">Latency : 00:00:00</span></span>

<span data-ttu-id="843ef-138">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="843ef-138">Error Message :</span></span>

<span data-ttu-id="843ef-139">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="843ef-139">Diagnosis :</span></span>

<span data-ttu-id="843ef-140">Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="843ef-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="843ef-141">FQDN di destinazione: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="843ef-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="843ef-142">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="843ef-142">Result : Failure</span></span>

<span data-ttu-id="843ef-143">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="843ef-143">Latency : 00:00:00</span></span>

<span data-ttu-id="843ef-144">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="843ef-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="843ef-145">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="843ef-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="843ef-146">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="843ef-146">established connection failed because connected host has</span></span>

<span data-ttu-id="843ef-147">Impossibile rispondere \[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="843ef-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="843ef-148">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="843ef-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="843ef-149">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="843ef-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="843ef-150">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="843ef-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="843ef-151">non è stato in grado di rispondere</span><span class="sxs-lookup"><span data-stu-id="843ef-151">has failed to respond</span></span>

<span data-ttu-id="843ef-152">\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="843ef-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="843ef-153">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="843ef-153">Diagnosis :</span></span>

<span data-ttu-id="843ef-154">Ad esempio, l'output precedente include la nota "la parte connessa non ha risposto correttamente" che indica in genere un problema con il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="843ef-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="843ef-155">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="843ef-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="843ef-156">Di seguito sono riportate alcune ragioni comuni per cui **test-CsAudioConferencingProvider** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="843ef-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="843ef-157">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="843ef-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="843ef-158">Come illustrato nell'esempio precedente, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="843ef-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="843ef-159">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="843ef-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="843ef-160">Si noti che il test avrà esito negativo se all'utente utilizzato dal cmdlet **test-CsAudioConferencingProvider** non è stato assegnato un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="843ef-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="843ef-161">Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="843ef-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

