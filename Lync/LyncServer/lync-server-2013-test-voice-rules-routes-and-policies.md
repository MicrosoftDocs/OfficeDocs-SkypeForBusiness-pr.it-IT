---
title: 'Lync Server 2013: testare le regole vocali, le route e i criteri'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Testare le regole vocali, le route e i criteri in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet test-CsVoiceUser. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Quando un utente effettua una chiamata telefonica, la route che la chiamata richiede per raggiungere la destinazione dipende sia dai criteri che dai dial plan assegnati all'utente. In base all'indirizzo SIP e a un numero di telefono di un utente, il cmdlet test-CsVoiceUser verifica se l'utente in questione può completare una chiamata a tale numero. Se il test ha esito positivo, test-CsVoiceUser restituisce quanto segue:

  - Il numero tradotto in formato E. 164 (in base al dial plan dell'utente)

  - Regola di normalizzazione che ha fornito tale traduzione

  - Route vocale usata (in base alla priorità del percorso);

  - L'uso del telefono che ha collegato il criterio vocale dell'utente alla route vocale.

Test-CsVoiceUser consente di determinare se un numero di telefono specifico verrà instradato e tradotto come previsto e può aiutare a risolvere i problemi relativi alle chiamate sperimentati dai singoli utenti.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Quando si utilizza il cmdlet test-CsVoiceUser, è necessario fornire due informazioni: il numero da chiamare (DialedNumber) e l'identità dell'account utente testato. Ad esempio, questo comando verifica la capacità dell'utente che ha l'indirizzo SIP sip:kenmyer@litwareinc.com di effettuare una chiamata al numero di telefono + 1206555-1219:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

Il numero di telefono deve essere formattato nel modo previsto per la chiamata. Ad esempio, se gli utenti in genere non chiamano l'1 prima di effettuare una chiamata a lunga distanza, è consigliabile usare questo formato:

`-DialedNumber "2065551219"`

Naturalmente, in questo caso, il test non riuscirà se non si dispone di una regola di normalizzazione che può tradurre correttamente il numero 2065551219 nel formato telefonico E. 164 usato da Lync Server. Per altre informazioni, vedere l'argomento della Guida cmdlet New-CsVoiceNormalizationRule.

Se si vuole eseguire lo stesso test in ognuno degli account utente, è possibile usare un comando simile al seguente:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se il test viene completato correttamente (ovvero, se l'utente può effettuare una chiamata telefonica al numero specificato), l'output visualizzerà le informazioni come il numero di telefono tradotto e la regola di normalizzazione e la route vocale corrispondenti:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 descripti...    LocalRoute local

A causa delle limitazioni della schermata di Windows PowerShell, potrebbe non essere visualizzata sullo schermo almeno alcune informazioni restituite (in particolare la descrizione completa della regola di normalizzazione corrispondente). Se si è interessati solo al successo o al fallimento del test, potrebbe non essere importante. Se si preferisce visualizzare tutti i dettagli dei dati restituiti, inviare l'output al cmdlet Format-List durante l'uso del test:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Questo visualizzerà l'output in un formato più intuitivo:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ (\\d{11}) $; Traduzione = + $1;

Name = prefix all; IsInternalExtension = false

FirsMatchingRoute : LocalRoute

MatchingUsage: local

Se il test non riesce, test-CsVoiceUser restituirà un set vuoto di valori di proprietà:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Esistono diversi motivi per cui il cmdlet test-CsVoiceUser potrebbe non riuscire: potrebbe non essere presente una regola di normalizzazione che può tradurre il numero di telefono specificato. Potrebbero esserci problemi con la route vocale. Potrebbe essersi verificato un problema di configurazione con il dial plan assegnato all'utente in questione. Per questo motivo, potrebbe essere necessario includere il parametro Verbose quando si esegue il cmdlet test-CsVoiceUser:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Quando viene incluso il cmdlet Verbose, test-CsVoiceUser emetterà un account dettagliato di tutti i passaggi necessari per eseguire i controlli. Ad esempio, potresti vedere i passaggi simili a questi: 

VERBOse: individuazione dell'utente con identità "sip:kenmyer@litwareinc.com"

VERBOse: caricamento di dial plan: "" RedmondDialPlan ""

Queste informazioni aggiuntive possono dare suggerimenti sui passaggi che è possibile eseguire per individuare la causa dell'errore. Ad esempio, l'output dettagliato illustrato qui indica che all'utente in fase di test è stato assegnato il dial plan "RedmondDialPlan". Se il test ha esito negativo, un passaggio successivo logico consiste nel verificare che "RedmondDialPlan" possa tradurre il numero di telefono fornito.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

