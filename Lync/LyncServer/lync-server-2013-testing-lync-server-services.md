---
title: 'Lync Server 2013: test dei servizi di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Test dei servizi di Lync Server in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsComputer. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Test-CsComputer verifica lo stato di tutti i servizi di Lync Server 2013 in uso nel computer locale. (Test-CsComputer può essere eseguito solo localmente, non può essere eseguito da un'istanza remota di Windows PowerShell). Il cmdlet controlla inoltre se le porte del firewall appropriate vengono aperte nel computer e determina se i gruppi di Active Directory creati durante l'installazione di Lync Server 2013 sono stati aggiunti ai gruppi locali corrispondenti. Ad esempio, Test-CsComputer verificherà che il gruppo Active Directory RTCUniversalUserAdmins sia stato aggiunto al gruppo Administrators.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsComputer può essere eseguito solo nel computer locale, non è possibile chiamare Test-CsComputer da un'istanza remota di Windows PowerShell. Per impostazione predefinita, Test-CsComputer Visualizza un output molto poco sullo schermo, mentre le informazioni restituite dal cmdlet vengono scritte in un file HTML. Per questo motivo, è consigliabile includere il parametro Verbose e il parametro report ogni volta che si esegue Test-CsComputer. Il parametro Verbose fornirà un output leggermente più dettagliato sullo schermo durante l'esecuzione del cmdlet. Il parametro report consente di specificare un percorso file e un nome file per il file HTML generato da Test-CsComputer. Se non si include il parametro di report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

Il comando di esempio seguente esegue Test-CsComputer e salva l'output in un file denominato C:\\logs\\ComputerTest. html:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

A causa del numero di controlli di verifica eseguiti, Test-CsComputer non riporta un semplice **Sì, il** test è riuscito o **No, il test non è riuscito**. È invece necessario visualizzare il file HTML generato usando Internet Explorer per determinare l'esito positivo o negativo di ogni test.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsComputer potrebbe non riuscire:

  - Il computer di test potrebbe non essere abilitato per l'uso con Lync Server. Questo problema può verificarsi se i servizi di Lync Server o i ruoli del server nel computer sono stati modificati e non è stato eseguito il cmdlet Enable-CsComputer. Per risolvere il problema, eseguire il comando seguente:
    
        Enable-CsComputer

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

