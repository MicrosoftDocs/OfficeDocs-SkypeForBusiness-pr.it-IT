---
title: 'Lync Server 2013: controllare le regole di normalizzazione vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e383f38d5af6f106354a766c857635bcd87eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Controllare le regole di normalizzazione vocale in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsVoiceNormalizationRule. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Le regole di normalizzazione vocale vengono usate per convertire un numero di telefono composto da un utente (ad esempio 2065551219) nel formato E. 164 usato da Lync Server (+ 12065551219). Ad esempio, se gli utenti hanno l'abitudine di chiamare un numero di telefono senza includere il codice paese o il prefisso (ad esempio 5551219), è necessario avere una regola di normalizzazione vocale in grado di convertire tale numero nel formato E. 164: + 12065551219. Senza tale regola, l'utente non potrà chiamare 555-1219.

Il cmdlet Test-CsVoiceNormalizationRule verifica che una regola di normalizzazione vocale specificata possa convertire correttamente un numero di telefono specificato. Ad esempio, questo comando controlla se la regola di normalizzazione globale NoAreaCode può normalizzare e convertire la stringa di chiamata 5551219.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per eseguire il cmdlet Test-CsVoiceNormalizationRule, è necessario prima di tutto usare il cmdlet Get-CsVoiceNormalizationRule per recuperare un'istanza della regola da provare e quindi eseguire il piping di tale istanza in Test-CsVoiceNormalizationRule. La sintassi simile a questa non funziona:

Test-CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "Global/Prefix All"

USA invece la sintassi seguente, che combina entrambi i cmdlet Get-CsVoiceNormalizationRule e Test-CsVoiceNormalizationRule:

Get-CsVoiceNormalizationRule-Identity "Global/Prefix All" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . In alternativa, puoi anche usare questo approccio per recuperare un'istanza di una regola e quindi testare la regola in base a un numero di telefono specificato:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Immettere il valore per il parametro DialedNumber esattamente come previsto per la chiamata del numero. Ad esempio, se la regola di normalizzazione vocale specificata dovrebbe aggiungere automaticamente il codice paese (l'1 iniziale nel valore 12065551219), è necessario escludere il codice paese:

`-DialedNumber "2065551219"`

Se la regola è configurata correttamente, il codice paese verrà aggiunto automaticamente quando si traduce il numero nel formato E. 164 usato da Lync Server.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se la regola di normalizzazione vocale specificata può tradurre il numero fornito, il numero tradotto verrà visualizzato sullo schermo:

TranslatedNumber

\----------------

\+12065551219

Se il test ha esito negativo, verrà restituito un numero tradotto vuoto:

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se il test-CsVoiceNormalizationRule restituisce un numero tradotto che indica che la regola di normalizzazione vocale specificata non è riuscita a tradurre il numero di telefono fornito nel formato E. 164 usato da Lync Server. Per verificare che, prima di tutto, assicurarsi di aver digitato correttamente il numero di telefono. Ad esempio, ci si aspetterebbe che la regola di normalizzazione vocale abbia problemi a tradurre un numero simile al seguente:

`-DialedNumber "1"`

Supponendo che il numero sia stato immesso correttamente, il passaggio successivo deve essere verificare che la regola di normalizzazione specificata sia progettata per gestire il numero di telefono. Ad esempio, una regola di normalizzazione può essere progettata per gestire il formato 12065551219, ma una seconda regola può essere progettata per gestire il numero 2065551219. (Questo è lo stesso numero di telefono, meno il codice paese 1 all'inizio). Per ottenere informazioni dettagliate su una regola di normalizzazione vocale, eseguire un comando simile al seguente:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Per ottenere informazioni dettagliate su tutte le regole di normalizzazione vocale, eseguire invece questo comando:

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

