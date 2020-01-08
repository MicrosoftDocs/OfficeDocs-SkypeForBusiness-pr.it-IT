---
title: 'Lync Server 2013: controllare le regole di normalizzazione vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="14cbd-102">Controllare le regole di normalizzazione vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14cbd-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14cbd-103">_**Argomento Ultima modifica:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="14cbd-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14cbd-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="14cbd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="14cbd-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="14cbd-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14cbd-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="14cbd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="14cbd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14cbd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14cbd-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="14cbd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="14cbd-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="14cbd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="14cbd-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="14cbd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="14cbd-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14cbd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="14cbd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14cbd-112">Description</span></span>

<span data-ttu-id="14cbd-113">Le regole di normalizzazione vocale vengono usate per convertire un numero di telefono composto da un utente (ad esempio 2065551219) nel formato E. 164 usato da Lync Server (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="14cbd-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="14cbd-114">Ad esempio, se gli utenti hanno l'abitudine di chiamare un numero di telefono senza includere il codice paese o il prefisso (ad esempio 5551219), è necessario avere una regola di normalizzazione vocale in grado di convertire tale numero nel formato E. 164: + 12065551219.</span><span class="sxs-lookup"><span data-stu-id="14cbd-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="14cbd-115">Senza tale regola, l'utente non potrà chiamare 555-1219.</span><span class="sxs-lookup"><span data-stu-id="14cbd-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="14cbd-116">Il cmdlet Test-CsVoiceNormalizationRule verifica che una regola di normalizzazione vocale specificata possa convertire correttamente un numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="14cbd-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="14cbd-117">Ad esempio, questo comando controlla se la regola di normalizzazione globale NoAreaCode può normalizzare e convertire la stringa di chiamata 5551219.</span><span class="sxs-lookup"><span data-stu-id="14cbd-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="14cbd-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="14cbd-118">Running the test</span></span>

<span data-ttu-id="14cbd-119">Per eseguire il cmdlet Test-CsVoiceNormalizationRule, è necessario prima di tutto usare il cmdlet Get-CsVoiceNormalizationRule per recuperare un'istanza della regola da provare e quindi eseguire il piping di tale istanza in Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="14cbd-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="14cbd-120">La sintassi simile a questa non funziona:</span><span class="sxs-lookup"><span data-stu-id="14cbd-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="14cbd-121">Test-CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "Global/Prefix All"</span><span class="sxs-lookup"><span data-stu-id="14cbd-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="14cbd-122">USA invece la sintassi seguente, che combina entrambi i cmdlet Get-CsVoiceNormalizationRule e Test-CsVoiceNormalizationRule:</span><span class="sxs-lookup"><span data-stu-id="14cbd-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="14cbd-123">Get-CsVoiceNormalizationRule-Identity "Global/Prefix All" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="14cbd-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14cbd-124">.</span><span class="sxs-lookup"><span data-stu-id="14cbd-124"></span></span> <span data-ttu-id="14cbd-125">In alternativa, puoi anche usare questo approccio per recuperare un'istanza di una regola e quindi testare la regola in base a un numero di telefono specificato:</span><span class="sxs-lookup"><span data-stu-id="14cbd-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="14cbd-126">Immettere il valore per il parametro DialedNumber esattamente come previsto per la chiamata del numero.</span><span class="sxs-lookup"><span data-stu-id="14cbd-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="14cbd-127">Ad esempio, se la regola di normalizzazione vocale specificata dovrebbe aggiungere automaticamente il codice paese (l'1 iniziale nel valore 12065551219), è necessario escludere il codice paese:</span><span class="sxs-lookup"><span data-stu-id="14cbd-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="14cbd-128">Se la regola è configurata correttamente, il codice paese verrà aggiunto automaticamente quando si traduce il numero nel formato E. 164 usato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14cbd-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="14cbd-129">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="14cbd-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="14cbd-130">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="14cbd-130">Determining success or failure</span></span>

<span data-ttu-id="14cbd-131">Se la regola di normalizzazione vocale specificata può tradurre il numero fornito, il numero tradotto verrà visualizzato sullo schermo:</span><span class="sxs-lookup"><span data-stu-id="14cbd-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="14cbd-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="14cbd-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="14cbd-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="14cbd-133">\+12065551219</span></span>

<span data-ttu-id="14cbd-134">Se il test ha esito negativo, verrà restituito un numero tradotto vuoto:</span><span class="sxs-lookup"><span data-stu-id="14cbd-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="14cbd-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="14cbd-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="14cbd-136">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="14cbd-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="14cbd-137">Se il test-CsVoiceNormalizationRule restituisce un numero tradotto che indica che la regola di normalizzazione vocale specificata non è riuscita a tradurre il numero di telefono fornito nel formato E. 164 usato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14cbd-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="14cbd-138">Per verificare che, prima di tutto, assicurarsi di aver digitato correttamente il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="14cbd-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="14cbd-139">Ad esempio, ci si aspetterebbe che la regola di normalizzazione vocale abbia problemi a tradurre un numero simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="14cbd-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="14cbd-140">Supponendo che il numero sia stato immesso correttamente, il passaggio successivo deve essere verificare che la regola di normalizzazione specificata sia progettata per gestire il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="14cbd-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="14cbd-141">Ad esempio, una regola di normalizzazione può essere progettata per gestire il formato 12065551219, ma una seconda regola può essere progettata per gestire il numero 2065551219.</span><span class="sxs-lookup"><span data-stu-id="14cbd-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="14cbd-142">(Questo è lo stesso numero di telefono, meno il codice paese 1 all'inizio). Per ottenere informazioni dettagliate su una regola di normalizzazione vocale, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="14cbd-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="14cbd-143">Per ottenere informazioni dettagliate su tutte le regole di normalizzazione vocale, eseguire invece questo comando:</span><span class="sxs-lookup"><span data-stu-id="14cbd-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14cbd-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14cbd-144">See Also</span></span>


[<span data-ttu-id="14cbd-145">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="14cbd-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

