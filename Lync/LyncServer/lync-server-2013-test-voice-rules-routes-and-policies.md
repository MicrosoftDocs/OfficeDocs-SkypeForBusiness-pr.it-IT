---
title: 'Lync Server 2013: testare le regole vocali, le route e i criteri'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b2d98846e537a9a416eaabaf6b02627c7273f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="1e061-102">Testare le regole vocali, le route e i criteri in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e061-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e061-103">_**Argomento Ultima modifica:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="1e061-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e061-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="1e061-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1e061-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="1e061-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e061-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="1e061-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1e061-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e061-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e061-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="1e061-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1e061-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1e061-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1e061-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="1e061-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="1e061-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1e061-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1e061-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e061-112">Description</span></span>

<span data-ttu-id="1e061-113">Quando un utente effettua una chiamata telefonica, la route che la chiamata richiede per raggiungere la destinazione dipende sia dai criteri che dai dial plan assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="1e061-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="1e061-114">In base all'indirizzo SIP e a un numero di telefono di un utente, il cmdlet test-CsVoiceUser verifica se l'utente in questione può completare una chiamata a tale numero.</span><span class="sxs-lookup"><span data-stu-id="1e061-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="1e061-115">Se il test ha esito positivo, test-CsVoiceUser restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1e061-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="1e061-116">Il numero tradotto in formato E. 164 (in base al dial plan dell'utente)</span><span class="sxs-lookup"><span data-stu-id="1e061-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="1e061-117">Regola di normalizzazione che ha fornito tale traduzione</span><span class="sxs-lookup"><span data-stu-id="1e061-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="1e061-118">Route vocale usata (in base alla priorità del percorso);</span><span class="sxs-lookup"><span data-stu-id="1e061-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="1e061-119">L'uso del telefono che ha collegato il criterio vocale dell'utente alla route vocale.</span><span class="sxs-lookup"><span data-stu-id="1e061-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="1e061-120">Test-CsVoiceUser consente di determinare se un numero di telefono specifico verrà instradato e tradotto come previsto e può aiutare a risolvere i problemi relativi alle chiamate sperimentati dai singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="1e061-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1e061-121">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="1e061-121">Running the test</span></span>

<span data-ttu-id="1e061-122">Quando si utilizza il cmdlet test-CsVoiceUser, è necessario fornire due informazioni: il numero da chiamare (DialedNumber) e l'identità dell'account utente testato.</span><span class="sxs-lookup"><span data-stu-id="1e061-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="1e061-123">Ad esempio, questo comando verifica la capacità dell'utente che ha l'indirizzo SIP sip:kenmyer@litwareinc.com di effettuare una chiamata al numero di telefono + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="1e061-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="1e061-124">Il numero di telefono deve essere formattato nel modo previsto per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e061-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="1e061-125">Ad esempio, se gli utenti in genere non chiamano l'1 prima di effettuare una chiamata a lunga distanza, è consigliabile usare questo formato:</span><span class="sxs-lookup"><span data-stu-id="1e061-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="1e061-126">Naturalmente, in questo caso, il test non riuscirà se non si dispone di una regola di normalizzazione che può tradurre correttamente il numero 2065551219 nel formato telefonico E. 164 usato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e061-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="1e061-127">Per altre informazioni, vedere l'argomento della Guida cmdlet New-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="1e061-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="1e061-128">Se si vuole eseguire lo stesso test in ognuno degli account utente, è possibile usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1e061-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="1e061-129">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="1e061-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1e061-130">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="1e061-130">Determining success or failure</span></span>

<span data-ttu-id="1e061-131">Se il test viene completato correttamente (ovvero, se l'utente può effettuare una chiamata telefonica al numero specificato), l'output visualizzerà le informazioni come il numero di telefono tradotto e la regola di normalizzazione e la route vocale corrispondenti:</span><span class="sxs-lookup"><span data-stu-id="1e061-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="1e061-132">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="1e061-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="1e061-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="1e061-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="1e061-134">\+12065551219 descripti...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="1e061-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="1e061-135">A causa delle limitazioni della schermata di Windows PowerShell, potrebbe non essere visualizzata sullo schermo almeno alcune informazioni restituite (in particolare la descrizione completa della regola di normalizzazione corrispondente).</span><span class="sxs-lookup"><span data-stu-id="1e061-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="1e061-136">Se si è interessati solo al successo o al fallimento del test, potrebbe non essere importante.</span><span class="sxs-lookup"><span data-stu-id="1e061-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="1e061-137">Se si preferisce visualizzare tutti i dettagli dei dati restituiti, inviare l'output al cmdlet Format-List durante l'uso del test:</span><span class="sxs-lookup"><span data-stu-id="1e061-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="1e061-138">Questo visualizzerà l'output in un formato più intuitivo:</span><span class="sxs-lookup"><span data-stu-id="1e061-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="1e061-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="1e061-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="1e061-140">MatchingRule: Description =; Pattern = ^ (\\d{11}) $; Traduzione = + $1;</span><span class="sxs-lookup"><span data-stu-id="1e061-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="1e061-141">Name = prefix all; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="1e061-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="1e061-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="1e061-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="1e061-143">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="1e061-143">MatchingUsage : Local</span></span>

<span data-ttu-id="1e061-144">Se il test non riesce, test-CsVoiceUser restituirà un set vuoto di valori di proprietà:</span><span class="sxs-lookup"><span data-stu-id="1e061-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="1e061-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="1e061-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="1e061-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="1e061-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1e061-147">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="1e061-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="1e061-148">Esistono diversi motivi per cui il cmdlet test-CsVoiceUser potrebbe non riuscire: potrebbe non essere presente una regola di normalizzazione che può tradurre il numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="1e061-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="1e061-149">Potrebbero esserci problemi con la route vocale.</span><span class="sxs-lookup"><span data-stu-id="1e061-149">There could be problems with the voice route.</span></span> <span data-ttu-id="1e061-150">Potrebbe essersi verificato un problema di configurazione con il dial plan assegnato all'utente in questione.</span><span class="sxs-lookup"><span data-stu-id="1e061-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="1e061-151">Per questo motivo, potrebbe essere necessario includere il parametro Verbose quando si esegue il cmdlet test-CsVoiceUser:</span><span class="sxs-lookup"><span data-stu-id="1e061-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="1e061-152">Quando viene incluso il cmdlet Verbose, test-CsVoiceUser emetterà un account dettagliato di tutti i passaggi necessari per eseguire i controlli.</span><span class="sxs-lookup"><span data-stu-id="1e061-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="1e061-153">Ad esempio, potresti vedere i passaggi simili a questi:</span><span class="sxs-lookup"><span data-stu-id="1e061-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="1e061-154">VERBOse: individuazione dell'utente con identità "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="1e061-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="1e061-155">VERBOse: caricamento di dial plan: "" RedmondDialPlan ""</span><span class="sxs-lookup"><span data-stu-id="1e061-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="1e061-156">Queste informazioni aggiuntive possono dare suggerimenti sui passaggi che è possibile eseguire per individuare la causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="1e061-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="1e061-157">Ad esempio, l'output dettagliato illustrato qui indica che all'utente in fase di test è stato assegnato il dial plan "RedmondDialPlan".</span><span class="sxs-lookup"><span data-stu-id="1e061-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="1e061-158">Se il test ha esito negativo, un passaggio successivo logico consiste nel verificare che "RedmondDialPlan" possa tradurre il numero di telefono fornito.</span><span class="sxs-lookup"><span data-stu-id="1e061-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e061-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e061-159">See Also</span></span>


[<span data-ttu-id="1e061-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="1e061-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

