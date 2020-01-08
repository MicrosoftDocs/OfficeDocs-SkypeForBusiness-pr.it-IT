---
title: 'Lync Server 2013: testing di Exchange alle notifiche di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="6ede0-102">Test delle notifiche di Exchange a Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ede0-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ede0-103">_**Argomento Ultima modifica:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="6ede0-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ede0-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="6ede0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6ede0-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="6ede0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ede0-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="6ede0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6ede0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ede0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ede0-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="6ede0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6ede0-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6ede0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6ede0-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="6ede0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="6ede0-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ede0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6ede0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ede0-112">Description</span></span>

<span data-ttu-id="6ede0-113">Il cmdlet **test-CsExStorageNotification** viene usato per verificare che il servizio di notifica di Microsoft Exchange Server 2013 sia in grado di inviare notifiche a Lync Server 2013 in qualsiasi momento vengano apportati aggiornamenti all'elenco contatti di un utente.</span><span class="sxs-lookup"><span data-stu-id="6ede0-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="6ede0-114">Questo cmdlet è valido solo se si usa l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="6ede0-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6ede0-115">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="6ede0-115">Running the test</span></span>

<span data-ttu-id="6ede0-116">Il comando illustrato nell'esempio 1 consente di verificare se il servizio di archiviazione di Lync Server può connettersi al servizio di notifica delle cassette postali di Microsoft Exchange Server per l'utente sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6ede0-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="6ede0-117">In questo esempio, NetNamedPipe viene usato come binding WCF.</span><span class="sxs-lookup"><span data-stu-id="6ede0-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6ede0-118">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="6ede0-118">Determining success or failure</span></span>

<span data-ttu-id="6ede0-119">Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita**:</span><span class="sxs-lookup"><span data-stu-id="6ede0-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="6ede0-120">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6ede0-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6ede0-121">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="6ede0-121">Result : Success</span></span>

<span data-ttu-id="6ede0-122">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6ede0-122">Latency : 00:00:00</span></span>

<span data-ttu-id="6ede0-123">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="6ede0-123">Error Message :</span></span>

<span data-ttu-id="6ede0-124">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="6ede0-124">Diagnosis :</span></span>

<span data-ttu-id="6ede0-125">Se l'utente specificato non può ricevere notifiche, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="6ede0-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6ede0-126">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6ede0-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6ede0-127">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="6ede0-127">Result : Failure</span></span>

<span data-ttu-id="6ede0-128">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6ede0-128">Latency : 00:00:00</span></span>

<span data-ttu-id="6ede0-129">Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa</span><span class="sxs-lookup"><span data-stu-id="6ede0-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="6ede0-130">non ha risposto correttamente dopo un periodo di tempo o</span><span class="sxs-lookup"><span data-stu-id="6ede0-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="6ede0-131">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="6ede0-131">established connection failed because connected host has</span></span>

<span data-ttu-id="6ede0-132">Impossibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="6ede0-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="6ede0-133">Eccezione interna: tentativo di connessione non riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="6ede0-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="6ede0-134">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="6ede0-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="6ede0-135">l'ora o la connessione stabilita non è riuscita perché l'host connesso</span><span class="sxs-lookup"><span data-stu-id="6ede0-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="6ede0-136">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="6ede0-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="6ede0-137">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="6ede0-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6ede0-138">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="6ede0-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="6ede0-139">Ecco alcuni motivi comuni per cui **test-CsExStorageNotification** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="6ede0-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="6ede0-140">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="6ede0-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="6ede0-141">Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6ede0-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="6ede0-142">Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="6ede0-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="6ede0-143">Questo comando non riuscirà se il server di Microsoft Exchange non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="6ede0-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ede0-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ede0-144">See Also</span></span>


[<span data-ttu-id="6ede0-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="6ede0-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

