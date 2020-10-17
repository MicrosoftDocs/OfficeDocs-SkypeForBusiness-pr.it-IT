---
title: 'Lync Server 2013: testare le regole vocali, le route e i criteri'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b903ff4453f15bc22b6715abe27cc045381c0e5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527853"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Testare le regole vocali, le route e i criteri in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoiceUser. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Quando un utente effettua una chiamata telefonica, la route che la chiamata richiede per raggiungere la destinazione dipende sia dai criteri che dai dial plan assegnati a quell'utente. Dato l'indirizzo SIP e il numero di telefono di un utente, il cmdlet Test-CsVoiceUser verifica se l'utente in questione può completare una chiamata a tale numero. Se il test ha esito positivo, Test-CsVoiceUser restituirà gli elementi seguenti:

  - Il numero convertito nel formato E. 164 (in base al dial plan dell'utente)

  - Regola di normalizzazione che ha fornito la traduzione

  - La route vocale utilizzata (in base alla priorità del percorso);

  - Utilizzo del telefono che ha collegato il criterio vocale dell'utente alla route vocale.

Test-CsVoiceUser consente di determinare se il numero di telefono specifico viene instradato e tradotto come previsto e può essere utile per la risoluzione dei problemi relativi alle chiamate riscontrati da singoli utenti.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Quando si esegue il cmdlet Test-CsVoiceUser, è necessario fornire due informazioni: il numero da comporre (DialedNumber) e l'identità dell'account utente da testare. Ad esempio, questo comando verifica la capacità dell'utente che ha l'indirizzo SIP sip:kenmyer@litwareinc.com di effettuare una chiamata al numero di telefono + 1206555-1219:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

Il numero di telefono deve essere formattato in modo da prevederne la composizione. Ad esempio, se gli utenti in genere non eseguono la chiamata 1 prima di effettuare chiamate interurbane, è necessario utilizzare questo formato:

`-DialedNumber "2065551219"`

Naturalmente, in tal caso, il test avrà esito negativo se non si dispone di una regola di normalizzazione che può tradurre correttamente il numero 2065551219 nel formato del telefono E. 164 utilizzato da Lync Server. Per ulteriori informazioni, vedere l'argomento della Guida New-CsVoiceNormalizationRule cmdlet.

Se si desidera eseguire lo stesso test su ciascuno degli account utente, è possibile utilizzare un comando simile al seguente:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se il test viene completato correttamente (ovvero se l'utente può effettuare una chiamata al numero specificato), l'output mostrerà informazioni come il numero di telefono convertito e la regola di normalizzazione corrispondente e la route vocale:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 descripti...    LocalRoute local

A causa delle limitazioni della schermata di Windows PowerShell, almeno alcune informazioni restituite, in particolare la descrizione completa della regola di normalizzazione corrispondente, potrebbero non essere visualizzate sullo schermo. Se si è interessati solo all'esito positivo o negativo del test, potrebbe non essere importante. Se si preferisce visualizzare tutti i dettagli dei dati restituiti, eseguire il piping dell'output al cmdlet Format-List quando si esegue il test:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Che visualizzerà l'output in un formato più facile da usare per i lettori:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ ( \\ d {11} ) $; Translation = + $1;

Name = prefix all; IsInternalExtension = false

FirsMatchingRoute : LocalRoute

MatchingUsage: local

Se il test ha esito negativo, Test-CsVoiceUser restituirà un set vuoto di valori della proprietà:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Esistono diversi motivi per i quali il cmdlet Test-CsVoiceUser potrebbe avere esito negativo: potrebbe non essere una regola di normalizzazione che può tradurre il numero di telefono specificato. Potrebbero verificarsi problemi con la route vocale. Potrebbe esserci un problema di configurazione con il dial plan assegnato all'utente in questione. Per questo motivo, è possibile che si desideri includere il parametro Verbose quando si esegue il cmdlet Test-CsVoiceUser:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Quando viene incluso il cmdlet Verbose, Test-CsVoiceUser rilascerà un account dettagliato di tutti i passaggi necessari per l'esecuzione dei controlli. Ad esempio, è possibile che vengano visualizzati passaggi analoghi a quelli riportati di seguito: 

VERBOse: individuazione di un utente con identità "sip:kenmyer@litwareinc.com"

VERBOse: Loading dial plan: "RedmondDialPlan"

Queste informazioni aggiuntive possono fornire suggerimenti per i passaggi che è possibile eseguire per individuare la causa dell'errore. Ad esempio, l'output dettagliato mostrato di seguito indica che all'utente che è stato sottoposto a test è stato assegnato il dial plan RedmondDialPlan. Se il test non ha avuto esito positivo, si verificherà che RedmondDialPlan può tradurre il numero di telefono specificato.

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

