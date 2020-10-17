---
title: 'Lync Server 2013: testare il numero di telefono in una route vocale'
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
ms.openlocfilehash: 1e2db63b7f8c4d801c7e2e89da93593a5745c9c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519123"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="b1d48-102">Testare il numero di telefono in una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d48-102">Test telephone number against a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1d48-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b1d48-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1d48-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="b1d48-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b1d48-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="b1d48-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1d48-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="b1d48-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b1d48-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1d48-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1d48-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="b1d48-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b1d48-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b1d48-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b1d48-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="b1d48-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="b1d48-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b1d48-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b1d48-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1d48-112">Description</span></span>

<span data-ttu-id="b1d48-113">Le route vocali interagiscono con i criteri vocali per instradare le chiamate vocali aziendali alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="b1d48-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="b1d48-114">Ogni route vocale include un'espressione regolare (uno schema numerico) che identifica i numeri di telefono che verranno instradati tramite una determinata route vocale: la route sarà in grado di gestire i numeri di telefono che corrispondono a questa espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="b1d48-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="b1d48-115">Ad esempio, una route vocale può avere un'espressione regolare che consente di gestire qualsiasi numero di 10 cifre.</span><span class="sxs-lookup"><span data-stu-id="b1d48-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="b1d48-116">Questo significa che la route sarebbe in grado di gestire un numero di telefono come questo:</span><span class="sxs-lookup"><span data-stu-id="b1d48-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="b1d48-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="b1d48-117">2065551219</span></span>

<span data-ttu-id="b1d48-118">La route non è in grado di gestire uno dei due numeri seguenti, nessuno dei quali ha 10 cifre:</span><span class="sxs-lookup"><span data-stu-id="b1d48-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="b1d48-119">5551219</span><span class="sxs-lookup"><span data-stu-id="b1d48-119">5551219</span></span>

  - <span data-ttu-id="b1d48-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="b1d48-120">12065551219</span></span>

<span data-ttu-id="b1d48-121">Il cmdlet Test-CsVoiceRoute verifica se una determinata route vocale può instradare un numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="b1d48-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b1d48-122">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="b1d48-122">Running the test</span></span>

<span data-ttu-id="b1d48-123">La verifica dell'abilità di una route vocale per instradare un numero di telefono specificato è un processo in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="b1d48-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="b1d48-124">Per prima cosa, è necessario utilizzare il cmdlet Get-CsVoiceRoute per restituire un'istanza di tale route vocale e quindi è necessario utilizzare il cmdlet Test-CsVoiceRoute per verificare la capacità di tale route di gestire il numero di telefono di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b1d48-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="b1d48-125">Ad esempio, questo comando consente di verificare se la route vocale di RedmondVoiceRoute può instradare il numero di telefono 2065551219:</span><span class="sxs-lookup"><span data-stu-id="b1d48-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="b1d48-126">Si noti che il numero di telefono deve essere digitato come previsto per gli utenti di comporre il numero.</span><span class="sxs-lookup"><span data-stu-id="b1d48-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="b1d48-127">Ad esempio, se non si prevede che gli utenti includano il codice paese e il prefisso di area durante la composizione, utilizzare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b1d48-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="b1d48-128">In questo caso, il numero di destinazione lascia fuori sia il prefisso nazionale che il prefisso.</span><span class="sxs-lookup"><span data-stu-id="b1d48-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="b1d48-129">Per utilizzare un singolo comando per testare tutte le route vocali in base a un numero di destinazione specificato, utilizzare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b1d48-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="b1d48-130">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="b1d48-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b1d48-131">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="b1d48-131">Determining success or failure</span></span>

<span data-ttu-id="b1d48-132">Se la route vocale è in grado di instradare il numero di telefono di destinazione, il cmdlet Test-CsVoiceRoute restituisce solo il valore true:</span><span class="sxs-lookup"><span data-stu-id="b1d48-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="b1d48-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="b1d48-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="b1d48-134">Vero</span><span class="sxs-lookup"><span data-stu-id="b1d48-134">True</span></span>

<span data-ttu-id="b1d48-135">Questo significa che la route può gestire numeri simili al numero di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b1d48-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="b1d48-136">Se la route vocale non è in grado di gestire il numero di destinazione, Test-CsVoiceRoute restituirà il valore false:</span><span class="sxs-lookup"><span data-stu-id="b1d48-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="b1d48-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="b1d48-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="b1d48-138">False</span><span class="sxs-lookup"><span data-stu-id="b1d48-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b1d48-139">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="b1d48-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="b1d48-140">Quando si testano le route vocali, "Failure" è un termine relativo.</span><span class="sxs-lookup"><span data-stu-id="b1d48-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="b1d48-141">In questo caso, non significa che la route è in qualche modo "interrotta;" invece, significa solo che la route non è in grado di gestire il numero di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b1d48-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="b1d48-142">Questo potrebbe essere dovuto al fatto che la route vocale non è stata configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b1d48-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="b1d48-143">Potrebbe anche significare che la route non è mai stata progettata per gestire i numeri usando questo modello.</span><span class="sxs-lookup"><span data-stu-id="b1d48-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="b1d48-144">Ad esempio, se non si desidera eseguire il routing delle chiamate ad altri paesi su una determinata route, è possibile che route sia configurata in modo da rifiutare tutti i numeri di telefono che includono un codice paese.</span><span class="sxs-lookup"><span data-stu-id="b1d48-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="b1d48-145">Se Test-CsVoiceRoute restituisce false quando si prevede che restituisca true, verificare di aver digitato correttamente il numero di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b1d48-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="b1d48-146">In questo caso, utilizzare un comando simile al seguente per visualizzare la NumberPattern configurata per la route:</span><span class="sxs-lookup"><span data-stu-id="b1d48-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1d48-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1d48-147">See Also</span></span>


[<span data-ttu-id="b1d48-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="b1d48-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

