---
title: 'Lync Server 2013: testare il numero di telefono in una route vocale'
description: 'Lync Server 2013: testare il numero di telefono in una route vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563392"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Testare il numero di telefono in una route vocale in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoiceRoute. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Le route vocali interagiscono con i criteri vocali per instradare le chiamate vocali aziendali alla rete PSTN. Ogni route vocale include un'espressione regolare (uno schema numerico) che identifica i numeri di telefono che verranno instradati tramite una determinata route vocale: la route sarà in grado di gestire i numeri di telefono che corrispondono a questa espressione regolare. Ad esempio, una route vocale può avere un'espressione regolare che consente di gestire qualsiasi numero di 10 cifre. Questo significa che la route sarebbe in grado di gestire un numero di telefono come questo:

  - 2065551219

La route non è in grado di gestire uno dei due numeri seguenti, nessuno dei quali ha 10 cifre:

  - 5551219

  - 12065551219

Il cmdlet Test-CsVoiceRoute verifica se una determinata route vocale può instradare un numero di telefono specificato.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

La verifica dell'abilità di una route vocale per instradare un numero di telefono specificato è un processo in due passaggi. Per prima cosa, è necessario utilizzare il cmdlet Get-CsVoiceRoute per restituire un'istanza di tale route vocale e quindi è necessario utilizzare il cmdlet Test-CsVoiceRoute per verificare la capacità di tale route di gestire il numero di telefono di destinazione. Ad esempio, questo comando consente di verificare se la route vocale di RedmondVoiceRoute può instradare il numero di telefono 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Si noti che il numero di telefono deve essere digitato come previsto per gli utenti di comporre il numero. Ad esempio, se non si prevede che gli utenti includano il codice paese e il prefisso di area durante la composizione, utilizzare una sintassi simile alla seguente:

`-TargetNumber "5551219"`

In questo caso, il numero di destinazione lascia fuori sia il prefisso nazionale che il prefisso.

Per utilizzare un singolo comando per testare tutte le route vocali in base a un numero di destinazione specificato, utilizzare una sintassi simile alla seguente:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se la route vocale è in grado di instradare il numero di telefono di destinazione, il cmdlet Test-CsVoiceRoute restituisce solo il valore true:

MatchesPattern

\--------------

Vero

Questo significa che la route può gestire numeri simili al numero di destinazione. Se la route vocale non è in grado di gestire il numero di destinazione, Test-CsVoiceRoute restituirà il valore false:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Quando si testano le route vocali, "Failure" è un termine relativo. In questo caso, non significa che la route è in qualche modo "interrotta;" invece, significa solo che la route non è in grado di gestire il numero di destinazione. Questo potrebbe essere dovuto al fatto che la route vocale non è stata configurata correttamente. Potrebbe anche significare che la route non è mai stata progettata per gestire i numeri usando questo modello. Ad esempio, se non si desidera eseguire il routing delle chiamate ad altri paesi su una determinata route, è possibile che route sia configurata in modo da rifiutare tutti i numeri di telefono che includono un codice paese. Se Test-CsVoiceRoute restituisce false quando si prevede che restituisca true, verificare di aver digitato correttamente il numero di destinazione. In questo caso, utilizzare un comando simile al seguente per visualizzare la NumberPattern configurata per la route:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

