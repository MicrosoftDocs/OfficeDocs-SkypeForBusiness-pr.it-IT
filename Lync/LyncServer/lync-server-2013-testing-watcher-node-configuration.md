---
title: 'Lync Server 2013: verifica della configurazione del nodo Watcher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d2c79de4f86e490244ef63948c263d8f387fc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Verifica della configurazione del nodo Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-11-03_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Se si usa Microsoft System Center Operations Manager per monitorare Lync Server 2013, è possibile configurare "nodi Watcher": computer che eseguono periodicamente e automaticamente transazioni sintetiche per verificare che Lync Server funzioni come previsto. I nodi Watcher vengono assegnati ai pool e gestiti tramite i cmdlet **CsWatcherNodeConfiguration** . Si noti che non è necessario installare i nodi Watcher se si usa System Center Operations Manager. È comunque possibile monitorare il sistema senza usare i nodi Watcher. L'unica differenza è che tutte le transazioni sintetiche che si desidera eseguire devono essere richiamate manualmente anziché richiamate automaticamente da Operations Manager.

Il cmdlet **Test-CsWatcherNodeConfiguration** consente di verificare che un nodo Watcher sia stato configurato correttamente e sia stato assegnato a un pool di Lync Server 2013 valido. Tieni presente che il cmdlet **Test-CsWatcherNodeConfiguration** deve essere eseguito nel nodo Watcher stesso. Il cmdlet non può essere eseguito in computer remoti.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il comando seguente verifica le impostazioni di configurazione per ogni nodo Watcher che viene usato nell'organizzazione.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

L'output di esempio riuscito seguente mostra un sistema con quattro server perimetrali.

Convalida della atl-cs-001.litwareinc.com del pool di destinazione rispetto alla topologia.

Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com esiste nella topologia.

Operazione riuscita: pool di destinazione atl-cs-001.litwareinc.com ha installato il ruolo di registrar.

Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com è supportato.

Operazione riuscita: numero di porta per il pool di destinazione di 5061 atl-cs-001.litwareinc.com è corretto.

Viene avviato il controllo dei pool mancanti nella configurazione del nodo Watcher. Se viene rilevato un errore, verrà stampato.

Il controllo dei pool mancanti nella configurazione del nodo Watcher è terminato.

Viene avviato il controllo delle chiavi del registro di sistema di Watcher create dall'installazione del nodo Watcher. Se viene rilevato un errore, verrà stampato.

Il controllo delle chiavi del registro di sistema di Watcher create dall'installazione di Watcher node è terminato. Il tipo di autenticazione rilevata è Negotiate.

È stata convalidata l'esistenza della credenziale dell'utente di test SIP: user1@ atl-cs-001.litwareinc.com in Credential Management store.

È stata convalidata l'esistenza della credenziale dell'utente di test SIP: user2@ atl-cs-001.litwareinc.com in Credential Management store.

Viene avviato il controllo dei pool mancanti nella configurazione del nodo Watcher. Se viene rilevato un errore, verrà stampato.

AVVISO: il pool di atl-cs-001.litwareinc.com ha un registrar

ruolo installato, ma non sono stati configurati utenti di test.

Il controllo dei pool mancanti nella configurazione del nodo Watcher è terminato.

Il controllo delle chiavi del registro di sistema di Watcher create dall'installazione di Watcher node è

Iniziato. Se viene rilevato un errore, verrà stampato.

Test-CsWatcherNodeConfiguration: Impossibile trovare la chiave del registro di sistema di integrità

Software\\Microsoft\\per comunicazioni in tempo reale. Verificare che Watcher node. msi sia

installato correttamente.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **Test-CsWatcherNodeConfiguration** potrebbe non riuscire:

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

