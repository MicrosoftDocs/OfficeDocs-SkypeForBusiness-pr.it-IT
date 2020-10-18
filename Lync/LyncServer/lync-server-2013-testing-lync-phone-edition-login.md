---
title: "Lync Server 2013: test dell'account di accesso di Lync Phone Edition"
description: "Lync Server 2013: test dell'account di accesso di Lync Phone Edition."
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
ms.openlocfilehash: d21d65676c4f5e0f867c7d9556cdea50419be69b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575242"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="ab47b-103">Test dell'account di accesso di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab47b-103">Testing Lync Phone Edition login in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab47b-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ab47b-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab47b-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ab47b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ab47b-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="ab47b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab47b-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="ab47b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ab47b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab47b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab47b-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ab47b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ab47b-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab47b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ab47b-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="ab47b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="ab47b-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ab47b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ab47b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab47b-113">Description</span></span>

<span data-ttu-id="ab47b-114">Il cmdlet Test-CsPhoneBootstrap consente agli amministratori di verificare che un determinato utente, utilizzando il numero di telefono e il PIN assegnato a lui, sia in grado di accedere al sistema da un dispositivo compatibile con Lync 2013 Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ab47b-114">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="ab47b-115">(Nessun dispositivo è effettivamente necessario per eseguire il test).</span><span class="sxs-lookup"><span data-stu-id="ab47b-115">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="ab47b-116">Per consentire al cmdlet Test-CsPhoneBootstrap di effettuare il controllo, il pool di registrazione che ospita l'account utente su cui viene eseguito il test deve risultare individuabile mediante protocollo DHCP.</span><span class="sxs-lookup"><span data-stu-id="ab47b-116">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="ab47b-117">Per determinare se un servizio di registrazione è individuabile in questo modo, utilizzare il cmdlet Get-CsRegistrarConfiguration e controllare il valore della proprietà EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="ab47b-117">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="ab47b-118">Se questa proprietà è impostata su false, è necessario utilizzare Set-CsRegistrarConfiguration per impostare il valore della proprietà su true e rendere individuabile il registrar tramite DHCP.</span><span class="sxs-lookup"><span data-stu-id="ab47b-118">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="ab47b-119">È possibile eseguire questa operazione anche utilizzando il server DHCP aziendale e la configurazione delle opzioni specifiche di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab47b-119">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ab47b-120">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="ab47b-120">Running the test</span></span>

<span data-ttu-id="ab47b-121">Per eseguire il cmdlet Test-CsPhoneBootstrap, è necessario fornire almeno il numero di telefono e il PIN (Personal Identification Number) client per un utente di Lync Server valido.</span><span class="sxs-lookup"><span data-stu-id="ab47b-121">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="ab47b-122">Ad esempio, questo comando verifica la capacità di accesso per l'utente che ha il numero di telefono 12065551219 e il PIN 0712:</span><span class="sxs-lookup"><span data-stu-id="ab47b-122">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="ab47b-123">Per un controllo più esaustivo, è possibile includere anche l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ab47b-123">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="ab47b-124">In tal caso, il numero di telefono, il PIN client e l'indirizzo SIP devono essere tutti validi affinché il test venga eseguito correttamente:</span><span class="sxs-lookup"><span data-stu-id="ab47b-124">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="ab47b-125">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="ab47b-125">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ab47b-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ab47b-126">Determining success or failure</span></span>

<span data-ttu-id="ab47b-127">Se l'utente specificato è in grado di connettersi a Lync Server, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="ab47b-127">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ab47b-128">TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="ab47b-128">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="ab47b-129">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="ab47b-129">CertProvisioningService.svc</span></span>

<span data-ttu-id="ab47b-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ab47b-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ab47b-131">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="ab47b-131">Result : Success</span></span>

<span data-ttu-id="ab47b-132">Latenza: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="ab47b-132">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="ab47b-133">Errore</span><span class="sxs-lookup"><span data-stu-id="ab47b-133">Error :</span></span>

<span data-ttu-id="ab47b-134">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ab47b-134">Diagnosis :</span></span>

