---
title: 'Lync Server 2013: testing PSTN peer to peer Call'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c172ea79e646e9deec1c56e792d4e7c4df3a26
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="ece76-102">Testing PSTN peer to peer Call in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece76-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ece76-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ece76-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ece76-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ece76-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ece76-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="ece76-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ece76-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="ece76-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ece76-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ece76-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ece76-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ece76-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ece76-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ece76-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ece76-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsPstnPeerToPeerCall.</span><span class="sxs-lookup"><span data-stu-id="ece76-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="ece76-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ece76-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ece76-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ece76-112">Description</span></span>

<span data-ttu-id="ece76-113">Il cmdlet Test-CsPstnPeerToPeerCall verifica la capacità di una coppia di utenti di effettuare una chiamata peer-to-peer sul gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="ece76-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="ece76-114">Quando si chiama Test-CsPstnPeerToPeerCall, il cmdlet tenterà innanzitutto di accedere a due utenti di test a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece76-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="ece76-115">Presupponendo che gli accessi abbiano esito positivo, il cmdlet utilizzerà l'utente 1 per tentare di chiamare l'utente 2 sul gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ece76-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="ece76-116">Test-CsPstnPeerToPeerCall effettuerà questa chiamata utilizzando il dial plan, il criterio vocale e altre impostazioni di configurazione e criteri assegnate all'utente di test.</span><span class="sxs-lookup"><span data-stu-id="ece76-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="ece76-117">Se il test viene pianificato, il cmdlet verificherà che l'utente 2 sia stato in grado di rispondere alla chiamata e quindi disconnettere entrambi gli account di test dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ece76-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="ece76-118">Test-CsPstnPeerToPeerCall effettua una telefonata reale, una che verifica che sia possibile effettuare una connessione e che trasmetta anche codici DTMF sulla rete per determinare se è possibile inviare un supporto tramite la connessione.</span><span class="sxs-lookup"><span data-stu-id="ece76-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="ece76-119">La chiamata viene risolta dal cmdlet stesso e non è necessaria alcuna terminazione manuale della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ece76-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="ece76-120">(Ovvero, nessuno deve rispondere e quindi riagganciare il telefono che è stato chiamato).</span><span class="sxs-lookup"><span data-stu-id="ece76-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ece76-121">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="ece76-121">Running the test</span></span>

<span data-ttu-id="ece76-122">Il cmdlet Test-CsPstnPeerToPeerCall può essere eseguito utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece76-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="ece76-123">Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="ece76-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="ece76-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ece76-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="ece76-125">Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="ece76-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ece76-126">Quando si chiama Test-CsPstnPeerToPeerCall, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:</span><span class="sxs-lookup"><span data-stu-id="ece76-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="ece76-127">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="ece76-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ece76-128">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ece76-128">Determining success or failure</span></span>

<span data-ttu-id="ece76-129">Se gli utenti specificati possono completare una chiamata peer-to-peer, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="ece76-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ece76-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ece76-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ece76-131">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="ece76-131">Result : Success</span></span>

<span data-ttu-id="ece76-132">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="ece76-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="ece76-133">Errore</span><span class="sxs-lookup"><span data-stu-id="ece76-133">Error :</span></span>

<span data-ttu-id="ece76-134">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ece76-134">Diagnosis :</span></span>

<span data-ttu-id="ece76-135">Se gli utenti specificati non sono in grado di completare una chiamata peer-to-peer, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="ece76-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ece76-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ece76-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ece76-137">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="ece76-137">Result : Failure</span></span>

<span data-ttu-id="ece76-138">Latenza: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="ece76-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="ece76-139">Errore: 403, Forbidden</span><span class="sxs-lookup"><span data-stu-id="ece76-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="ece76-140">Diagnosi: ErrorCode = 12001, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="ece76-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="ece76-141">Reason = il criterio utente non contiene l'utilizzo di route telefoniche</span><span class="sxs-lookup"><span data-stu-id="ece76-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="ece76-142">L'output precedente dichiara che il test ha avuto esito negativo perché il criterio vocale assegnato a almeno uno degli utenti specificati non include un utilizzo del telefono.</span><span class="sxs-lookup"><span data-stu-id="ece76-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="ece76-143">(Gli usi telefonici collegano i criteri vocali alle route vocali.</span><span class="sxs-lookup"><span data-stu-id="ece76-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="ece76-144">Se non si dispone di un criterio vocale e di una route vocale corrispondente, non è possibile effettuare chiamate tramite la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="ece76-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="ece76-145">Se Test-CsPstnPeerToPeerCall ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="ece76-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="ece76-146">Quando viene incluso il parametro Verbose, Test-CsPstnPeerToPeerCall restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece76-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ece76-147">Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:</span><span class="sxs-lookup"><span data-stu-id="ece76-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="ece76-148">Creazione di una chiamata audio video a' SIP: + 12065551219@litwareinc. com; user = phone '.</span><span class="sxs-lookup"><span data-stu-id="ece76-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="ece76-149">Eccezione ' una risposta 404 (non trovata) è stata ricevuta dalla rete e l'operazione ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ece76-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ece76-150">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="ece76-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="ece76-151">Di seguito sono riportate alcune ragioni comuni per cui Test-CsPstnPeerToPeerCall potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ece76-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="ece76-152">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="ece76-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="ece76-153">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ece76-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ece76-154">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece76-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="ece76-155">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ece76-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="ece76-156">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece76-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="ece76-157">I criteri vocali assegnati all'utente specificato non dispongono di un utilizzo PSTN valido.</span><span class="sxs-lookup"><span data-stu-id="ece76-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="ece76-158">Per determinare il criterio vocale assegnato a un utente, è possibile utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ece76-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="ece76-159">È quindi possibile determinare gli utilizzi PSTN (se presenti) assegnati a tale criterio utilizzando un comando simile al seguente, in cui vengono recuperate le informazioni sul criterio vocale per utente RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="ece76-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

