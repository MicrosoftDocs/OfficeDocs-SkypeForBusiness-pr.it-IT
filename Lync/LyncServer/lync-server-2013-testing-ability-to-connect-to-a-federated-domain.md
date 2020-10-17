---
title: 'Lync Server 2013: verifica della possibilità di connettersi a un dominio federato'
description: 'Lync Server 2013: verifica della possibilità di connettersi a un dominio federato.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560822"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="3ad8e-103">Verifica della possibilità di connettersi a un dominio federato da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ad8e-103">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ad8e-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3ad8e-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ad8e-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="3ad8e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3ad8e-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="3ad8e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ad8e-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="3ad8e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3ad8e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ad8e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ad8e-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="3ad8e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3ad8e-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3ad8e-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="3ad8e-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3ad8e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ad8e-113">Description</span></span>

<span data-ttu-id="3ad8e-114">Test-CsFederatedPartner consente di verificare la possibilità di connessione al dominio di un partner federato.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-114">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="3ad8e-115">Per verificare la connettività a un dominio, tale dominio deve essere elencato nell'insieme dei domini consentiti (federati).</span><span class="sxs-lookup"><span data-stu-id="3ad8e-115">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="3ad8e-116">È possibile recuperare un elenco di domini nell'elenco dei domini consentiti utilizzando questo comando:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-116">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="3ad8e-117">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="3ad8e-117">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3ad8e-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="3ad8e-118">Running the test</span></span>

<span data-ttu-id="3ad8e-119">Il cmdlet Test-FederatedPartner richiede due informazioni: il nome di dominio completo del server perimetrale e il nome di dominio completo del partner federato.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-119">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="3ad8e-120">Ad esempio, questo comando consente di testare la possibilità di connettersi al dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-120">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="3ad8e-121">Questo comando consente di testare le connessioni a tutti i domini attualmente presenti nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-121">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="3ad8e-122">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="3ad8e-122">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3ad8e-123">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="3ad8e-123">Determining success or failure</span></span>

<span data-ttu-id="3ad8e-124">Se il dominio specificato può essere contattato, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="3ad8e-124">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3ad8e-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ad8e-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ad8e-126">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="3ad8e-126">Result : Success</span></span>

<span data-ttu-id="3ad8e-127">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3ad8e-127">Latency : 00:00:00</span></span>

<span data-ttu-id="3ad8e-128">Errore</span><span class="sxs-lookup"><span data-stu-id="3ad8e-128">Error :</span></span>

<span data-ttu-id="3ad8e-129">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="3ad8e-129">Diagnosis :</span></span>

<span data-ttu-id="3ad8e-130">Se il dominio specificato non può essere contattato, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-130">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3ad8e-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ad8e-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ad8e-132">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="3ad8e-132">Result : Failure</span></span>

<span data-ttu-id="3ad8e-133">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3ad8e-133">Latency : 00:00:00</span></span>

<span data-ttu-id="3ad8e-134">Errore: 504, timeout del server</span><span class="sxs-lookup"><span data-stu-id="3ad8e-134">Error : 504, Server time-out</span></span>

<span data-ttu-id="3ad8e-135">Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See</span><span class="sxs-lookup"><span data-stu-id="3ad8e-135">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="3ad8e-136">codice di risposta e frase del motivo.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-136">response code and reason phrase.</span></span>

<span data-ttu-id="3ad8e-137">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="3ad8e-137">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3ad8e-138">Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo a causa di un errore del timeout del server.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-138">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="3ad8e-139">Questo indica in genere i problemi di connettività di rete o i problemi che contattano il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-139">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="3ad8e-140">Se Test-CsFederatedPartner ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-140">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3ad8e-141">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3ad8e-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="3ad8e-142">Di seguito sono riportate alcune ragioni comuni per cui Test-CsFederatedPartner potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-142">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="3ad8e-143">Il server perimetrale potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-143">The Edge Server might not be available.</span></span> <span data-ttu-id="3ad8e-144">È possibile utilizzare questo comando per i nomi FQDN dei server perimetrali:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-144">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="3ad8e-145">È quindi possibile eseguire il ping di ogni server perimetrale per verificare che sia possibile accedervi tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-145">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="3ad8e-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-146">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="3ad8e-147">Il dominio specificato potrebbe non essere elencato nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="3ad8e-147">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="3ad8e-148">Per verificare i domini che sono stati aggiunti all'elenco dei domini consentiti, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-148">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="3ad8e-149">Se si desidera visualizzare un elenco di domini ai quali gli utenti sono stati bloccati dalla comunicazione, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3ad8e-149">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

