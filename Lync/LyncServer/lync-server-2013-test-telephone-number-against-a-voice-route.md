---
title: 'Lync Server 2013: verificare il numero di telefono in una route vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Verificare il numero di telefono in una route vocale in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsVoiceRoute. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Le route vocali collaborano con i criteri vocali per instradare le chiamate vocali aziendali alla rete PSTN. Ogni route vocale include un'espressione regolare (uno schema numerico) che identifica i numeri di telefono che verranno instradati attraverso una determinata route vocale: la route sarà in grado di gestire tutti i numeri di telefono corrispondenti a questa espressione regolare. Ad esempio, una route vocale può avere un'espressione regolare che consente di gestire qualsiasi numero di 10 cifre. Questo significa che la route sarebbe in grado di gestire un numero di telefono come questo:

  - 2065551219

La route non è in grado di gestire uno dei due numeri seguenti, nessuna delle quali contiene 10 cifre:

  - 5551219

  - 12065551219

Il cmdlet Test-CsVoiceRoute verifica se una determinata route vocale può instradare un numero di telefono specificato.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

La verifica della capacità di una route vocale di instradare un numero di telefono specificato è un processo in due passaggi. Prima di tutto, devi usare il cmdlet Get-CsVoiceRoute per restituire un'istanza della route vocale e quindi devi usare il cmdlet Test-CsVoiceRoute per verificare la capacità della route di gestire il numero di telefono di destinazione. Ad esempio, questo comando verifica se la route vocale RedmondVoiceRoute può instradare il numero di telefono 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Tieni presente che il numero di telefono deve essere digitato quando prevedi che gli utenti compongano il numero. Ad esempio, se non si prevede che gli utenti includano il codice paese e il prefisso di area durante la chiamata, usare una sintassi simile alla seguente:

`-TargetNumber "5551219"`

In questo caso, il numero di destinazione lascia fuori sia il prefisso locale che il prefisso.

Per usare un singolo comando per testare tutte le route vocali in base a un numero di destinazione specificato, usare una sintassi simile alla seguente:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se la route vocale può instradare il numero di telefono di destinazione, il cmdlet Test-CsVoiceRoute restituisce semplicemente il valore true:

MatchesPattern

\--------------

True

Questo significa che la route può gestire numeri simili al numero di destinazione. Se la route vocale non è in grado di gestire il numero di destinazione, Test-CsVoiceRoute restituisce il valore false:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Quando si provano le route vocali, "Failure" è un termine relativo. In questo caso, non significa che la route sia in qualche modo "spezzata;", ma significa semplicemente che la route non può gestire il numero di destinazione. Questo potrebbe essere il fatto che la route vocale sia stata configurata in modo non corretto. Potrebbe anche significare che la route non è mai stata progettata per gestire i numeri usando questo modello. Ad esempio, se non si vuole instradare le chiamate ad altri paesi tramite una determinata route, tale route può essere configurata per rifiutare tutti i numeri di telefono che includono un codice paese. Se Test-CsVoiceRoute restituisce false quando si prevede che restituisca true, verificare di aver digitato correttamente il numero di destinazione. In questo caso, usa un comando simile a questo per visualizzare la NumberPattern configurata per la route:

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

