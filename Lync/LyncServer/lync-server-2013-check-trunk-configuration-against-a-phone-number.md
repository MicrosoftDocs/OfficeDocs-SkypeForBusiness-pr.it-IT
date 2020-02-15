---
title: 'Lync Server 2013: verificare la configurazione del trunk in base a un numero di telefono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b67831b6dbcd7dae12f9b19dd71f2512a8807189
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="11ae9-102">Controllare la configurazione del trunk in base a un numero di telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11ae9-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11ae9-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="11ae9-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11ae9-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="11ae9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="11ae9-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="11ae9-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ae9-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="11ae9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="11ae9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11ae9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11ae9-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="11ae9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="11ae9-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="11ae9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="11ae9-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="11ae9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="11ae9-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="11ae9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="11ae9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11ae9-112">Description</span></span>

<span data-ttu-id="11ae9-113">Trunk SIP connettere la rete VoIP aziendale interna di Lync Server a una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="11ae9-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="11ae9-114">La rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="11ae9-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="11ae9-115">Un PBX (IP-Public Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="11ae9-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="11ae9-116">Un session border controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="11ae9-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="11ae9-117">Il cmdlet Test-CsTrunkConfiguration verifica che il numero di telefono (come composto da un utente) possa essere convertito nella rete e. 164 e instradato su un trunk SIP specificato.</span><span class="sxs-lookup"><span data-stu-id="11ae9-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="11ae9-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="11ae9-118">Running the test</span></span>

<span data-ttu-id="11ae9-119">Per eseguire il cmdlet Test-CsTrunkConfiguration, è innanzitutto necessario utilizzare il cmdlet Get-CsTrunkConfiguration per recuperare un'istanza delle impostazioni di configurazione del trunk SIP. l'istanza viene quindi inviata tramite pipe a Test-CsTrunkConfiguration:</span><span class="sxs-lookup"><span data-stu-id="11ae9-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="11ae9-120">L'esecuzione di Test-CsTrunkConfiguration senza prima esecuzione di Get-CsTrunkConfiguration non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="11ae9-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="11ae9-121">Ad esempio, questo comando avrà esito negativo senza restituire alcun dato:</span><span class="sxs-lookup"><span data-stu-id="11ae9-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="11ae9-122">Se si dispone di più raccolte di impostazioni di configurazione del trunk SIP, è possibile utilizzare un comando simile al seguente per testare contemporaneamente ogni raccolta con lo stesso numero di telefono:</span><span class="sxs-lookup"><span data-stu-id="11ae9-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="11ae9-123">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="11ae9-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="11ae9-124">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="11ae9-124">Determining success or failure</span></span>

<span data-ttu-id="11ae9-125">Se Test-CsTrunkConfiguration può effettuare una chiamata al numero composto, il numero di telefono convertito (nel formato E. 164) e la regola utilizzata per tradurre il numero di telefono verranno entrambi visualizzati sullo schermo:</span><span class="sxs-lookup"><span data-stu-id="11ae9-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="11ae9-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="11ae9-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="11ae9-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="11ae9-127">\---------------- ------------</span></span>

<span data-ttu-id="11ae9-128">\+12065551219 globale/Redmond</span><span class="sxs-lookup"><span data-stu-id="11ae9-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="11ae9-129">Se il test ha esito negativo, Test-CsTrunkConfiguration restituirà i valori della proprietà Empty:</span><span class="sxs-lookup"><span data-stu-id="11ae9-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="11ae9-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="11ae9-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="11ae9-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="11ae9-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="11ae9-132">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="11ae9-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="11ae9-133">Se Test-CsTrunkConfiguration non restituisce una corrispondenza che in genere indica che le impostazioni di configurazione del trunk in fase di test non dispongono di una regola di conversione dei numeri di chiamata in uscita in grado di convertire il numero composto nel formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="11ae9-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="11ae9-134">Per recuperare le regole di conversione assegnate a una raccolta di impostazioni di configurazione del trunk, è possibile utilizzare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="11ae9-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="11ae9-135">Che restituisce informazioni simili a queste per ogni regola di conversione:</span><span class="sxs-lookup"><span data-stu-id="11ae9-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="11ae9-136">Descrizione: numeri di telefono senza codice di paese o indicativo di località.</span><span class="sxs-lookup"><span data-stu-id="11ae9-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="11ae9-137">Motivo: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="11ae9-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="11ae9-138">Nome: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="11ae9-138">Name : NoAreaCode</span></span>

<span data-ttu-id="11ae9-139">A questo punto, è possibile controllare il valore della proprietà pattern (ovvero una stringa di [espressione regolare](http://go.microsoft.com/fwlink/?linkid=400464) ) per verificare se una o più regole di conversione sono configurate per gestire il numero composto.</span><span class="sxs-lookup"><span data-stu-id="11ae9-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="11ae9-140">In caso contrario, è necessario modificare una delle regole esistenti (Set-CsOutboundTranslationRule) oppure utilizzare il cmdlet New-CsOutboundTranslationRule per aggiungere una nuova regola all'insieme.</span><span class="sxs-lookup"><span data-stu-id="11ae9-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11ae9-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11ae9-141">See Also</span></span>


[<span data-ttu-id="11ae9-142">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="11ae9-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

