---
title: 'Lync Server 2013: verifica della configurazione del database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d57659c93aa42392f5408721157df1d14b56b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504103"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a>Verifica della configurazione del database in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-07_


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
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins ed è necessario disporre di privilegi di amministratore su SQL Server.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsDatabase</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsDatabase** consente di verificare la connettività a uno o più database di Lync Server 2013. Quando viene eseguito, il cmdlet **Test-CsDatabase** legge la topologia di Lync Server, tenta di connettersi a database rilevanti e quindi segnala nuovamente l'esito positivo o negativo di ogni tentativo. Se è possibile effettuare una connessione, il cmdlet riporterà inoltre informazioni quali il nome del database, la versione di SQL Server e il percorso di eventuali database mirror installati.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il comando riportato nell'esempio 1 verifica la configurazione del database di gestione centrale.

    Test-CsDatabase -CentralManagementDatabase

Nell'esempio 2 vengono verificati tutti i database di Lync Server installati nel computer atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

Nell'esempio 3 la verifica viene eseguita solo per il database di archiviazione installato nel computer atl-sql-001.litwareinc.com. Si noti che viene incluso il parametro SqlInstanceName per specificare l'istanza di SQL Server (Archinst) in cui si trova il database di archiviazione.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

Il comando riportato nell'esempio 4 verifica i database installati nel computer locale.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se la connettività del database è configurata correttamente, si riceverà un output simile al seguente, con la proprietà succeed contrassegnata come **true**:

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SqlServerVersion

ExpectedVersion : 10.13.2

InstalledVersion :

Esito positivo: true

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: LIS

DataSource

SqlServerVersion

ExpectedVersion: 3.1.1

InstalledVersion :

Esito positivo: true

Se il database è configurato correttamente, ma è ancora disponibile, il campo esito positivo verrà visualizzato come **falso**e verranno forniti avvisi e informazioni aggiuntive:

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SqlServerVersion

ExpectedVersion : 10.13.2

InstalledVersion :

Esito positivo: false

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: LIS

DataSource

SqlServerVersion

ExpectedVersion: 3.1.1

InstalledVersion :

Esito positivo: false

AVVISO: Test-CsDatabase riscontrato un errore. Consultare il file di registro per un

analisi dettagliata e per assicurarsi che tutti gli errori (2) e gli avvisi (0) siano indirizzati

prima di continuare.

AVVISO: i risultati dettagliati sono disponibili all'indirizzo

"C: utenti che eseguono il \\ \\ testing \\ AppData \\ Local \\ temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **Test-CsDatabase** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - Questo comando avrà esito negativo se il database non è stato configurato correttamente o non è stato ancora distribuito.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

