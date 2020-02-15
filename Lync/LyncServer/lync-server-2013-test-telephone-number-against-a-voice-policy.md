---
title: 'Lync Server 2013: testare il numero di telefono per un criterio vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a234419dc6f06ae9bdc8d7c198873bdc3c706701
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="576e4-102">Verificare il numero di telefono di un criterio vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="576e4-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="576e4-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="576e4-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576e4-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="576e4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="576e4-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="576e4-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576e4-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="576e4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="576e4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="576e4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576e4-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="576e4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="576e4-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="576e4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="576e4-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="576e4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="576e4-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="576e4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="576e4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="576e4-112">Description</span></span>

<span data-ttu-id="576e4-113">La possibilità per gli utenti di VoIP aziendale di effettuare chiamate telefoniche in uscita tramite le cerniere PSTN (Public Switched Telephone Network), in gran parte, su tre elementi:</span><span class="sxs-lookup"><span data-stu-id="576e4-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="576e4-114">Criteri vocali assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="576e4-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="576e4-115">Le route vocali utilizzate per instradare le chiamate da Lync Server alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="576e4-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="576e4-116">Utilizzo della rete PSTN, una proprietà di Lync Server che connette un criterio vocale a una route vocale.</span><span class="sxs-lookup"><span data-stu-id="576e4-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="576e4-117">L'utilizzo della rete PSTN è particolarmente importante: è la proprietà che connette un criterio vocale a una route vocale.</span><span class="sxs-lookup"><span data-stu-id="576e4-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="576e4-118">(Si dice che un criterio vocale e una route vocale siano connessi se hanno almeno un utilizzo PSTN in comune). I criteri vocali possono essere configurati senza specificare un utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="576e4-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="576e4-119">In tal caso, gli utenti a cui è stato assegnato il criterio non saranno in grado di effettuare chiamate in uscita sulla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="576e4-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="576e4-120">Analogamente, le route vocali che non dispongono di almeno un utilizzo PSTN specificato non saranno in grado di instradare le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="576e4-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="576e4-121">Il cmdlet Test-CsVoicePolicy verifica che un determinato criterio vocale abbia un utilizzo PSTN e che l'utilizzo sia condiviso da almeno una route vocale.</span><span class="sxs-lookup"><span data-stu-id="576e4-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="576e4-122">Se la verifica eseguita da Test-CsVoicePolicy ha esito positivo, il cmdlet restituirà il nome della prima route vocale valida individuata e anche il nome dell'utilizzo PSTN che connette il criterio alla route.</span><span class="sxs-lookup"><span data-stu-id="576e4-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="576e4-123">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="576e4-123">Running the test</span></span>

<span data-ttu-id="576e4-124">Per eseguire il cmdlet Test-CsVoicePolicy, è necessario innanzitutto utilizzare il cmdlet Get-CsVoicePolicy per recuperare un'istanza del criterio vocale da testare. tale istanza deve quindi essere inviata tramite pipe a Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="576e4-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="576e4-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="576e4-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="576e4-126">Si noti che questo comando, che non utilizza Get-CsVoicePolicy per recuperare un'istanza del criterio vocale, avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="576e4-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="576e4-127">Se si desidera controllare tutti i criteri vocali in base a un numero di telefono specificato, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="576e4-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="576e4-128">Si noti che TargetNumber deve essere specificato utilizzando il formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="576e4-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="576e4-129">Test-CsVoicePolicy non tenterà di normalizzare o tradurre i numeri di telefono nel formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="576e4-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="576e4-130">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="576e4-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="576e4-131">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="576e4-131">Determining success or failure</span></span>

<span data-ttu-id="576e4-132">Se il criterio vocale è in grado di trovare sia una route vocale corrispondente che un utilizzo PSTN corrispondente, sia la route che l'utilizzo verranno visualizzati sullo schermo:</span><span class="sxs-lookup"><span data-stu-id="576e4-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="576e4-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="576e4-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="576e4-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="576e4-134">\------------------ -------------</span></span>

<span data-ttu-id="576e4-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="576e4-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="576e4-136">Se non è possibile trovare una route vocale appropriata o un utilizzo PSTN appropriato, i valori delle proprietà vuote verranno visualizzati sullo schermo:</span><span class="sxs-lookup"><span data-stu-id="576e4-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="576e4-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="576e4-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="576e4-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="576e4-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="576e4-139">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="576e4-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="576e4-140">Se Test-CsVoicePolicy non restituisce una corrispondenza che potrebbe significare che il criterio vocale non condivide un utilizzo PSTN con una route vocale.</span><span class="sxs-lookup"><span data-stu-id="576e4-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="576e4-141">Per verificare che, utilizzare un cmdlet simile al seguente per verificare che gli utilizzi PSTN assegnati al criterio vocale:</span><span class="sxs-lookup"><span data-stu-id="576e4-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="576e4-142">Successivamente, eseguire questo comando per determinare gli utilizzi PSTN assegnati a ciascuna delle route vocali:</span><span class="sxs-lookup"><span data-stu-id="576e4-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="576e4-143">Se vengono visualizzate eventuali corrispondenze, ovvero se vengono visualizzate una o più route vocali che condividono almeno un utilizzo PSTN con il criterio vocale, è necessario eseguire il cmdlet Test-CsVoiceRoute per verificare che la route vocale sia in grado di comporre il numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="576e4-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="576e4-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="576e4-144">See Also</span></span>


[<span data-ttu-id="576e4-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="576e4-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

