---
title: 'Lync Server 2013: verificare il numero di telefono in base a un criterio vocale'
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
ms.openlocfilehash: 37d0c9ae6512cb7755c7ef73e4cfd3e37b92884d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Verificare il numero di telefono in un criterio vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Mensile</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsVoicePolicy. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

La capacità degli utenti di VoIP aziendale di effettuare telefonate in uscita sulle cerniere PSTN (Public Switched Telephone Network), in gran parte, su tre aspetti:

  - Criterio vocale assegnato all'utente.

  - Route vocali usate per instradare le chiamate da Lync Server alla rete PSTN.

  - L'utilizzo PSTN, una proprietà server Lync che connette un criterio vocale a una route vocale.

L'utilizzo PSTN è particolarmente importante: è la proprietà che connette un criterio vocale a una route vocale. (Un criterio vocale e una route vocale sono detti connessi se hanno almeno un uso PSTN in comune). I criteri vocali possono essere configurati senza specificare un uso PSTN. In questo caso, gli utenti a cui è stato assegnato il criterio non saranno in grado di effettuare chiamate in uscita tramite la rete PSTN. Analogamente, le route vocali che non hanno almeno un utilizzo PSTN specificato non saranno in grado di instradare le chiamate alla rete PSTN.

Il cmdlet Test-CsVoicePolicy verifica che un criterio vocale specifico abbia un uso PSTN e che l'utilizzo sia condiviso da almeno una route vocale. Se la verifica eseguita da Test-CsVoicePolicy riesce, il cmdlet riporta il nome della prima route vocale valida trovata e anche il nome dell'utilizzo PSTN che connette il criterio alla route.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per eseguire il cmdlet Test-CsVoicePolicy, è necessario prima di tutto utilizzare il cmdlet Get-CsVoicePolicy per recuperare un'istanza del criterio vocale da testare. Questa istanza deve quindi essere inviata tramite pipe a Test-CsVoicePolicy. Ad esempio:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Tieni presente che questo comando, che non usa Get-CsVoicePolicy per recuperare un'istanza di un criterio vocale, avrà esito negativo:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Se si vuole controllare tutti i criteri vocali in base a un numero di telefono specificato, usare un comando simile al seguente:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Tieni presente che TargetNumber deve essere specificato usando il formato E. 164. Test-CsVoicePolicy non tenterà di normalizzare o tradurre i numeri di telefono nel formato E. 164.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se il criterio vocale può trovare sia una route vocale corrispondente che un uso PSTN corrispondente, verranno visualizzate sullo schermo sia la route che l'utilizzo:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Se non è possibile trovare una route vocale appropriata o un utilizzo PSTN appropriato, i valori delle proprietà vuote verranno visualizzati sullo schermo:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsVoicePolicy non restituisce una corrispondenza che potrebbe significare che il criterio vocale non condivide un uso PSTN con una route vocale. Per verificare che, usare un cmdlet simile al seguente per verificare che gli usi PSTN assegnati al criterio vocale:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Esegui quindi questo comando per determinare gli usi PSTN assegnati a ogni route vocale:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Se vengono visualizzate eventuali corrispondenze, ovvero se sono presenti una o più route vocali che condividono almeno un uso PSTN con il criterio vocale, è necessario eseguire il cmdlet Test-CsVoiceRoute per verificare che la route vocale possa chiamare il numero di telefono fornito.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