<span data-ttu-id="ab47b-135">Se l'utente specificato non è in grado di effettuare una connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="ab47b-135">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ab47b-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ab47b-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ab47b-137">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="ab47b-137">Result : Failure</span></span>

<span data-ttu-id="ab47b-138">Latenza: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="ab47b-138">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="ab47b-139">Error: ERROR-No Response Received for Web-Ticket Service.</span><span class="sxs-lookup"><span data-stu-id="ab47b-139">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="ab47b-140">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ab47b-140">Diagnosis :</span></span>

<span data-ttu-id="ab47b-141">L'output precedente dichiara che il test non ha avuto esito positivo perché il servizio ticket web non ha risposto.</span><span class="sxs-lookup"><span data-stu-id="ab47b-141">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="ab47b-142">Questo potrebbe essere dovuto a un problema con il servizio stesso oppure potrebbe essere dovuto a un indirizzo SIP, a un numero di telefono o a un PIN client passato a Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="ab47b-142">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="ab47b-143">È possibile verificare l'indirizzo SIP e il numero di telefono dell'utente utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ab47b-143">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="ab47b-144">È possibile verificare che l'utente disponga di un PIN valido utilizzando un comando come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ab47b-144">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="ab47b-145">Se Test-CsPhoneBootstrap ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="ab47b-145">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="ab47b-146">Quando viene incluso il parametro Verbose, Test-CsPhoneBootstrap restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab47b-146">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ab47b-147">Ad esempio, di seguito viene fornita una parte dell'output per un accesso non riuscito, una sessione in cui è stato incluso un PIN errato:</span><span class="sxs-lookup"><span data-stu-id="ab47b-147">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="ab47b-148">Utilizzo dell'autenticazione PIN con il telefono \\ ext: 12065551219 pin: 0712</span><span class="sxs-lookup"><span data-stu-id="ab47b-148">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="ab47b-149">Impossibile ottenere il ticket web</span><span class="sxs-lookup"><span data-stu-id="ab47b-149">Could not get web ticket</span></span>

<span data-ttu-id="ab47b-150">CONTROLLO</span><span class="sxs-lookup"><span data-stu-id="ab47b-150">CHECK :</span></span>

<span data-ttu-id="ab47b-151">\- L'URL del servizio Web è valido e i servizi Web sono funzionali</span><span class="sxs-lookup"><span data-stu-id="ab47b-151">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="ab47b-152">\- Se si utilizza \\ il pin di PhoneNo per eseguire l'autenticazione, assicurarsi che corrispondano all'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ab47b-152">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="ab47b-153">\- Se si utilizza l' \\ autenticazione Kerberos NTLM, accertarsi di aver specificato le credenziali valide</span><span class="sxs-lookup"><span data-stu-id="ab47b-153">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ab47b-154">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="ab47b-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="ab47b-155">Di seguito sono riportate alcune ragioni comuni per cui Test-CsPhoneBootstrap potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ab47b-155">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="ab47b-156">Potrebbe essere stato specificato un indirizzo SIP non valido.</span><span class="sxs-lookup"><span data-stu-id="ab47b-156">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="ab47b-157">È possibile verificare che un indirizzo SIP sia corretto utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ab47b-157">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ab47b-158">Potrebbe essere stato specificato un PIN non valido.</span><span class="sxs-lookup"><span data-stu-id="ab47b-158">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="ab47b-159">Anche se non è possibile recuperare il numero di PIN dell'utente, è possibile verificare che l'utente disponga almeno di un numero di PIN utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ab47b-159">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ab47b-160">Potrebbe essere stato specificato un numero di telefono non valido.</span><span class="sxs-lookup"><span data-stu-id="ab47b-160">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="ab47b-161">È possibile verificare il numero di telefono di un utente utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ab47b-161">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="ab47b-162">Il pool di registrazione non è abilitato per il protocollo DHCP.</span><span class="sxs-lookup"><span data-stu-id="ab47b-162">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="ab47b-163">Per determinare se il pool di registrazione è abilitato per DHCP, eseguire il cmdlet Get-CsRegistrarConfiguration e controllare il valore della proprietà EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="ab47b-163">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="ab47b-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ab47b-164">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

