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
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="dd9a1-102">Test di routing delle chiamate telefoniche PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd9a1-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd9a1-103">_**Argomento Ultima modifica:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="dd9a1-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd9a1-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="dd9a1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dd9a1-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="dd9a1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9a1-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="dd9a1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dd9a1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd9a1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9a1-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="dd9a1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dd9a1-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dd9a1-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="dd9a1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="dd9a1-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="dd9a1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dd9a1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd9a1-112">Description</span></span>

<span data-ttu-id="dd9a1-113">Il cmdlet **Test-CsInterTrunkRouting** verifica che le chiamate possano essere instradate da un SIP a un altro.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="dd9a1-114">A questo scopo, al cmdlet viene assegnato un numero di telefono e una configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="dd9a1-115">**Test-CsInterTrunkRouting** riporterà quindi le route corrispondenti e gli usi PSTN corrispondenti per il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="dd9a1-116">Tieni presente che le chiamate possono essere instradate tra Trunks solo se i trunk hanno un modello di numero corrispondente al numero di telefono specificato e solo se i trunk condividono almeno un uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dd9a1-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="dd9a1-117">Running the test</span></span>

<span data-ttu-id="dd9a1-118">I comandi riportati di seguito restituiscono le route corrispondenti e gli usi di telefono corrispondenti che consentono agli utenti di chiamare il numero di telefono 1-206-555-1219 usando le impostazioni di configurazione trunk per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dd9a1-119">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="dd9a1-119">Determining success or failure</span></span>

<span data-ttu-id="dd9a1-120">Se le chiamate possono essere instradate da un SIP a un altro, si riceverà un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="dd9a1-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="dd9a1-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="dd9a1-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="dd9a1-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="dd9a1-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="dd9a1-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="dd9a1-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="dd9a1-124">Se il test non è riuscito, si riceverà un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="dd9a1-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="dd9a1-125">Test-CsInterTrunkRouting: non è possibile elaborare la trasformazione degli argomenti sul parametro</span><span class="sxs-lookup"><span data-stu-id="dd9a1-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="dd9a1-126">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="dd9a1-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="dd9a1-127">TrunkConfigurationsetting non valido (parametro).</span><span class="sxs-lookup"><span data-stu-id="dd9a1-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="dd9a1-128">Specificare un</span><span class="sxs-lookup"><span data-stu-id="dd9a1-128">Specify a</span></span>

<span data-ttu-id="dd9a1-129">impostazione valida (parametro) e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="dd9a1-130">At line: 1 carattere: 79</span><span class="sxs-lookup"><span data-stu-id="dd9a1-130">At line:1 char:79</span></span>

<span data-ttu-id="dd9a1-131">\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="dd9a1-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="dd9a1-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="dd9a1-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="dd9a1-133">\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par</span><span class="sxs-lookup"><span data-stu-id="dd9a1-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="dd9a1-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="dd9a1-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="dd9a1-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="dd9a1-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="dd9a1-136">TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="dd9a1-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dd9a1-137">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="dd9a1-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="dd9a1-138">Ecco alcuni motivi comuni per cui **Test-CsInterTrunkRouting** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="dd9a1-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="dd9a1-139">Sono stati specificati parametri non validi.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-139">You specified invalid parameters.</span></span> <span data-ttu-id="dd9a1-140">Il trunk potrebbe non essere ancora configurato correttamente e il numero di destinazione specificato potrebbe non essere corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="dd9a1-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd9a1-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd9a1-141">See Also</span></span>


[<span data-ttu-id="dd9a1-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="dd9a1-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="dd9a1-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="dd9a1-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

