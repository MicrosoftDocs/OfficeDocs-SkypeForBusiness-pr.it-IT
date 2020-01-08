---
title: 'Lync Server 2013: testare il dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="e273d-102">Testare il dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e273d-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e273d-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e273d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e273d-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="e273d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e273d-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="e273d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e273d-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="e273d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e273d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e273d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e273d-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="e273d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e273d-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e273d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e273d-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="e273d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="e273d-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e273d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e273d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e273d-112">Description</span></span>

<span data-ttu-id="e273d-113">Il cmdlet Test-CsDialPlan consente di visualizzare i risultati dell'applicazione di un dial plan a un numero di telefono specifico.</span><span class="sxs-lookup"><span data-stu-id="e273d-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="e273d-114">I dial plan offrono informazioni, ad esempio la modalità di applicazione delle regole di normalizzazione, necessarie per consentire agli utenti di VoIP aziendale di effettuare chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="e273d-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="e273d-115">In base a un numero composto e a un dial plan, questo cmdlet verificherà la regola di normalizzazione all'interno del dial plan e il numero tradotto.</span><span class="sxs-lookup"><span data-stu-id="e273d-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="e273d-116">Puoi usare questo cmdlet per risolvere i problemi relativi alle traduzioni dei numeri o per verificare come applicare regole a determinati numeri.</span><span class="sxs-lookup"><span data-stu-id="e273d-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e273d-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="e273d-117">Running the test</span></span>

<span data-ttu-id="e273d-118">Il cmdlet Test-CsDialPlan richiede di eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="e273d-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="e273d-119">Prima di tutto, è necessario ottenere un'istanza del dial plan da testare; Questa operazione può essere eseguita usando il cmdlet Get-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="e273d-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="e273d-120">In secondo luogo, devi specificare il numero di telefono che deve essere normalizzato.</span><span class="sxs-lookup"><span data-stu-id="e273d-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="e273d-121">Il formato usato per il numero di telefono deve corrispondere al numero selezionato/immesso da un utente.</span><span class="sxs-lookup"><span data-stu-id="e273d-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="e273d-122">Ad esempio, questo comando Recupera un'istanza del dial plan, "RedmondDialPlan", e controlla se il numero di telefono 12065551219 può essere normalizzato:</span><span class="sxs-lookup"><span data-stu-id="e273d-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="e273d-123">Se si ha una regola di normalizzazione che aggiunge automaticamente il codice paese (in questo esempio 1) e il prefisso (206), è possibile controllare il numero di telefono 5551219, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e273d-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="e273d-124">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="e273d-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e273d-125">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="e273d-125">Determining success or failure</span></span>

<span data-ttu-id="e273d-126">Test-CsDialPlan differisce da molti dei cmdlet di test di Lync Server perché indica solo indirettamente se un test è riuscito o non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="e273d-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="e273d-127">Quando si usa Test-CsDialPlan non si riceve l'output posteriore simile a quello con il risultato chiaramente etichettato:</span><span class="sxs-lookup"><span data-stu-id="e273d-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="e273d-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e273d-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e273d-129">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="e273d-129">Result : Success</span></span>

<span data-ttu-id="e273d-130">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="e273d-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="e273d-131">Errore</span><span class="sxs-lookup"><span data-stu-id="e273d-131">Error :</span></span>

<span data-ttu-id="e273d-132">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="e273d-132">Diagnosis :</span></span>

<span data-ttu-id="e273d-133">Se invece Test-CsDialPlan ha esito positivo, riceverai informazioni sulla regola di normalizzazione che è stata in grado di tradurre e usare il numero di telefono specificato:</span><span class="sxs-lookup"><span data-stu-id="e273d-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="e273d-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="e273d-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="e273d-135">MatchingRule: Description =; Pattern = ^ (\\d (11)) $; Traduzione = + $1;</span><span class="sxs-lookup"><span data-stu-id="e273d-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="e273d-136">Nome = prefisso tutti; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="e273d-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="e273d-137">Se Test-CsDialPlan non riesce, ovvero se il dial plan non ha una regola di normalizzazione che può tradurre il numero di telefono specificato, è sufficiente ricevere l'output "vuoto" nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e273d-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="e273d-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="e273d-138">TranslatedNumber :</span></span>

<span data-ttu-id="e273d-139">MatchingRule</span><span class="sxs-lookup"><span data-stu-id="e273d-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e273d-140">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="e273d-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="e273d-141">Ecco alcuni motivi comuni per cui Test-CsDialPlan potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="e273d-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="e273d-142">Quando si specifica il numero di telefono, è possibile che sia stato usato un formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="e273d-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="e273d-143">I dial plan includono regole di normalizzazione che consentono a Lync Server di tradurre i numeri di telefono chiamati o immessi da un utente.</span><span class="sxs-lookup"><span data-stu-id="e273d-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="e273d-144">Di conseguenza, il dial plan dovrebbe avere regole di normalizzazione che corrispondono ai numeri che gli utenti hanno la possibilità di effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e273d-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="e273d-145">Ad esempio, se gli utenti possono chiamare il prefisso, il prefisso e quindi il numero di telefono, significa che il dial plan deve avere una regola di normalizzazione per gestire i numeri di telefono, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e273d-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="e273d-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="e273d-146">12065551219</span></span>
    
    <span data-ttu-id="e273d-147">Se invece si immette un numero di telefono non corretto, ad esempio se si esce dalla cifra finale, il Test-CsDialPlan non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="e273d-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="e273d-148">Non perché il dial plan sia difettoso, ma perché è stato immesso un numero di telefono che non può essere interpretato.</span><span class="sxs-lookup"><span data-stu-id="e273d-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

