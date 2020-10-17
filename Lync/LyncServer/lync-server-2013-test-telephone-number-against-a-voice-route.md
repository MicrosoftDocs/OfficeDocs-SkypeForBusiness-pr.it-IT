---
title: 'Lync Server 2013: testare il numero di telefono in una route vocale'
description: 'Lync Server 2013: testare il numero di telefono in una route vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563392"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="f0dcd-103">Testare il numero di telefono in una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0dcd-103">Test telephone number against a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0dcd-104">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="f0dcd-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0dcd-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="f0dcd-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f0dcd-106">Mensile</span><span class="sxs-lookup"><span data-stu-id="f0dcd-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0dcd-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="f0dcd-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f0dcd-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0dcd-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0dcd-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="f0dcd-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f0dcd-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f0dcd-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="f0dcd-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f0dcd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0dcd-113">Description</span></span>

<span data-ttu-id="f0dcd-114">Le route vocali interagiscono con i criteri vocali per instradare le chiamate vocali aziendali alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-114">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="f0dcd-115">Ogni route vocale include un'espressione regolare (uno schema numerico) che identifica i numeri di telefono che verranno instradati tramite una determinata route vocale: la route sarà in grado di gestire i numeri di telefono che corrispondono a questa espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-115">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="f0dcd-116">Ad esempio, una route vocale può avere un'espressione regolare che consente di gestire qualsiasi numero di 10 cifre.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-116">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="f0dcd-117">Questo significa che la route sarebbe in grado di gestire un numero di telefono come questo:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-117">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="f0dcd-118">2065551219</span><span class="sxs-lookup"><span data-stu-id="f0dcd-118">2065551219</span></span>

<span data-ttu-id="f0dcd-119">La route non è in grado di gestire uno dei due numeri seguenti, nessuno dei quali ha 10 cifre:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-119">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="f0dcd-120">5551219</span><span class="sxs-lookup"><span data-stu-id="f0dcd-120">5551219</span></span>

  - <span data-ttu-id="f0dcd-121">12065551219</span><span class="sxs-lookup"><span data-stu-id="f0dcd-121">12065551219</span></span>

<span data-ttu-id="f0dcd-122">Il cmdlet Test-CsVoiceRoute verifica se una determinata route vocale può instradare un numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-122">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f0dcd-123">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="f0dcd-123">Running the test</span></span>

<span data-ttu-id="f0dcd-124">La verifica dell'abilità di una route vocale per instradare un numero di telefono specificato è un processo in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-124">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="f0dcd-125">Per prima cosa, è necessario utilizzare il cmdlet Get-CsVoiceRoute per restituire un'istanza di tale route vocale e quindi è necessario utilizzare il cmdlet Test-CsVoiceRoute per verificare la capacità di tale route di gestire il numero di telefono di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-125">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="f0dcd-126">Ad esempio, questo comando consente di verificare se la route vocale di RedmondVoiceRoute può instradare il numero di telefono 2065551219:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-126">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="f0dcd-127">Si noti che il numero di telefono deve essere digitato come previsto per gli utenti di comporre il numero.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-127">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="f0dcd-128">Ad esempio, se non si prevede che gli utenti includano il codice paese e il prefisso di area durante la composizione, utilizzare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-128">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="f0dcd-129">In questo caso, il numero di destinazione lascia fuori sia il prefisso nazionale che il prefisso.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-129">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="f0dcd-130">Per utilizzare un singolo comando per testare tutte le route vocali in base a un numero di destinazione specificato, utilizzare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-130">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="f0dcd-131">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-131">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f0dcd-132">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="f0dcd-132">Determining success or failure</span></span>

<span data-ttu-id="f0dcd-133">Se la route vocale è in grado di instradare il numero di telefono di destinazione, il cmdlet Test-CsVoiceRoute restituisce solo il valore true:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-133">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="f0dcd-134">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="f0dcd-134">MatchesPattern</span></span>

\--------------

<span data-ttu-id="f0dcd-135">Vero</span><span class="sxs-lookup"><span data-stu-id="f0dcd-135">True</span></span>

<span data-ttu-id="f0dcd-136">Questo significa che la route può gestire numeri simili al numero di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-136">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="f0dcd-137">Se la route vocale non è in grado di gestire il numero di destinazione, Test-CsVoiceRoute restituirà il valore false:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-137">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="f0dcd-138">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="f0dcd-138">MatchesPattern</span></span>

\--------------

<span data-ttu-id="f0dcd-139">False</span><span class="sxs-lookup"><span data-stu-id="f0dcd-139">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f0dcd-140">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="f0dcd-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="f0dcd-141">Quando si testano le route vocali, "Failure" è un termine relativo.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-141">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="f0dcd-142">In questo caso, non significa che la route è in qualche modo "interrotta;" invece, significa solo che la route non è in grado di gestire il numero di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-142">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="f0dcd-143">Questo potrebbe essere dovuto al fatto che la route vocale non è stata configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-143">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="f0dcd-144">Potrebbe anche significare che la route non è mai stata progettata per gestire i numeri usando questo modello.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-144">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="f0dcd-145">Ad esempio, se non si desidera eseguire il routing delle chiamate ad altri paesi su una determinata route, è possibile che route sia configurata in modo da rifiutare tutti i numeri di telefono che includono un codice paese.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-145">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="f0dcd-146">Se Test-CsVoiceRoute restituisce false quando si prevede che restituisca true, verificare di aver digitato correttamente il numero di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f0dcd-146">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="f0dcd-147">In questo caso, utilizzare un comando simile al seguente per visualizzare la NumberPattern configurata per la route:</span><span class="sxs-lookup"><span data-stu-id="f0dcd-147">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0dcd-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0dcd-148">See Also</span></span>


[<span data-ttu-id="f0dcd-149">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="f0dcd-149">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

