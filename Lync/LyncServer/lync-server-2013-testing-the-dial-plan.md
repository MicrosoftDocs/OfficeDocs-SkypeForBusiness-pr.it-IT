---
title: 'Lync Server 2013: test del dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c758f2f16d59db92841a5e7ef727a41cee8a8d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530443"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="38187-102">Test del dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38187-102">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38187-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="38187-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38187-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="38187-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="38187-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="38187-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38187-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="38187-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="38187-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38187-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38187-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="38187-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="38187-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="38187-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="38187-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="38187-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="38187-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38187-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="38187-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38187-112">Description</span></span>

<span data-ttu-id="38187-113">Il cmdlet Test-CsDialPlan consente di visualizzare i risultati dell'applicazione di un dial plan a un determinato numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="38187-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="38187-114">I dial plan forniscono informazioni, ad esempio la modalità di applicazione delle regole di normalizzazione, necessarie per consentire agli utenti di VoIP aziendale di effettuare chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="38187-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="38187-115">Specificando un numero di composizione e un dial plan, questo cmdlet verificherà quale regola di normalizzazione del dial plan verrà applicata e quale sarà il numero convertito.</span><span class="sxs-lookup"><span data-stu-id="38187-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="38187-116">È possibile utilizzare questo cmdlet per risolvere i problemi relativi alle traduzioni dei numeri o per verificare la modalità di applicazione delle regole rispetto a determinati numeri.</span><span class="sxs-lookup"><span data-stu-id="38187-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="38187-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="38187-117">Running the test</span></span>

<span data-ttu-id="38187-118">Il cmdlet Test-CsDialPlan richiede di eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="38187-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="38187-119">Per prima cosa, è necessario ottenere un'istanza del dial plan in fase di testing. che è possibile eseguire utilizzando il cmdlet Get-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="38187-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="38187-120">In secondo luogo, è necessario specificare il numero di telefono che deve essere normalizzato.</span><span class="sxs-lookup"><span data-stu-id="38187-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="38187-121">Il formato utilizzato per il numero di telefono deve corrispondere al numero come composto o immesso da un utente.</span><span class="sxs-lookup"><span data-stu-id="38187-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="38187-122">Ad esempio, questo comando consente di recuperare un'istanza del dial plan, RedmondDialPlan, e di controllare se il numero di telefono 12065551219 può essere normalizzato:</span><span class="sxs-lookup"><span data-stu-id="38187-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="38187-123">Se si dispone di una regola di normalizzazione che aggiunge automaticamente il codice paese (in questo esempio 1) e il prefisso (206), potrebbe essere necessario controllare il numero di telefono 5551219, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="38187-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="38187-124">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="38187-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="38187-125">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="38187-125">Determining success or failure</span></span>

<span data-ttu-id="38187-126">Test-CsDialPlan differisce da molti dei cmdlet di test di Lync Server perché indica solo indirettamente se un test è stato completato o ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="38187-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="38187-127">Quando si utilizza Test-CsDialPlan non viene restituito un output simile al seguente con il risultato chiaramente etichettato:</span><span class="sxs-lookup"><span data-stu-id="38187-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="38187-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38187-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="38187-129">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="38187-129">Result : Success</span></span>

<span data-ttu-id="38187-130">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="38187-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="38187-131">Errore</span><span class="sxs-lookup"><span data-stu-id="38187-131">Error :</span></span>

<span data-ttu-id="38187-132">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="38187-132">Diagnosis :</span></span>

<span data-ttu-id="38187-133">In caso contrario, se Test-CsDialPlan ha esito positivo, verranno ricevute informazioni sulla regola di normalizzazione che è stata in grado di tradurre e utilizzare il numero di telefono specificato:</span><span class="sxs-lookup"><span data-stu-id="38187-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="38187-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="38187-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="38187-135">MatchingRule: Description =; Pattern = ^ ( \\ d (11)) $; Translation = + $1;</span><span class="sxs-lookup"><span data-stu-id="38187-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="38187-136">Name = prefix all; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="38187-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="38187-137">Se Test-CsDialPlan ha esito negativo (ovvero se il dial plan non dispone di una regola di normalizzazione che può tradurre il numero di telefono specificato), si riceverà solo l'output "vuoto" come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="38187-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="38187-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="38187-138">TranslatedNumber :</span></span>

<span data-ttu-id="38187-139">MatchingRule</span><span class="sxs-lookup"><span data-stu-id="38187-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="38187-140">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="38187-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="38187-141">Di seguito sono riportate alcune ragioni comuni per cui Test-CsDialPlan potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="38187-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="38187-142">Quando si specifica il numero di telefono, potrebbe essere stato utilizzato un formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="38187-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="38187-143">I dial plan includono regole di normalizzazione che consentono a Lync Server di tradurre i numeri di telefono composti o immessi da un utente.</span><span class="sxs-lookup"><span data-stu-id="38187-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="38187-144">Pertanto, il dial plan deve disporre di regole di normalizzazione che corrispondono ai numeri che gli utenti hanno la possibilità di comporre.</span><span class="sxs-lookup"><span data-stu-id="38187-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="38187-145">Ad esempio, se gli utenti possono comporre il codice paese, il prefisso e quindi il numero di telefono, significa che il dial plan deve disporre di una regola di normalizzazione per gestire i numeri di telefono, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38187-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="38187-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="38187-146">12065551219</span></span>
    
    <span data-ttu-id="38187-147">Tuttavia, se si immette un numero di telefono non corretto (ad esempio, lasciando la cifra finale), Test-CsDialPlan avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="38187-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="38187-148">Questo non è dovuto al fatto che il dial plan è difettoso, ma perché è stato immesso un numero di telefono che non può essere interpretato.</span><span class="sxs-lookup"><span data-stu-id="38187-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

