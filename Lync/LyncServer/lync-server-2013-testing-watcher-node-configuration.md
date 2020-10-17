---
title: 'Lync Server 2013: verifica della configurazione del nodo Watcher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a52b251f238b8d79602e5fe1bf2803902cbae23f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503813"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Test della configurazione del nodo Watcher in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-03_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Se si utilizza Microsoft System Center Operations Manager per monitorare Lync Server 2013, è possibile impostare "nodi Watcher": computer che periodicamente e automaticamente eseguono transazioni sintetiche per verificare che Lync Server funzioni come previsto. I nodi Watcher sono assegnati ai pool e vengono gestiti utilizzando i cmdlet di **CsWatcherNodeConfiguration** . Si noti che non è necessario installare nodi Watcher se si utilizza System Center Operations Manager. È comunque possibile monitorare il sistema senza utilizzare i nodi Watcher. L'unica differenza è che tutte le transazioni sintetiche che si desidera eseguire devono essere richiamate manualmente anziché richiamate automaticamente da Operations Manager.

Il cmdlet **Test-CsWatcherNodeConfiguration** consente di verificare che un nodo Watcher sia stato configurato correttamente e che sia assegnato a un pool Lync Server 2013 valido. Si noti che il cmdlet **Test-CsWatcherNodeConfiguration** deve essere eseguito nel nodo Watcher stesso. Non è possibile eseguire il cmdlet nei computer remoti.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Con il comando seguente vengono verificate le impostazioni di configurazione per ogni nodo Watcher utilizzato nell'organizzazione.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Nell'output di esempio riportato di seguito viene illustrato un sistema con quattro server perimetrali.

Convalida del pool di destinazione atl-cs-001.litwareinc.com rispetto alla topologia.

Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com esiste nella topologia.

Success: pool di destinazione in cui è installato il ruolo atl-cs-001.litwareinc.com.

Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com è supportato.

Esito positivo: numero di porta per il pool di destinazione 5061 atl-cs-001.litwareinc.com è corretto.

È stato avviato il controllo dei pool mancanti nella configurazione del nodo Watcher. Se viene rilevato un errore, verrà stampato.

La verifica dei pool mancanti nella configurazione del nodo Watcher è terminata.

Viene avviata la verifica delle chiavi del registro di sistema dei nodi Watcher create dall'installazione del nodo Watcher. Se viene rilevato un errore, verrà stampato.

È stato completato il controllo delle chiavi del registro di sistema del nodo Watcher create dall'installazione del nodo Watcher. Il tipo di autenticazione rilevato è Negotiate.

Esito positivo della convalida della credenziale SIP dell'utente di test: user1@ atl-cs-001.litwareinc.com nell'archivio di gestione delle credenziali.

Esito positivo della convalida della credenziale SIP dell'utente di test: user2@ atl-cs-001.litwareinc.com nell'archivio di gestione delle credenziali.

È stato avviato il controllo dei pool mancanti nella configurazione del nodo Watcher. Se viene rilevato un errore, verrà stampato.

AVVISO: pool atl-cs-001.litwareinc.com has registrar

ruolo installato, ma non sono stati configurati gli utenti di test.

La verifica dei pool mancanti nella configurazione del nodo Watcher è terminata.

Verifica delle chiavi del registro di sistema dei nodi Watcher create dall'installazione del nodo Watcher, è

iniziare. Se viene rilevato un errore, verrà stampato.

Test-CsWatcherNodeConfiguration: Impossibile trovare la chiave del registro di sistema di integrità in

\\Comunicazione software Microsoft \\ Real-Time. Verificare che il nodo Watcher. msi sia

installato correttamente.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **Test-CsWatcherNodeConfiguration** potrebbe non riuscire:

  - Il nodo Watcher non è installato correttamente.

  - Non sono configurati utenti di test.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

