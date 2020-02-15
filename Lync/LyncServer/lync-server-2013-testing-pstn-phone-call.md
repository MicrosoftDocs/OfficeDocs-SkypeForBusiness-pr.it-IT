---
title: 'Lync Server 2013: testing PSTN Phone Call'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4092f728cc691ab73432d7ca853f6441728b5713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="65621-102">Testing PSTN Phone Call in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65621-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65621-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="65621-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65621-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="65621-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="65621-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="65621-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65621-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="65621-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="65621-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65621-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65621-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="65621-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="65621-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="65621-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="65621-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="65621-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="65621-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65621-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="65621-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65621-112">Description</span></span>

<span data-ttu-id="65621-113">Il cmdlet Test-CsPstnOutboundCall verifica la capacità di un utente di effettuare una chiamata a un numero di telefono che si trova nella rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="65621-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="65621-114">Quando si esegue Test-CsPstnOutboundCall, il cmdlet tenta innanzitutto di accedere all'utente di test su Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65621-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="65621-115">Se l'accesso ha esito positivo, il cmdlet tenterà di effettuare una chiamata telefonica sul gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="65621-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="65621-116">Questa telefonata verrà effettuata utilizzando il dial plan, il criterio vocale e gli altri criteri e le impostazioni assegnati all'account di test.</span><span class="sxs-lookup"><span data-stu-id="65621-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="65621-117">Quando si riceve una risposta alla chiamata, il cmdlet invia codici DTMF (Dual-Tone Multi-Frequency) sulla rete per verificare la connettività multimediale.</span><span class="sxs-lookup"><span data-stu-id="65621-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="65621-118">Nel corso del test, il cmdlet Test-CsPstnOutboundCall effettua una vera chiamata telefonica: il telefono di destinazione squillerà e sarà necessario rispondere affinché il test possa considerarsi riuscito.</span><span class="sxs-lookup"><span data-stu-id="65621-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="65621-119">Questa chiamata deve essere terminata manualmente dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="65621-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="65621-120">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="65621-120">Running the test</span></span>

<span data-ttu-id="65621-121">È possibile eseguire il cmdlet Test-CsPstnOutboundCall utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65621-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="65621-122">Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo del pool di Lync Server da testare e il numero di telefono PSTN chiamato.</span><span class="sxs-lookup"><span data-stu-id="65621-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="65621-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="65621-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="65621-124">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="65621-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="65621-125">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsPstnOutboundCall:</span><span class="sxs-lookup"><span data-stu-id="65621-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="65621-126">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="65621-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="65621-127">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="65621-127">Determining success or failure</span></span>

<span data-ttu-id="65621-128">Se l'utente specificato è in grado di effettuare la chiamata e, se la chiamata ha esito positivo, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="65621-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="65621-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65621-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65621-130">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="65621-130">Result : Success</span></span>

<span data-ttu-id="65621-131">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="65621-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="65621-132">Errore</span><span class="sxs-lookup"><span data-stu-id="65621-132">Error :</span></span>

<span data-ttu-id="65621-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="65621-133">Diagnosis :</span></span>

<span data-ttu-id="65621-134">Se l'utente specificato non è in grado di effettuare la chiamata o se la chiamata non è stata risolta, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="65621-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="65621-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65621-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65621-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="65621-136">Result : Failure</span></span>

<span data-ttu-id="65621-137">Latenza: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="65621-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="65621-138">Errore: 403, Forbidden</span><span class="sxs-lookup"><span data-stu-id="65621-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="65621-139">Diagnosi: ErrorCode = 12001, source = atl-cs-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="65621-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="65621-140">Il criterio non contiene l'utilizzo di route telefoniche</span><span class="sxs-lookup"><span data-stu-id="65621-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="65621-141">L'output precedente dichiara che il test ha avuto esito negativo perché il criterio vocale assegnato all'utente specificato non include un utilizzo del telefono.</span><span class="sxs-lookup"><span data-stu-id="65621-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="65621-142">(Gli usi telefonici collegano i criteri vocali alle route vocali.</span><span class="sxs-lookup"><span data-stu-id="65621-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="65621-143">Senza un criterio vocale e una route vocale corrispondente, non è possibile effettuare chiamate tramite la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="65621-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="65621-144">Se Test-CsPstnOutboundCall ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="65621-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="65621-145">Quando viene incluso il parametro Verbose, Test-CsPstnOutboundCall restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65621-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="65621-146">Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:</span><span class="sxs-lookup"><span data-stu-id="65621-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="65621-147">Creazione di una chiamata audio video a' SIP: + 12065551219@litwareinc. com; user = phone '.</span><span class="sxs-lookup"><span data-stu-id="65621-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="65621-148">Eccezione ' una risposta 404 (non trovata) è stata ricevuta dalla rete e l'operazione ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="65621-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="65621-149">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="65621-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="65621-150">Di seguito sono riportate alcune ragioni comuni per cui Test-CsPstnOutboundCall potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="65621-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="65621-151">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="65621-151">You specified an invalid user account.</span></span> <span data-ttu-id="65621-152">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="65621-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="65621-153">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65621-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="65621-154">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="65621-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="65621-155">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65621-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="65621-156">I criteri vocali assegnati all'utente specificato non dispongono di un utilizzo PSTN valido.</span><span class="sxs-lookup"><span data-stu-id="65621-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="65621-157">Per determinare il criterio vocale assegnato a un utente, è possibile utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="65621-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="65621-158">È quindi possibile determinare gli utilizzi PSTN (se presenti) assegnati a tale criterio utilizzando un comando simile al seguente, in cui vengono recuperate le informazioni sul criterio vocale per utente RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="65621-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

