---
title: 'Lync Server 2013: verificare la configurazione vocale'
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
ms.openlocfilehash: 9532327640be12351143632813d403edddf5c437
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="46cb8-102">Verificare la configurazione vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46cb8-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46cb8-103">_**Argomento Ultima modifica:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="46cb8-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46cb8-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="46cb8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="46cb8-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="46cb8-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46cb8-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="46cb8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="46cb8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46cb8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46cb8-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="46cb8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="46cb8-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="46cb8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="46cb8-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="46cb8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="46cb8-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="46cb8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="46cb8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46cb8-112">Description</span></span>

<span data-ttu-id="46cb8-113">Lync Server include diversi cmdlet di Windows PowerShell, ad esempio Test-CsVoiceRoute e Test-CsVoicePolicy, Test-CsTrunkConfiguration, che consentono di verificare che i singoli elementi dell'infrastruttura vocale aziendale, ovvero le route vocali, la voce i criteri, trunk SIP, funzionano come previsto.</span><span class="sxs-lookup"><span data-stu-id="46cb8-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="46cb8-114">Mentre è importante con Enterprise Voice che tutti i singoli pezzi funzionano: è possibile avere una route vocale valida, un criterio vocale valido e un trunk SIP valido, ma gli utenti non possono ancora effettuare o ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="46cb8-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="46cb8-115">Per questo motivo, Lync Server offre anche la possibilità di creare configurazioni di test vocali.</span><span class="sxs-lookup"><span data-stu-id="46cb8-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="46cb8-116">Le configurazioni di test vocale rappresentano scenari comuni per le voci aziendali: è possibile specificare elementi come una route vocale, un criterio vocale e un dial plan, quindi verificare che questi singole voci funzionino in modo da collaborare per ottenere un servizio telefonico.</span><span class="sxs-lookup"><span data-stu-id="46cb8-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="46cb8-117">Inoltre, puoi convalidare le tue aspettative in uno scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="46cb8-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="46cb8-118">Supponiamo ad esempio che si preveda che la combinazione di dial plan A e Policy vocale B comporterebbe la routing delle chiamate tramite la route vocale C. È possibile immettere la route vocale C come ExpectedRoute.</span><span class="sxs-lookup"><span data-stu-id="46cb8-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="46cb8-119">Quando si esegue il test, se la route vocale C non viene usata, il test verrà contrassegnato come non riuscito.</span><span class="sxs-lookup"><span data-stu-id="46cb8-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="46cb8-120">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="46cb8-120">Running the test</span></span>

<span data-ttu-id="46cb8-121">Prima di testare le raccolte di configurazione vocale tramite Windows PowerShell, devi prima usare il cmdlet Get-CsVoiceTestConfiguration per recuperare un'istanza di queste impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="46cb8-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="46cb8-122">Questa istanza deve quindi essere inviata tramite pipe al Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="46cb8-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="46cb8-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="46cb8-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="46cb8-124">Per convalidare tutte le impostazioni di configurazione del test vocale contemporaneamente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="46cb8-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="46cb8-125">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="46cb8-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="46cb8-126">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="46cb8-126">Determining success or failure</span></span>

<span data-ttu-id="46cb8-127">Il cmdlet Test-CsVoiceTestConfiguration segnala se un test non è riuscito o è riuscito e fornisce informazioni aggiuntive su ogni test riuscito, ad esempio la regola di traduzione, la route vocale e l'utilizzo PSTN usato per completare l'attività:</span><span class="sxs-lookup"><span data-stu-id="46cb8-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="46cb8-128">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="46cb8-128">Result:             Success</span></span>

<span data-ttu-id="46cb8-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="46cb8-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="46cb8-130">MatchingRule: Description =; Pattern = ^ (\\d{4}) $; Traduzione = + 1\\d; Name = test; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="46cb8-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="46cb8-131">FirstMatchingRoute: sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="46cb8-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="46cb8-132">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="46cb8-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="46cb8-133">Se il test ha esito negativo, il risultato viene segnalato come non riuscito:</span><span class="sxs-lookup"><span data-stu-id="46cb8-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="46cb8-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="46cb8-134">Result:             Fail</span></span>

<span data-ttu-id="46cb8-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="46cb8-135">TranslatedNumber:</span></span>   

<span data-ttu-id="46cb8-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="46cb8-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="46cb8-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="46cb8-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="46cb8-138">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="46cb8-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="46cb8-139">Dato che i test della configurazione del test vocale provano diversi elementi, tra cui i criteri vocali, i dial plan, le route vocali e così via, esistono diversi fattori che potrebbero causare un test non riuscito.</span><span class="sxs-lookup"><span data-stu-id="46cb8-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="46cb8-140">Se un test ha esito negativo, il primo passaggio deve essere rivedere le impostazioni di configurazione tramite il cmdlet Get-CsVoiceTestConfiguration:</span><span class="sxs-lookup"><span data-stu-id="46cb8-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="46cb8-141">Se le impostazioni sembrano essere configurate correttamente, ripetere l'esecuzione del test, includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="46cb8-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="46cb8-142">Il parametro Verbose fornirà un account dettagliato di ogni azione eseguita da Test-CsVoiceTestConfiguration, come illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="46cb8-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="46cb8-143">VERBOse: caricamento di dial plan: "globale"</span><span class="sxs-lookup"><span data-stu-id="46cb8-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="46cb8-144">VERBOse: caricamento dei criteri vocali: "" RedmondDialPlan ""</span><span class="sxs-lookup"><span data-stu-id="46cb8-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="46cb8-145">Questo account dettagliato potrebbe dare un indizio utile in merito alla posizione in cui il test non è effettivamente riuscito.</span><span class="sxs-lookup"><span data-stu-id="46cb8-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="46cb8-146">In caso contrario, puoi quindi usare altri cmdlet di Windows PowerShell (ad esempio Test-CsVoicePolicy) e iniziare metodicamente a verificare i singoli componenti inclusi nelle impostazioni di configurazione del test vocale.</span><span class="sxs-lookup"><span data-stu-id="46cb8-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="46cb8-147">Oltre a ciò, tieni presente che è possibile che un test sia in grado di instradare una chiamata e che sia ancora contrassegnata come un errore. Ciò può verificarsi se si immettono valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e tutte le attese non vengono soddisfatte.</span><span class="sxs-lookup"><span data-stu-id="46cb8-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="46cb8-148">Ad esempio, supponiamo che tu immetti la route vocale C come itinerario vocale previsto, ma il test completa effettivamente la chiamata usando la route vocale D. In questo caso, il test verrà contrassegnato come non riuscito perché non è stata usata la route vocale prevista.</span><span class="sxs-lookup"><span data-stu-id="46cb8-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="46cb8-149">Se un test non riesce, è possibile rimuovere i valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e quindi eseguire di nuovo il test.</span><span class="sxs-lookup"><span data-stu-id="46cb8-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="46cb8-150">Questo ti aiuterà a determinare se l'errore è stato perché la chiamata non è stata completata o perché ti aspetti una cosa e ne hai ricevuto un altro.</span><span class="sxs-lookup"><span data-stu-id="46cb8-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46cb8-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46cb8-151">See Also</span></span>


[<span data-ttu-id="46cb8-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="46cb8-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

