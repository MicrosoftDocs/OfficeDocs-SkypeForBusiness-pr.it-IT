---
title: 'Lync Server 2013: verificare la configurazione del trunk in base a un numero di telefono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Verificare la configurazione del trunk in base a un numero di telefono in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsTrunkConfiguration. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Trunk SIP connettere la rete VoIP aziendale interna di Lync Server a una delle opzioni seguenti:

  - Rete PSTN (Public Switched Telephone Network).

  - IP-PBX (Public Branch Exchange).

  - Un session border controller (SBC).

Il cmdlet Test-CsTrunkConfiguration verifica che un numero di telefono (come composto da un utente) possa essere convertito nella rete e. 164 e instradato su un trunk SIP specificato.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per eseguire il cmdlet Test-CsTrunkConfiguration, è necessario prima di tutto utilizzare il cmdlet Get-CsTrunkConfiguration per recuperare un'istanza delle impostazioni di configurazione del trunk SIP. Questa istanza viene quindi inviata tramite pipe a Test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

L'uso di Test-CsTrunkConfiguration senza prima eseguire Get-CsTrunkConfiguration non funziona. Ad esempio, questo comando avrà esito negativo senza restituire i dati:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Se si hanno più raccolte di impostazioni di configurazione trunk SIP, è possibile usare un comando simile al seguente per testare contemporaneamente ogni raccolta con lo stesso numero di telefono:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se Test-CsTrunkConfiguration può effettuare una chiamata al numero composto, il numero di telefono tradotto (nel formato E. 164) e la regola usata per tradurre il numero di telefono verranno visualizzati sullo schermo:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 globale/Redmond

Se il test ha esito negativo, Test-CsTrunkConfiguration restituirà valori di proprietà vuoti:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsTrunkConfiguration non restituisce una corrispondenza che in genere indica che le impostazioni di configurazione del trunk test non hanno una regola di traduzione del numero di chiamata in uscita in grado di convertire il numero composto nel formato E. 164. Per recuperare le regole di traduzione assegnate a una raccolta di impostazioni di configurazione trunk, è possibile usare una sintassi simile alla seguente:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Che restituisce informazioni simili a queste per ogni regola di traduzione:

Descrizione: numeri di telefono senza codice paese o prefisso.

Motivo: ^\\+ (\\d\*) $

`Translation : $1`

Nome: NoAreaCode

A questo punto, controlla il valore della proprietà pattern (che è una stringa di [espressione regolare](http://go.microsoft.com/fwlink/?linkid=400464) ) per verificare se una delle regole di traduzione è configurata per gestire il numero composto. In caso contrario, sarà necessario modificare una delle regole esistenti (Set-CsOutboundTranslationRule) oppure usare il cmdlet New-CsOutboundTranslationRule per aggiungere una nuova regola alla raccolta.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

