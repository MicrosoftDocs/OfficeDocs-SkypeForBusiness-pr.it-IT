---
title: 'Lync Server 2013: testare la configurazione vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1491aa1d28de238bcadd2a024021fabf16e9128a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527903"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="9a880-102">Testare la configurazione vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a880-102">Test voice configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a880-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9a880-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a880-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="9a880-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9a880-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="9a880-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a880-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="9a880-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9a880-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a880-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a880-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="9a880-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9a880-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9a880-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9a880-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a880-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="9a880-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a880-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9a880-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a880-112">Description</span></span>

<span data-ttu-id="9a880-113">In Lync Server sono inclusi diversi cmdlet di Windows PowerShell, ad esempio Test-CsVoiceRoute e Test-CsVoicePolicy, Test-CsTrunkConfiguration, che consentono di verificare che i singoli componenti dell'infrastruttura VoIP aziendale, ovvero le route vocali, i criteri vocali e i trunk SIP, funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="9a880-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="9a880-114">Anche se è importante con VoIP aziendale che tutti i singoli pezzi funzionino: è possibile avere una route vocale valida, un criterio vocale valido e un trunk SIP valido, ma gli utenti non possono ancora effettuare o ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="9a880-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="9a880-115">Per questo motivo, Lync Server fornisce anche la possibilità di creare configurazioni di test vocale.</span><span class="sxs-lookup"><span data-stu-id="9a880-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="9a880-116">Le configurazioni di test vocale rappresentano scenari di VoIP aziendale comuni: è possibile specificare elementi quali una route vocale, un criterio vocale e un dial plan e quindi verificare che i singoli elementi siano in grado di collaborare per fornire il servizio telefonico.</span><span class="sxs-lookup"><span data-stu-id="9a880-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="9a880-117">È inoltre possibile convalidare le aspettative in un determinato scenario.</span><span class="sxs-lookup"><span data-stu-id="9a880-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="9a880-118">Si supponga, ad esempio, che si preveda che la combinazione del dial plan A e del criterio vocale B comporterà l'instradamento delle chiamate tramite la route vocale C. È possibile immettere la route vocale C come ExpectedRoute.</span><span class="sxs-lookup"><span data-stu-id="9a880-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="9a880-119">Quando si esegue il test, se la route vocale C non viene utilizzata, la verifica verrà contrassegnata come non riuscita.</span><span class="sxs-lookup"><span data-stu-id="9a880-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9a880-120">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="9a880-120">Running the test</span></span>

<span data-ttu-id="9a880-121">Prima di testare le raccolte di configurazione vocale utilizzando Windows PowerShell, è necessario utilizzare il cmdlet Get-CsVoiceTestConfiguration per recuperare un'istanza di queste impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9a880-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="9a880-122">Tale istanza deve quindi essere inviata tramite pipe al cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a880-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="9a880-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9a880-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="9a880-124">Per convalidare contemporaneamente tutte le impostazioni di configurazione del test vocale, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="9a880-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="9a880-125">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a880-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9a880-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="9a880-126">Determining success or failure</span></span>

<span data-ttu-id="9a880-127">Il cmdlet Test-CsVoiceTestConfiguration segnala se un test non è riuscito o ha avuto esito positivo e fornisce ulteriori informazioni su ogni test corretto, ad esempio la regola di conversione, la route vocale e l'utilizzo PSTN utilizzati per completare l'attività:</span><span class="sxs-lookup"><span data-stu-id="9a880-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="9a880-128">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="9a880-128">Result:             Success</span></span>

<span data-ttu-id="9a880-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="9a880-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="9a880-130">MatchingRule: Description =; Pattern = ^ ( \\ d {4} ) $; Translation = + 1 \\ d; Name = test; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="9a880-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="9a880-131">FirstMatchingRoute: sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="9a880-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="9a880-132">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="9a880-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="9a880-133">Se il test ha esito negativo, il risultato viene segnalato come non riuscito:</span><span class="sxs-lookup"><span data-stu-id="9a880-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="9a880-134">Risultato: esito negativo</span><span class="sxs-lookup"><span data-stu-id="9a880-134">Result:             Fail</span></span>

<span data-ttu-id="9a880-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="9a880-135">TranslatedNumber:</span></span>   

<span data-ttu-id="9a880-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="9a880-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="9a880-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="9a880-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9a880-138">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="9a880-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="9a880-139">Poiché la configurazione del test vocale verifica vari elementi, tra cui criteri vocali, dial plan, route vocali e così via, esistono diversi fattori che potrebbero causare un test non riuscito.</span><span class="sxs-lookup"><span data-stu-id="9a880-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="9a880-140">Se un test ha esito negativo, il primo passaggio consiste nell'esaminare le impostazioni di configurazione stesse utilizzando il cmdlet Get-CsVoiceTestConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9a880-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="9a880-141">Se le impostazioni sembrano essere configurate correttamente, rieseguire il test con il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="9a880-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="9a880-142">Il parametro Verbose fornirà un account dettagliato di ogni azione intrapresa da Test-CsVoiceTestConfiguration come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9a880-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="9a880-143">VERBOse: Loading dial plan: "globale"</span><span class="sxs-lookup"><span data-stu-id="9a880-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="9a880-144">VERBOse: caricamento del criterio vocale: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="9a880-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="9a880-145">Questo account dettagliato potrebbe fornire un indizio utile in merito alla posizione in cui il test ha effettivamente avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9a880-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="9a880-146">In caso contrario, è possibile utilizzare altri cmdlet di Windows PowerShell (come Test-CsVoicePolicy) e iniziare metodicamente a verificare i singoli componenti inclusi nelle impostazioni di configurazione del test vocale.</span><span class="sxs-lookup"><span data-stu-id="9a880-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="9a880-147">Inoltre, tenere presente che è possibile che un test sia in grado di instradare una chiamata ma che sia ancora contrassegnata come un errore. Ciò può verificarsi se si immettono valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e una qualsiasi di queste aspettative non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="9a880-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="9a880-148">Si supponga, ad esempio, di immettere la route vocale C come route vocale prevista, ma il test esegue effettivamente la chiamata tramite la route vocale D. In tal caso, la verifica verrà contrassegnata come non riuscita perché non è stata utilizzata la route vocale prevista.</span><span class="sxs-lookup"><span data-stu-id="9a880-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="9a880-149">Se un test ha esito negativo, è possibile rimuovere i valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e quindi rieseguire il test.</span><span class="sxs-lookup"><span data-stu-id="9a880-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="9a880-150">Ciò consentirà di stabilire se l'errore è dovuto al fatto che la chiamata non è stata completata o perché si prevede una cosa e ne viene effettivamente ricevuta un'altra.</span><span class="sxs-lookup"><span data-stu-id="9a880-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a880-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a880-151">See Also</span></span>


[<span data-ttu-id="9a880-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a880-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

