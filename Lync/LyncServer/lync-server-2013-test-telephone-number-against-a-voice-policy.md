---
title: 'Lync Server 2013: testare il numero di telefono per un criterio vocale'
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
ms.openlocfilehash: f2ac10938dbbc2810e5b43aae85711bf8413ad27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519163"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Verificare il numero di telefono di un criterio vocale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-20_


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
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoicePolicy. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

La possibilità per gli utenti di VoIP aziendale di effettuare chiamate telefoniche in uscita tramite le cerniere PSTN (Public Switched Telephone Network), in gran parte, su tre elementi:

  - Criteri vocali assegnati all'utente.

  - Le route vocali utilizzate per instradare le chiamate da Lync Server alla rete PSTN.

  - Utilizzo della rete PSTN, una proprietà di Lync Server che connette un criterio vocale a una route vocale.

L'utilizzo della rete PSTN è particolarmente importante: è la proprietà che connette un criterio vocale a una route vocale. (Si dice che un criterio vocale e una route vocale siano connessi se hanno almeno un utilizzo PSTN in comune). I criteri vocali possono essere configurati senza specificare un utilizzo PSTN. In tal caso, gli utenti a cui è stato assegnato il criterio non saranno in grado di effettuare chiamate in uscita sulla rete PSTN. Analogamente, le route vocali che non dispongono di almeno un utilizzo PSTN specificato non saranno in grado di instradare le chiamate alla rete PSTN.

Il cmdlet Test-CsVoicePolicy verifica che un determinato criterio vocale abbia un utilizzo PSTN e che l'utilizzo sia condiviso da almeno una route vocale. Se la verifica eseguita da Test-CsVoicePolicy ha esito positivo, il cmdlet restituirà il nome della prima route vocale valida individuata e anche il nome dell'utilizzo PSTN che connette il criterio alla route.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per eseguire il cmdlet Test-CsVoicePolicy è necessario innanzitutto utilizzare il cmdlet Get-CsVoicePolicy recuperare un'istanza del criterio vocale da testare. tale istanza deve quindi essere inviata tramite pipe a Test-CsVoicePolicy. Ad esempio:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Si noti che questo comando, che non utilizza Get-CsVoicePolicy per recuperare un'istanza del criterio vocale, avrà esito negativo:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Se si desidera controllare tutti i criteri vocali in base a un numero di telefono specificato, utilizzare un comando simile al seguente:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Si noti che TargetNumber deve essere specificato utilizzando il formato E. 164. Test-CsVoicePolicy non tenterà di normalizzare o tradurre i numeri di telefono nel formato E. 164.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se il criterio vocale è in grado di trovare sia una route vocale corrispondente che un utilizzo PSTN corrispondente, sia la route che l'utilizzo verranno visualizzati sullo schermo:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Se non è possibile trovare una route vocale appropriata o un utilizzo PSTN appropriato, i valori delle proprietà vuote verranno visualizzati sullo schermo:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se Test-CsVoicePolicy non restituisce una corrispondenza che potrebbe significare che il criterio vocale non condivide un utilizzo PSTN con una route vocale. Per verificare che, utilizzare un cmdlet simile al seguente per verificare che gli utilizzi PSTN assegnati al criterio vocale:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Successivamente, eseguire questo comando per determinare gli utilizzi PSTN assegnati a ciascuna delle route vocali:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Se vengono visualizzate eventuali corrispondenze, ovvero se vengono visualizzate una o più route vocali che condividono almeno un utilizzo PSTN con il criterio vocale, è necessario eseguire il cmdlet Test-CsVoiceRoute per verificare che la route vocale sia in grado di comporre il numero di telefono specificato.

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

