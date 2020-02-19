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
ms.openlocfilehash: 8da7334e00c0361a5c8ad840dbf57ee7d5024763
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="6ff64-102">Testare le regole vocali, le route e i criteri in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ff64-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ff64-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="6ff64-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ff64-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="6ff64-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6ff64-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="6ff64-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ff64-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="6ff64-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6ff64-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff64-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ff64-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="6ff64-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6ff64-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6ff64-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6ff64-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="6ff64-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="6ff64-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ff64-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6ff64-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ff64-112">Description</span></span>

<span data-ttu-id="6ff64-113">Quando un utente effettua una chiamata telefonica, la route che la chiamata richiede per raggiungere la destinazione dipende sia dai criteri che dai dial plan assegnati a quell'utente.</span><span class="sxs-lookup"><span data-stu-id="6ff64-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="6ff64-114">Dato un indirizzo SIP e un numero di telefono di un utente, il cmdlet test-CsVoiceUser verifica se l'utente in questione può completare una chiamata a tale numero.</span><span class="sxs-lookup"><span data-stu-id="6ff64-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="6ff64-115">Se il test ha esito positivo, test-CsVoiceUser restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6ff64-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="6ff64-116">Il numero convertito nel formato E. 164 (in base al dial plan dell'utente)</span><span class="sxs-lookup"><span data-stu-id="6ff64-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="6ff64-117">Regola di normalizzazione che ha fornito la traduzione</span><span class="sxs-lookup"><span data-stu-id="6ff64-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="6ff64-118">La route vocale utilizzata (in base alla priorità del percorso);</span><span class="sxs-lookup"><span data-stu-id="6ff64-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="6ff64-119">Utilizzo del telefono che ha collegato il criterio vocale dell'utente alla route vocale.</span><span class="sxs-lookup"><span data-stu-id="6ff64-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="6ff64-120">Test-CsVoiceUser consente di determinare se il numero di telefono specifico viene instradato e tradotto come previsto e può essere utile per risolvere i problemi relativi alle chiamate che sono stati sperimentati da singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="6ff64-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6ff64-121">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="6ff64-121">Running the test</span></span>

<span data-ttu-id="6ff64-122">Quando si esegue il cmdlet test-CsVoiceUser, è necessario fornire due informazioni: il numero da comporre (DialedNumber) e l'identità dell'account utente da testare.</span><span class="sxs-lookup"><span data-stu-id="6ff64-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="6ff64-123">Ad esempio, questo comando verifica la capacità dell'utente che ha l'indirizzo SIP sip:kenmyer@litwareinc.com di effettuare una chiamata al numero di telefono + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="6ff64-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="6ff64-124">Il numero di telefono deve essere formattato in modo da prevederne la composizione.</span><span class="sxs-lookup"><span data-stu-id="6ff64-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="6ff64-125">Ad esempio, se gli utenti in genere non eseguono la chiamata 1 prima di effettuare chiamate interurbane, è necessario utilizzare questo formato:</span><span class="sxs-lookup"><span data-stu-id="6ff64-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="6ff64-126">Naturalmente, in tal caso, il test avrà esito negativo se non si dispone di una regola di normalizzazione che può tradurre correttamente il numero 2065551219 nel formato del telefono E. 164 utilizzato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ff64-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="6ff64-127">Per ulteriori informazioni, vedere l'argomento della Guida New-CsVoiceNormalizationRule cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ff64-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="6ff64-128">Se si desidera eseguire lo stesso test su ciascuno degli account utente, è possibile utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6ff64-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="6ff64-129">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="6ff64-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6ff64-130">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="6ff64-130">Determining success or failure</span></span>

<span data-ttu-id="6ff64-131">Se il test viene completato correttamente (ovvero se l'utente può effettuare una chiamata al numero specificato), l'output mostrerà informazioni come il numero di telefono convertito e la regola di normalizzazione corrispondente e la route vocale:</span><span class="sxs-lookup"><span data-stu-id="6ff64-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="6ff64-132">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="6ff64-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="6ff64-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="6ff64-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="6ff64-134">\+12065551219 descripti...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="6ff64-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="6ff64-135">A causa delle limitazioni della schermata di Windows PowerShell, almeno alcune informazioni restituite, in particolare la descrizione completa della regola di normalizzazione corrispondente, potrebbero non essere visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="6ff64-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="6ff64-136">Se si è interessati solo all'esito positivo o negativo del test, potrebbe non essere importante.</span><span class="sxs-lookup"><span data-stu-id="6ff64-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="6ff64-137">Se si preferisce visualizzare tutti i dettagli dei dati restituiti, eseguire il piping dell'output al cmdlet Format-List durante l'esecuzione del test:</span><span class="sxs-lookup"><span data-stu-id="6ff64-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="6ff64-138">Che visualizzerà l'output in un formato più facile da usare per i lettori:</span><span class="sxs-lookup"><span data-stu-id="6ff64-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="6ff64-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="6ff64-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="6ff64-140">MatchingRule: Description =; Pattern = ^ (\\d{11}) $; Translation = + $1;</span><span class="sxs-lookup"><span data-stu-id="6ff64-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="6ff64-141">Name = prefix all; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="6ff64-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="6ff64-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="6ff64-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="6ff64-143">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="6ff64-143">MatchingUsage : Local</span></span>

<span data-ttu-id="6ff64-144">Se il test ha esito negativo, test-CsVoiceUser restituirà un set vuoto di valori della proprietà:</span><span class="sxs-lookup"><span data-stu-id="6ff64-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="6ff64-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="6ff64-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="6ff64-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="6ff64-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6ff64-147">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="6ff64-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="6ff64-148">Esistono diversi motivi per cui il cmdlet test-CsVoiceUser potrebbe avere esito negativo: potrebbe non essere una regola di normalizzazione che può tradurre il numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="6ff64-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="6ff64-149">Potrebbero verificarsi problemi con la route vocale.</span><span class="sxs-lookup"><span data-stu-id="6ff64-149">There could be problems with the voice route.</span></span> <span data-ttu-id="6ff64-150">Potrebbe esserci un problema di configurazione con il dial plan assegnato all'utente in questione.</span><span class="sxs-lookup"><span data-stu-id="6ff64-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="6ff64-151">Per questo motivo, potrebbe essere necessario includere il parametro Verbose quando si esegue il cmdlet test-CsVoiceUser:</span><span class="sxs-lookup"><span data-stu-id="6ff64-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="6ff64-152">Quando viene incluso il cmdlet Verbose, test-CsVoiceUser rilascerà un account dettagliato di tutti i passaggi necessari per l'esecuzione dei controlli.</span><span class="sxs-lookup"><span data-stu-id="6ff64-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="6ff64-153">Ad esempio, è possibile che vengano visualizzati passaggi analoghi a quelli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="6ff64-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="6ff64-154">VERBOse: individuazione di un utente con identità "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="6ff64-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="6ff64-155">VERBOse: Loading dial plan: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="6ff64-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="6ff64-156">Queste informazioni aggiuntive possono fornire suggerimenti per i passaggi che è possibile eseguire per individuare la causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="6ff64-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="6ff64-157">Ad esempio, l'output dettagliato mostrato di seguito indica che all'utente che è stato sottoposto a test è stato assegnato il dial plan RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="6ff64-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="6ff64-158">Se il test non ha avuto esito positivo, si verificherà che RedmondDialPlan può tradurre il numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="6ff64-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ff64-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ff64-159">See Also</span></span>


[<span data-ttu-id="6ff64-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="6ff64-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

