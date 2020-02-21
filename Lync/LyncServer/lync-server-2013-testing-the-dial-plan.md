---
title: 'Lync Server 2013: test del dial plan'
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
ms.openlocfilehash: a83f8058dd761386329c3c0bc58a50c4aef7bdb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Test del dial plan in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Giornaliero</p></td>
</tr>
<tr class="even">
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsDialPlan. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsDialPlan consente di visualizzare i risultati dell'applicazione di un dial plan a un determinato numero di telefono. I dial plan forniscono informazioni, ad esempio la modalità di applicazione delle regole di normalizzazione, necessarie per consentire agli utenti di VoIP aziendale di effettuare chiamate telefoniche. Specificando un numero di composizione e un dial plan, questo cmdlet verificherà quale regola di normalizzazione del dial plan verrà applicata e quale sarà il numero convertito.

È possibile utilizzare questo cmdlet per risolvere i problemi relativi alle traduzioni dei numeri o per verificare la modalità di applicazione delle regole rispetto a determinati numeri.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsDialPlan richiede di eseguire due operazioni. Per prima cosa, è necessario ottenere un'istanza del dial plan in fase di testing. che è possibile eseguire utilizzando il cmdlet Get-CsDialPlan. In secondo luogo, è necessario specificare il numero di telefono che deve essere normalizzato. Il formato utilizzato per il numero di telefono deve corrispondere al numero come composto o immesso da un utente. Ad esempio, questo comando consente di recuperare un'istanza del dial plan, RedmondDialPlan, e di controllare se il numero di telefono 12065551219 può essere normalizzato:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Se si dispone di una regola di normalizzazione che aggiunge automaticamente il codice paese (in questo esempio 1) e il prefisso (206), potrebbe essere necessario controllare il numero di telefono 5551219, come indicato di seguito:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Test-CsDialPlan è diverso da molti dei cmdlet di test di Lync Server perché indica solo indirettamente se un test è stato completato o ha avuto esito negativo. Quando si utilizza Test-CsDialPlan non viene restituito un output simile al seguente con il risultato chiaramente etichettato:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se invece Test-CsDialPlan ha esito positivo, verranno ricevute informazioni sulla regola di normalizzazione che è stata in grado di tradurre correttamente e utilizzare il numero di telefono specificato:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ (\\d (11)) $; Translation = + $1;

Name = prefix all; IsInternalExtension = false

Se Test-CsDialPlan ha esito negativo, ovvero se il dial plan non dispone di una regola di normalizzazione che può tradurre il numero di telefono specificato, verrà visualizzato solo l'output "vuoto" come indicato di seguito:

TranslatedNumber :

MatchingRule

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsDialPlan potrebbe non riuscire:

  - Quando si specifica il numero di telefono, potrebbe essere stato utilizzato un formato non corretto. I dial plan includono regole di normalizzazione che consentono a Lync Server di tradurre i numeri di telefono composti o immessi da un utente. Pertanto, il dial plan deve disporre di regole di normalizzazione che corrispondono ai numeri che gli utenti hanno la possibilità di comporre. Ad esempio, se gli utenti possono comporre il codice paese, il prefisso e quindi il numero di telefono, significa che il dial plan deve disporre di una regola di normalizzazione per gestire i numeri di telefono, ad esempio:
    
    12065551219
    
    Tuttavia, se si immette un numero di telefono errato (ad esempio, lasciando la cifra finale), Test-CsDialPlan avrà esito negativo. Questo non è dovuto al fatto che il dial plan è difettoso, ma perché è stato immesso un numero di telefono che non può essere interpretato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

