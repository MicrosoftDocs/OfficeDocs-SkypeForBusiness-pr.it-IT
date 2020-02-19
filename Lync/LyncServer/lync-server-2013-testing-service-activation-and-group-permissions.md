---
title: "Lync Server 2013: testare l'attivazione del servizio e le autorizzazioni di gruppo"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bc988ec1fdfeb0c4fd5714f31342902fe45821
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Test dell'attivazione del servizio e delle autorizzazioni di gruppo in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsTopology. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsTopology consente di verificare che Lync Server 2013 funzioni correttamente in un ambito globale. Per impostazione predefinita, il cmdlet controlla l'intera infrastruttura di Lync Server, verificando che i servizi necessari siano in esecuzione e che siano impostate le autorizzazioni appropriate per questi servizi e per i gruppi di protezione universali creati durante l'installazione di Lync Server .

Oltre a verificare la validità dell'installazione di Lync Server, Test-CsTopology consente anche di controllare la validità di un servizio specifico. Questo comando consente, ad esempio, di controllare lo stato di A/V Conferencing Server nel pool atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per impostazione predefinita, Test-CsTopology Visualizza un output molto poco visualizzato sullo schermo. Al contrario, le informazioni restituite dal cmdlet vengono scritte in un file HTML. Il parametro report consente di specificare un percorso di file e un nome di file per il file HTML generato da Test-CsTopology. Se non si include il parametro report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

Nel comando di esempio seguente viene eseguito test-CsTopology e l'output viene salvato in un file denominato C\\:\\logs ComputerTest. html:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

A differenza della maggior parte dei cmdlet di test, Test-CsTopology non riporta esito positivo o negativo. In parte, a causa del numero elevato di verifiche di verifica che il cmdlet deve eseguire ogni volta che viene eseguito. Al contrario, i dati vengono salvati in un report HTML che può quindi essere visualizzato utilizzando Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsTopology potrebbe non riuscire:

  - La replica potrebbe non essere aggiornata nel computer di test. È possibile controllare lo stato della replica corrente per un computer eseguendo il cmdlet Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Se lo stato di replica non è aggiornato, è possibile forzare manualmente la replica a essere eseguita utilizzando un comando simile al seguente:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Potrebbe essere necessario abilitare la topologia. Se si modifica la topologia di Lync Server (modifiche che potrebbero influire sul computer locale), è necessario abilitare la nuova topologia. È possibile abilitare la topologia in qualsiasi momento eseguendo questo comando:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

