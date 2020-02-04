---
title: "Lync Server 2013: verificare l'accesso a Lync Phone Edition"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bfce8b1e034fd9772e10178366b0ed524fdbd55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="a1e64-102">Verificare l'accesso a Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e64-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1e64-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a1e64-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1e64-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="a1e64-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a1e64-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="a1e64-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1e64-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="a1e64-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a1e64-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1e64-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1e64-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="a1e64-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a1e64-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a1e64-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a1e64-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="a1e64-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="a1e64-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a1e64-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a1e64-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1e64-112">Description</span></span>

<span data-ttu-id="a1e64-113">Il cmdlet Test-CsPhoneBootstrap consente agli amministratori di verificare che un utente specifico, usando il numero di telefono e il PIN assegnatigli, sia in grado di accedere al sistema da un dispositivo compatibile con Lync 2013 Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a1e64-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="a1e64-114">(Nessun dispositivo è effettivamente necessario per eseguire il test).</span><span class="sxs-lookup"><span data-stu-id="a1e64-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="a1e64-115">Affinché Test-CsPhoneBootstrap esegua il controllo, il pool di registrar che ospita l'account utente testato deve essere individuabile tramite DHCP.</span><span class="sxs-lookup"><span data-stu-id="a1e64-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="a1e64-116">Per determinare se un registrar è individuabile in questo modo, usa il cmdlet Get-CsRegistrarConfiguration e controlla il valore della proprietà EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="a1e64-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="a1e64-117">Se questa proprietà è impostata su false, è necessario usare Set-CsRegistrarConfiguration per impostare il valore della proprietà su true e rendere il registrar individuabile tramite DHCP.</span><span class="sxs-lookup"><span data-stu-id="a1e64-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="a1e64-118">Questa operazione può essere eseguita anche tramite il server DHCP aziendale e la configurazione delle opzioni specifiche di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1e64-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a1e64-119">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="a1e64-119">Running the test</span></span>

<span data-ttu-id="a1e64-120">Per eseguire il cmdlet Test-CsPhoneBootstrap, è necessario specificare almeno il numero di telefono e il PIN (client Personal Identification Number) per un utente di Lync Server valido.</span><span class="sxs-lookup"><span data-stu-id="a1e64-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="a1e64-121">Ad esempio, questo comando verifica l'abilità di accesso per l'utente che ha il numero di telefono 12065551219 e il PIN 0712:</span><span class="sxs-lookup"><span data-stu-id="a1e64-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="a1e64-122">Per un controllo più completo, puoi anche includere l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a1e64-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="a1e64-123">In questo caso, il numero di telefono, il PIN client e l'indirizzo SIP devono essere tutti validi affinché il test abbia successo:</span><span class="sxs-lookup"><span data-stu-id="a1e64-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="a1e64-124">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="a1e64-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a1e64-125">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="a1e64-125">Determining success or failure</span></span>

<span data-ttu-id="a1e64-126">Se l'utente specificato è riuscito a connettersi a Lync Server, si riceverà un output simile a questo, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="a1e64-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a1e64-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="a1e64-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="a1e64-128">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="a1e64-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="a1e64-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a1e64-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a1e64-130">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="a1e64-130">Result : Success</span></span>

<span data-ttu-id="a1e64-131">Latenza: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="a1e64-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="a1e64-132">Errore</span><span class="sxs-lookup"><span data-stu-id="a1e64-132">Error :</span></span>

<span data-ttu-id="a1e64-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="a1e64-133">Diagnosis :</span></span>

<span data-ttu-id="a1e64-134">Se l'utente specificato non è in grado di effettuare una connessione, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="a1e64-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a1e64-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a1e64-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a1e64-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="a1e64-136">Result : Failure</span></span>

<span data-ttu-id="a1e64-137">Latenza: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="a1e64-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="a1e64-138">Errore: errore-Nessuna risposta ricevuta per il servizio Ticket Web.</span><span class="sxs-lookup"><span data-stu-id="a1e64-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="a1e64-139">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="a1e64-139">Diagnosis :</span></span>

<span data-ttu-id="a1e64-140">L'output precedente indica che il test non è riuscito perché il servizio ticket web non ha risposto.</span><span class="sxs-lookup"><span data-stu-id="a1e64-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="a1e64-141">Questo potrebbe essere dovuto a un problema relativo al servizio stesso oppure potrebbe essere dovuto all'indirizzo SIP, al numero di telefono o al PIN del client passato a Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="a1e64-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="a1e64-142">Puoi verificare l'indirizzo SIP e il numero di telefono dell'utente usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a1e64-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="a1e64-143">Puoi verificare che l'utente abbia un PIN valido usando un comando come segue:</span><span class="sxs-lookup"><span data-stu-id="a1e64-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="a1e64-144">Se Test-CsPhoneBootstrap non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="a1e64-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="a1e64-145">Quando viene incluso il parametro Verbose, Test-CsPhoneBootstrap restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1e64-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a1e64-146">Ad esempio, ecco una parte dell'output per un accesso non riuscito, una sessione in cui è stato incluso un PIN errato:</span><span class="sxs-lookup"><span data-stu-id="a1e64-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="a1e64-147">Uso di PIN auth con\\il telefono Ext: 12065551219 pin: 0712</span><span class="sxs-lookup"><span data-stu-id="a1e64-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="a1e64-148">Impossibile ottenere il ticket web</span><span class="sxs-lookup"><span data-stu-id="a1e64-148">Could not get web ticket</span></span>

<span data-ttu-id="a1e64-149">CONTROLLO</span><span class="sxs-lookup"><span data-stu-id="a1e64-149">CHECK :</span></span>

<span data-ttu-id="a1e64-150">\-L'URL del servizio Web è valido e i servizi Web sono funzionali</span><span class="sxs-lookup"><span data-stu-id="a1e64-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="a1e64-151">\-Se si usa\\PhoneNo pin per eseguire l'autenticazione, verificare che corrispondano all'URI dell'utente</span><span class="sxs-lookup"><span data-stu-id="a1e64-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="a1e64-152">\-Se si usa\\l'autenticazione Kerberos NTLM, verificare che siano state fornite credenziali valide</span><span class="sxs-lookup"><span data-stu-id="a1e64-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a1e64-153">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="a1e64-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="a1e64-154">Ecco alcuni motivi comuni per cui Test-CsPhoneBootstrap potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="a1e64-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="a1e64-155">Potrebbe essere stato specificato un indirizzo SIP non valido.</span><span class="sxs-lookup"><span data-stu-id="a1e64-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="a1e64-156">Puoi verificare che un indirizzo SIP sia corretto usando un comando come questo:</span><span class="sxs-lookup"><span data-stu-id="a1e64-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a1e64-157">Potrebbe essere stato specificato un PIN non valido.</span><span class="sxs-lookup"><span data-stu-id="a1e64-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="a1e64-158">Anche se non si riesce a recuperare il numero PIN dell'utente, è possibile verificare che l'utente abbia almeno un numero di PIN usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a1e64-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a1e64-159">Potrebbe essere stato specificato un numero di telefono non valido.</span><span class="sxs-lookup"><span data-stu-id="a1e64-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="a1e64-160">Per verificare il telefono di un utente, è possibile usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a1e64-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="a1e64-161">Il pool di registrazione non è abilitato per DHCP.</span><span class="sxs-lookup"><span data-stu-id="a1e64-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="a1e64-162">Per determinare se il pool di registrazione è abilitato per DHCP, eseguire il cmdlet Get-CsRegistrarConfiguration e controllare il valore della proprietà EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="a1e64-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="a1e64-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1e64-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

