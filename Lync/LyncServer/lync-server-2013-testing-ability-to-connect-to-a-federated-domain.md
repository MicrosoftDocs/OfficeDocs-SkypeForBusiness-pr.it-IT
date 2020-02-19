---
title: 'Lync Server 2013: verifica della possibilità di connettersi a un dominio federato'
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
ms.openlocfilehash: 8a84e952f9c23fc95d3856b73697a049768ea179
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="9523d-102">Verifica della possibilità di connettersi a un dominio federato da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9523d-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9523d-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9523d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9523d-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="9523d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9523d-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="9523d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9523d-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="9523d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9523d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9523d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9523d-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="9523d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9523d-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9523d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9523d-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="9523d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="9523d-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9523d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9523d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9523d-112">Description</span></span>

<span data-ttu-id="9523d-113">Test-CsFederatedPartner consente di verificare la possibilità di connessione al dominio di un partner federato.</span><span class="sxs-lookup"><span data-stu-id="9523d-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="9523d-114">Per verificare la connettività a un dominio, tale dominio deve essere elencato nell'insieme dei domini consentiti (federati).</span><span class="sxs-lookup"><span data-stu-id="9523d-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="9523d-115">È possibile recuperare un elenco di domini nell'elenco dei domini consentiti utilizzando questo comando:</span><span class="sxs-lookup"><span data-stu-id="9523d-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="9523d-116">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="9523d-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9523d-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="9523d-117">Running the test</span></span>

<span data-ttu-id="9523d-118">Il cmdlet test-FederatedPartner richiede due informazioni: il nome di dominio completo del server perimetrale e il nome di dominio completo del partner federato.</span><span class="sxs-lookup"><span data-stu-id="9523d-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="9523d-119">Ad esempio, questo comando consente di testare la possibilità di connettersi al dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="9523d-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="9523d-120">Questo comando consente di testare le connessioni a tutti i domini attualmente presenti nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="9523d-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="9523d-121">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="9523d-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9523d-122">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="9523d-122">Determining success or failure</span></span>

<span data-ttu-id="9523d-123">Se il dominio specificato può essere contattato, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="9523d-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9523d-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9523d-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9523d-125">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="9523d-125">Result : Success</span></span>

<span data-ttu-id="9523d-126">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9523d-126">Latency : 00:00:00</span></span>

<span data-ttu-id="9523d-127">Errore</span><span class="sxs-lookup"><span data-stu-id="9523d-127">Error :</span></span>

<span data-ttu-id="9523d-128">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="9523d-128">Diagnosis :</span></span>

<span data-ttu-id="9523d-129">Se il dominio specificato non può essere contattato, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="9523d-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9523d-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9523d-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9523d-131">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="9523d-131">Result : Failure</span></span>

<span data-ttu-id="9523d-132">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9523d-132">Latency : 00:00:00</span></span>

<span data-ttu-id="9523d-133">Errore: 504, timeout del server</span><span class="sxs-lookup"><span data-stu-id="9523d-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="9523d-134">Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See</span><span class="sxs-lookup"><span data-stu-id="9523d-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="9523d-135">codice di risposta e frase del motivo.</span><span class="sxs-lookup"><span data-stu-id="9523d-135">response code and reason phrase.</span></span>

<span data-ttu-id="9523d-136">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="9523d-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9523d-137">Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo a causa di un errore del timeout del server.</span><span class="sxs-lookup"><span data-stu-id="9523d-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="9523d-138">Questo indica in genere i problemi di connettività di rete o i problemi che contattano il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9523d-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="9523d-139">Se Test-CsFederatedPartner ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="9523d-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9523d-140">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="9523d-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="9523d-141">Di seguito sono riportate alcune ragioni comuni per cui Test-CsFederatedPartner potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="9523d-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="9523d-142">Il server perimetrale potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="9523d-142">The Edge Server might not be available.</span></span> <span data-ttu-id="9523d-143">È possibile utilizzare questo comando per i nomi FQDN dei server perimetrali:</span><span class="sxs-lookup"><span data-stu-id="9523d-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="9523d-144">È quindi possibile eseguire il ping di ogni server perimetrale per verificare che sia possibile accedervi tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="9523d-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="9523d-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9523d-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="9523d-146">Il dominio specificato potrebbe non essere elencato nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="9523d-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="9523d-147">Per verificare i domini che sono stati aggiunti all'elenco dei domini consentiti, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="9523d-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="9523d-148">Se si desidera visualizzare un elenco di domini ai quali gli utenti sono stati bloccati dalla comunicazione, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="9523d-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

