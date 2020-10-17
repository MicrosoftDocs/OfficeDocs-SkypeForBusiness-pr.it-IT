---
title: 'Lync Server 2013: testing di Exchange alle notifiche di Lync'
description: 'Lync Server 2013: testing di Exchange alle notifiche di Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf453bfdaab7e7b6bdaae8b67ac7759c0d55af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560622"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="55b46-103">Test di Exchange alle notifiche di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55b46-103">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55b46-104">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="55b46-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55b46-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="55b46-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="55b46-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="55b46-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55b46-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="55b46-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="55b46-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55b46-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55b46-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="55b46-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="55b46-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="55b46-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="55b46-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="55b46-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="55b46-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="55b46-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="55b46-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55b46-113">Description</span></span>

<span data-ttu-id="55b46-114">Il cmdlet **test-CsExStorageNotification** viene utilizzato per verificare che il servizio di notifica di Microsoft Exchange Server 2013 possa informare Lync Server 2013 ogni volta che vengono apportate modifiche all'elenco contatti di un utente.</span><span class="sxs-lookup"><span data-stu-id="55b46-114">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="55b46-115">Questo cmdlet è valido solo se si utilizza l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="55b46-115">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="55b46-116">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="55b46-116">Running the test</span></span>

<span data-ttu-id="55b46-117">Il comando riportato nell'esempio 1 consente di verificare se il servizio di archiviazione di Lync Server può connettersi al servizio di notifica delle cassette postali di Microsoft Exchange Server per l'utente sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="55b46-117">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="55b46-118">In questo esempio viene utilizzato NetNamedPipe come binding WCF.</span><span class="sxs-lookup"><span data-stu-id="55b46-118">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="55b46-119">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="55b46-119">Determining success or failure</span></span>

<span data-ttu-id="55b46-120">Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="55b46-120">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="55b46-121">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55b46-121">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="55b46-122">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="55b46-122">Result : Success</span></span>

<span data-ttu-id="55b46-123">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55b46-123">Latency : 00:00:00</span></span>

<span data-ttu-id="55b46-124">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="55b46-124">Error Message :</span></span>

<span data-ttu-id="55b46-125">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="55b46-125">Diagnosis :</span></span>

<span data-ttu-id="55b46-126">Se l'utente specificato non è in grado di ricevere notifiche, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="55b46-126">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="55b46-127">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55b46-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="55b46-128">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="55b46-128">Result : Failure</span></span>

<span data-ttu-id="55b46-129">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55b46-129">Latency : 00:00:00</span></span>

<span data-ttu-id="55b46-130">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="55b46-130">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="55b46-131">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="55b46-131">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="55b46-132">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="55b46-132">established connection failed because connected host has</span></span>

<span data-ttu-id="55b46-133">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="55b46-133">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="55b46-134">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="55b46-134">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="55b46-135">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="55b46-135">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="55b46-136">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="55b46-136">time, or established connection failed because connected host</span></span>

<span data-ttu-id="55b46-137">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="55b46-137">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="55b46-138">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="55b46-138">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="55b46-139">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="55b46-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="55b46-140">Di seguito sono riportate alcune ragioni comuni per cui **test-CsExStorageNotification** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="55b46-140">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="55b46-141">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="55b46-141">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="55b46-142">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="55b46-142">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="55b46-143">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="55b46-143">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="55b46-144">Questo comando avrà esito negativo se il server di Microsoft Exchange non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="55b46-144">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55b46-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55b46-145">See Also</span></span>


[<span data-ttu-id="55b46-146">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="55b46-146">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

