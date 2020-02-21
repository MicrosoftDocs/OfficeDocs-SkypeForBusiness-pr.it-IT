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
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Controllare la configurazione del trunk in base a un numero di telefono in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsTrunkConfiguration. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Trunk SIP connettere la rete VoIP aziendale interna di Lync Server a una delle seguenti operazioni:

  - La rete PSTN (Public Switched Telephone Network).

  - Un PBX (IP-Public Branch Exchange).

  - Un session border controller (SBC).

Il cmdlet Test-CsTrunkConfiguration verifica che il numero di telefono (come composto da un utente) possa essere convertito nella rete e. 164 e instradato su un trunk SIP specificato.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per eseguire il cmdlet Test-CsTrunkConfiguration, è innanzitutto necessario utilizzare il cmdlet Get-CsTrunkConfiguration per recuperare un'istanza delle impostazioni di configurazione del trunk SIP. l'istanza viene quindi inviata tramite pipe a Test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

L'esecuzione di Test-CsTrunkConfiguration senza prima esecuzione di Get-CsTrunkConfiguration non funzionerà. Ad esempio, questo comando avrà esito negativo senza restituire alcun dato:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Se si dispone di più raccolte di impostazioni di configurazione del trunk SIP, è possibile utilizzare un comando simile al seguente per testare contemporaneamente ogni raccolta con lo stesso numero di telefono:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsTrunkConfiguration può effettuare una chiamata al numero composto, il numero di telefono convertito (nel formato E. 164) e la regola utilizzata per tradurre il numero di telefono verranno entrambi visualizzati sullo schermo:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 globale/Redmond

Se il test ha esito negativo, Test-CsTrunkConfiguration restituirà i valori della proprietà Empty:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se Test-CsTrunkConfiguration non restituisce una corrispondenza che in genere indica che le impostazioni di configurazione del trunk in fase di test non dispongono di una regola di conversione dei numeri di chiamata in uscita in grado di convertire il numero composto nel formato E. 164. Per recuperare le regole di conversione assegnate a una raccolta di impostazioni di configurazione del trunk, è possibile utilizzare una sintassi simile alla seguente:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Che restituisce informazioni simili a queste per ogni regola di conversione:

Descrizione: numeri di telefono senza codice di paese o indicativo di località.

Motivo: ^\\+ (\\d\*) $

`Translation : $1`

Nome: NoAreaCode

A questo punto, è possibile controllare il valore della proprietà pattern (ovvero una stringa di [espressione regolare](https://go.microsoft.com/fwlink/?linkid=400464) ) per verificare se una o più regole di conversione sono configurate per gestire il numero composto. In caso contrario, è necessario modificare una delle regole esistenti (Set-CsOutboundTranslationRule) oppure utilizzare il cmdlet New-CsOutboundTranslationRule per aggiungere una nuova regola all'insieme.

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

