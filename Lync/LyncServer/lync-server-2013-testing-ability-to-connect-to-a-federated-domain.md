---
title: 'Lync Server 2013: verificare la possibilità di connettersi a un dominio federato'
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
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="91bd4-102">Verifica della possibilità di connettersi a un dominio federato da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91bd4-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91bd4-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="91bd4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91bd4-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="91bd4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="91bd4-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="91bd4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91bd4-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="91bd4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="91bd4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91bd4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91bd4-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="91bd4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="91bd4-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="91bd4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="91bd4-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="91bd4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="91bd4-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="91bd4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="91bd4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91bd4-112">Description</span></span>

<span data-ttu-id="91bd4-113">Test-CsFederatedPartner verifica la possibilità di connettersi al dominio di un partner federato.</span><span class="sxs-lookup"><span data-stu-id="91bd4-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="91bd4-114">Per verificare la connettività a un dominio, tale dominio deve essere elencato nella raccolta di domini consentiti (federati).</span><span class="sxs-lookup"><span data-stu-id="91bd4-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="91bd4-115">Puoi recuperare un elenco dei domini nell'elenco di domini consentiti usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="91bd4-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="91bd4-116">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="91bd4-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="91bd4-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="91bd4-117">Running the test</span></span>

<span data-ttu-id="91bd4-118">Il cmdlet test-FederatedPartner richiede due informazioni: il nome di dominio completo del server perimetrale e il nome di dominio completo del partner federato.</span><span class="sxs-lookup"><span data-stu-id="91bd4-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="91bd4-119">Ad esempio, questo comando verifica la possibilità di connettersi al dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="91bd4-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="91bd4-120">Questo comando consente di testare le connessioni a tutti i domini attualmente presenti nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="91bd4-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="91bd4-121">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="91bd4-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="91bd4-122">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="91bd4-122">Determining success or failure</span></span>

<span data-ttu-id="91bd4-123">Se il dominio specificato può essere contattato, si riceverà un output simile a quello con la proprietà Result contrassegnata come **Success:**</span><span class="sxs-lookup"><span data-stu-id="91bd4-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="91bd4-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91bd4-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91bd4-125">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="91bd4-125">Result : Success</span></span>

<span data-ttu-id="91bd4-126">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="91bd4-126">Latency : 00:00:00</span></span>

<span data-ttu-id="91bd4-127">Errore</span><span class="sxs-lookup"><span data-stu-id="91bd4-127">Error :</span></span>

<span data-ttu-id="91bd4-128">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="91bd4-128">Diagnosis :</span></span>

<span data-ttu-id="91bd4-129">Se il dominio specificato non può essere contattato, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="91bd4-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="91bd4-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91bd4-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91bd4-131">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="91bd4-131">Result : Failure</span></span>

<span data-ttu-id="91bd4-132">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="91bd4-132">Latency : 00:00:00</span></span>

<span data-ttu-id="91bd4-133">Errore: 504, timeout del server</span><span class="sxs-lookup"><span data-stu-id="91bd4-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="91bd4-134">Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See</span><span class="sxs-lookup"><span data-stu-id="91bd4-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="91bd4-135">codice di risposta e frase motivo.</span><span class="sxs-lookup"><span data-stu-id="91bd4-135">response code and reason phrase.</span></span>

<span data-ttu-id="91bd4-136">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="91bd4-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="91bd4-137">Ad esempio, l'output precedente indica che il test non è riuscito a causa di un errore di timeout del server.</span><span class="sxs-lookup"><span data-stu-id="91bd4-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="91bd4-138">Questo indica in genere i problemi di connettività di rete o i problemi di contatto con il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="91bd4-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="91bd4-139">Se Test-CsFederatedPartner non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="91bd4-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="91bd4-140">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="91bd4-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="91bd4-141">Ecco alcuni motivi comuni per cui Test-CsFederatedPartner potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="91bd4-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="91bd4-142">Il server perimetrale potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="91bd4-142">The Edge Server might not be available.</span></span> <span data-ttu-id="91bd4-143">Puoi usare questo comando per gli FQDN degli Edge Server:</span><span class="sxs-lookup"><span data-stu-id="91bd4-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="91bd4-144">È quindi possibile eseguire il ping di ogni Edge Server per verificare che sia possibile accedervi tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="91bd4-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="91bd4-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91bd4-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="91bd4-146">Il dominio specificato potrebbe non essere elencato nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="91bd4-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="91bd4-147">Per verificare i domini aggiunti all'elenco dei domini consentiti, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="91bd4-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="91bd4-148">Se si vuole visualizzare un elenco dei domini a cui gli utenti sono stati bloccati dalla comunicazione, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="91bd4-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

