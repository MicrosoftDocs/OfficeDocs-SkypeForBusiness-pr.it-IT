---
title: "Lync Server 2013: verificare l'attivazione del servizio e le autorizzazioni di gruppo"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Test dell'attivazione del servizio e delle autorizzazioni di gruppo in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsTopology. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsTopology consente di verificare che Lync Server 2013 funzioni correttamente in un ambito globale. Per impostazione predefinita, il cmdlet controlla l'intera infrastruttura Lync Server, verificando che i servizi necessari siano in corso e che siano impostate le autorizzazioni appropriate per questi servizi e per i gruppi di sicurezza universale creati durante l'installazione di Lync Server .

Oltre a verificare la validità dell'installazione di Lync Server, Test-CsTopology consente anche di verificare la validità di un servizio specifico. Questo comando, ad esempio, controlla lo stato di un/V Conferencing Server nel pool atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per impostazione predefinita, Test-CsTopology Visualizza un output molto piccolo sullo schermo. Le informazioni restituite dal cmdlet vengono invece scritte in un file HTML. Il parametro report consente di specificare un percorso file e un nome file per il file HTML generato da Test-CsTopology. Se non si include il parametro di report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

Il comando di esempio seguente esegue Test-CsTopology e salva l'output in un file denominato C:\\logs\\ComputerTest. html:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

A differenza della maggior parte dei cmdlet di test, Test-CsTopology non riporta l'esito positivo o negativo. In parte, questo è dovuto al numero elevato di controlli di verifica che il cmdlet deve apportare ogni volta che viene eseguito. I dati vengono invece salvati in un report HTML che può essere visualizzato tramite Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsTopology potrebbe non riuscire:

  - La replica potrebbe non essere aggiornata nel computer di test. Per controllare lo stato di replica corrente di un computer, è possibile eseguire il cmdlet Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Se lo stato di replica non è aggiornato, è possibile forzare manualmente la replica in modo che venga eseguita usando un comando simile al seguente:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Potrebbe essere necessario abilitare la topologia. Se si modifica la topologia di Lync Server (modifiche che potrebbero influire sul computer locale), è necessario abilitare la nuova topologia. È possibile abilitare la topologia in qualsiasi momento eseguendo questo comando:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

