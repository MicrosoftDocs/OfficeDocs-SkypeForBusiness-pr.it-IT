---
title: 'Lync Server 2013: test del routing delle chiamate telefoniche PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750efc8ced1dbb4c048d10c879f0bfa2dd4a4f32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="49024-102">Test del routing delle chiamate telefoniche PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49024-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49024-103">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="49024-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49024-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="49024-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="49024-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="49024-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49024-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="49024-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="49024-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49024-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49024-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="49024-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="49024-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="49024-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="49024-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="49024-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="49024-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49024-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="49024-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49024-112">Description</span></span>

<span data-ttu-id="49024-113">Il cmdlet **Test-CsInterTrunkRouting** verifica che le chiamate possano essere instradate da un SIP a un altro.</span><span class="sxs-lookup"><span data-stu-id="49024-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="49024-114">A tale scopo, al cmdlet viene assegnato un numero di telefono e una configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="49024-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="49024-115">**Test-CsInterTrunkRouting** riporterà quindi le route corrispondenti e gli utilizzi PSTN corrispondenti per il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="49024-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="49024-116">Si noti che le chiamate possono essere instradate tra i trunk solo se i trunk dispongono di un modello numerico che corrisponde al numero di telefono specificato e solo se i trunk condividono almeno un utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="49024-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="49024-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="49024-117">Running the test</span></span>

<span data-ttu-id="49024-118">I comandi riportati di seguito restituiscono le route corrispondenti e gli utilizzi telefonici corrispondenti che consentono agli utenti di chiamare il numero di telefono 1-206-555-1219 utilizzando le impostazioni di configurazione del trunk per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="49024-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="49024-119">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="49024-119">Determining success or failure</span></span>

<span data-ttu-id="49024-120">Se le chiamate possono essere instradate da un SIP a un altro, si riceverà un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49024-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="49024-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="49024-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="49024-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="49024-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="49024-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="49024-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="49024-124">Se il test non ha avuto esito positivo, si riceverà un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49024-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="49024-125">Test-CsInterTrunkRouting: non è possibile elaborare la trasformazione degli argomenti sul parametro</span><span class="sxs-lookup"><span data-stu-id="49024-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="49024-126">' TrunkConfiguration '.</span><span class="sxs-lookup"><span data-stu-id="49024-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="49024-127">TrunkConfigurationsetting (parametro) non valido.</span><span class="sxs-lookup"><span data-stu-id="49024-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="49024-128">Specificare un</span><span class="sxs-lookup"><span data-stu-id="49024-128">Specify a</span></span>

<span data-ttu-id="49024-129">impostazione valida (parametro) e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="49024-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="49024-130">At line: 1 char: 79</span><span class="sxs-lookup"><span data-stu-id="49024-130">At line:1 char:79</span></span>

<span data-ttu-id="49024-131">\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="49024-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="49024-132">\-$T di TrunkConfiguration...</span><span class="sxs-lookup"><span data-stu-id="49024-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="49024-133">\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par</span><span class="sxs-lookup"><span data-stu-id="49024-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="49024-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="49024-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="49024-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="49024-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="49024-136">TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="49024-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="49024-137">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="49024-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="49024-138">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsInterTrunkRouting** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="49024-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="49024-139">Sono stati specificati parametri non validi.</span><span class="sxs-lookup"><span data-stu-id="49024-139">You specified invalid parameters.</span></span> <span data-ttu-id="49024-140">Il trunk potrebbe non essere ancora configurato correttamente e il numero di destinazione specificato potrebbe non essere corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="49024-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49024-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49024-141">See Also</span></span>


[<span data-ttu-id="49024-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="49024-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="49024-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="49024-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

