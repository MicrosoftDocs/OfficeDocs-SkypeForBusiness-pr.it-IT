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

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Test di routing delle chiamate telefoniche PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Quotidiana</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsInterTrunkRouting</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsInterTrunkRouting** verifica che le chiamate possano essere instradate da un SIP a un altro. A questo scopo, al cmdlet viene assegnato un numero di telefono e una configurazione trunk. **Test-CsInterTrunkRouting** riporterà quindi le route corrispondenti e gli usi PSTN corrispondenti per il numero specificato. Tieni presente che le chiamate possono essere instradate tra Trunks solo se i trunk hanno un modello di numero corrispondente al numero di telefono specificato e solo se i trunk condividono almeno un uso PSTN.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

I comandi riportati di seguito restituiscono le route corrispondenti e gli usi di telefono corrispondenti che consentono agli utenti di chiamare il numero di telefono 1-206-555-1219 usando le impostazioni di configurazione trunk per il sito Redmond.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se le chiamate possono essere instradate da un SIP a un altro, si riceverà un output simile al seguente:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Se il test non è riuscito, si riceverà un output simile al seguente:

Test-CsInterTrunkRouting: non è possibile elaborare la trasformazione degli argomenti sul parametro

"TrunkConfiguration". TrunkConfigurationsetting non valido (parametro). Specificare un

impostazione valida (parametro) e quindi riprovare.

At line: 1 carattere: 79

\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **Test-CsInterTrunkRouting** potrebbe non riuscire:

  - Sono stati specificati parametri non validi. Il trunk potrebbe non essere ancora configurato correttamente e il numero di destinazione specificato potrebbe non essere corretto o non valido.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

