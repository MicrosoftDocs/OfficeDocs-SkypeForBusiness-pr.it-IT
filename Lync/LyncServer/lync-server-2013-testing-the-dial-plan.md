---
title: 'Lync Server 2013: testare il dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0e39b88d7b6c90a55d236038d03cc4cc717319
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Testare il dial plan in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-05_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsDialPlan. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsDialPlan consente di visualizzare i risultati dell'applicazione di un dial plan a un numero di telefono specifico. I dial plan offrono informazioni, ad esempio la modalità di applicazione delle regole di normalizzazione, necessarie per consentire agli utenti di VoIP aziendale di effettuare chiamate telefoniche. In base a un numero composto e a un dial plan, questo cmdlet verificherà la regola di normalizzazione all'interno del dial plan e il numero tradotto.

Puoi usare questo cmdlet per risolvere i problemi relativi alle traduzioni dei numeri o per verificare come applicare regole a determinati numeri.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsDialPlan richiede di eseguire due operazioni. Prima di tutto, è necessario ottenere un'istanza del dial plan da testare; Questa operazione può essere eseguita usando il cmdlet Get-CsDialPlan. In secondo luogo, devi specificare il numero di telefono che deve essere normalizzato. Il formato usato per il numero di telefono deve corrispondere al numero selezionato/immesso da un utente. Ad esempio, questo comando Recupera un'istanza del dial plan, "RedmondDialPlan", e controlla se il numero di telefono 12065551219 può essere normalizzato:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Se si ha una regola di normalizzazione che aggiunge automaticamente il codice paese (in questo esempio 1) e il prefisso (206), è possibile controllare il numero di telefono 5551219, come indicato di seguito:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Test-CsDialPlan differisce da molti dei cmdlet di test di Lync Server perché indica solo indirettamente se un test è riuscito o non è riuscito. Quando si usa Test-CsDialPlan non si riceve l'output posteriore simile a quello con il risultato chiaramente etichettato:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se invece Test-CsDialPlan ha esito positivo, riceverai informazioni sulla regola di normalizzazione che è stata in grado di tradurre e usare il numero di telefono specificato:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ (\\d (11)) $; Traduzione = + $1;

Nome = prefisso tutti; IsInternalExtension = false

Se Test-CsDialPlan non riesce, ovvero se il dial plan non ha una regola di normalizzazione che può tradurre il numero di telefono specificato, è sufficiente ricevere l'output "vuoto" nel modo seguente:

TranslatedNumber :

MatchingRule

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsDialPlan potrebbe non riuscire:

  - Quando si specifica il numero di telefono, è possibile che sia stato usato un formato non corretto. I dial plan includono regole di normalizzazione che consentono a Lync Server di tradurre i numeri di telefono chiamati o immessi da un utente. Di conseguenza, il dial plan dovrebbe avere regole di normalizzazione che corrispondono ai numeri che gli utenti hanno la possibilità di effettuare la chiamata. Ad esempio, se gli utenti possono chiamare il prefisso, il prefisso e quindi il numero di telefono, significa che il dial plan deve avere una regola di normalizzazione per gestire i numeri di telefono, ad esempio:
    
    12065551219
    
    Se invece si immette un numero di telefono non corretto, ad esempio se si esce dalla cifra finale, il Test-CsDialPlan non riuscirà. Non perché il dial plan sia difettoso, ma perché è stato immesso un numero di telefono che non può essere interpretato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

