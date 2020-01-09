---
title: 'Lync Server 2013: testare le notifiche push in Smart Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="d4aa5-102">Testare le notifiche push agli smartphone in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4aa5-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4aa5-103">_**Argomento Ultima modifica:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="d4aa5-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4aa5-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="d4aa5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d4aa5-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="d4aa5-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4aa5-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="d4aa5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d4aa5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4aa5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4aa5-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="d4aa5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d4aa5-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d4aa5-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="d4aa5-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d4aa5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4aa5-112">Description</span></span>

<span data-ttu-id="d4aa5-113">Il servizio di notifica push (servizio notifica push Apple e servizio notifica push Microsoft) può inviare notifiche su eventi come nuovi messaggi istantanei o un nuovo messaggio vocale a dispositivi mobili come iPhone e telefoni Windows, anche se il client Lync in questi dispositivi è attualmente sospesa o in corso in background.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="d4aa5-114">Il servizio di notifica push è un servizio basato su cloud in uso nei server Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="d4aa5-115">Per sfruttare le notifiche push, è necessario essere in grado di connettersi e di essere autenticati tramite la finestra di compensazione delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="d4aa5-116">Il cmdlet Test-CsMcxPushNotification consente agli amministratori di verificare che le richieste di notifica push possano essere instradate tramite il server perimetrale alla compensazione delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d4aa5-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="d4aa5-117">Running the test</span></span>

<span data-ttu-id="d4aa5-118">Per testare il servizio di notifica push, chiama il cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="d4aa5-119">Verificare di aver specificato il nome di dominio completo del server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="d4aa5-120">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="d4aa5-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d4aa5-121">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="d4aa5-121">Determining success or failure</span></span>

<span data-ttu-id="d4aa5-122">Se Test-CsMcxPushNotification ha esito positivo il cmdlet restituirà il risultato del test:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="d4aa5-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4aa5-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d4aa5-124">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="d4aa5-124">Result : Success</span></span>

<span data-ttu-id="d4aa5-125">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d4aa5-125">Latency : 00:00:00</span></span>

<span data-ttu-id="d4aa5-126">Errore</span><span class="sxs-lookup"><span data-stu-id="d4aa5-126">Error :</span></span>

<span data-ttu-id="d4aa5-127">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="d4aa5-127">Diagnosis :</span></span>

<span data-ttu-id="d4aa5-128">Se Test-CsMcxPushNotification non è in grado di connettersi alla barra di notifica push, il cmdlet non restituirà in genere un risultato di verifica dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="d4aa5-129">Al contrario, il comando fallirà in genere completamente.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="d4aa5-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-130">For example:</span></span>

<span data-ttu-id="d4aa5-131">Test-CsMcxPushNotification: una risposta di 504 (timeout del server) è stata ricevuta dalla rete e l'operazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="d4aa5-132">Per altre informazioni, vedere i dettagli sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-132">See the exception details for more information.</span></span>

<span data-ttu-id="d4aa5-133">At line: 1 carattere: 27</span><span class="sxs-lookup"><span data-stu-id="d4aa5-133">At line:1 char:27</span></span>

<span data-ttu-id="d4aa5-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="d4aa5-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="d4aa5-135">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="d4aa5-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="d4aa5-136">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. Rtc. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="d4aa5-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d4aa5-137">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="d4aa5-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="d4aa5-138">Se il servizio di notifica push non riesce che in genere indica i problemi di comunicazione con il server perimetrale o i problemi di comunicazione con la camera di compensazione delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="d4aa5-139">Se si verificano problemi durante l'esecuzione di Test-CsMcxPushNotification, la prima operazione da eseguire è verificare che il server perimetrale funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="d4aa5-140">Un modo per eseguire questa operazione consiste nell'usare il cmdlet test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d4aa5-141">Questo controllo verifica che un utente specificato possa connettersi al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="d4aa5-142">Se il server perimetrale sembra funzionare correttamente, significa spesso che non si riesce a connettersi alla finestra di compensazione delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="d4aa5-143">A sua volta, ciò significa in genere che l'URI di compensazione non è stato configurato correttamente o che non si ha un record SRV DNS che punta a questo URL.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="d4aa5-144">Puoi verificare che l'URI sia impostato sul valore corretto (sip:push@push.lync.com) eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="d4aa5-145">Se la proprietà PushNotificationProxyUri è impostata su un valore diverso da sip:push@push.lync.com, è possibile risolvere il problema usando il cmdlet Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="d4aa5-146">Questo comando, ad esempio, imposta correttamente l'URI nell'intera organizzazione:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="d4aa5-147">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="d4aa5-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="d4aa5-148">Se l'URI è configurato correttamente, il passaggio successivo deve essere verificare di avere un record SRV DNS che venga risolto nel dominio SIP e nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="d4aa5-149">Per altre informazioni su come configurare questi record, vedere l'argomento della Guida requisiti DNS per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="d4aa5-150">Tieni presente che il messaggio di errore seguente indica in genere un problema con i record DNS:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="d4aa5-151">Una risposta di 504 (timeout del server) è stata ricevuta dalla rete e l'operazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="d4aa5-152">Per altre informazioni, vedere i dettagli sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-152">See the exception details for more information.</span></span>

<span data-ttu-id="d4aa5-153">È anche possibile che test-CsMcxConfiguration non riesca con questo messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="d4aa5-154">Test-CsMcxPushNotification: la richiesta di notifica push è stata rifiutata.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="d4aa5-155">At line: 1 carattere: 27</span><span class="sxs-lookup"><span data-stu-id="d4aa5-155">At line:1 char:27</span></span>

<span data-ttu-id="d4aa5-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="d4aa5-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="d4aa5-157">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="d4aa5-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="d4aa5-158">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. Rtc. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="d4aa5-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="d4aa5-159">Il messaggio "richiesta di notifica push è stato rifiutato" in genere si verifica se è stato abilitato il filtro URL e si bloccano i prefissi http: e https:.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="d4aa5-160">Puoi determinare quali prefissi vengono bloccati usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="d4aa5-161">Se http: o https: vengono visualizzati nei risultati, è necessario rimuoverli dall'elenco di prefissi bloccati per il lavoro delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="d4aa5-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="d4aa5-162">Questa operazione può essere eseguita usando comandi simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4aa5-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="d4aa5-163">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d4aa5-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

