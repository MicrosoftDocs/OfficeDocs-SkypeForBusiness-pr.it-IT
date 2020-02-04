---
title: 'Lync Server 2013: test della configurazione del database'
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Verifica della configurazione del database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-07-07_


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
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins e devono avere i privilegi di amministratore in SQL Server.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsDatabase</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsDatabase** verifica la connettività a uno o più database di Lync Server 2013. Quando viene eseguito, il cmdlet **Test-CsDatabase** legge la topologia di Lync Server, cerca di connettersi a database rilevanti e quindi riporta l'esito positivo o negativo di ogni tentativo. Se è possibile effettuare una connessione, il cmdlet riporta anche le informazioni relative al nome del database, alle informazioni sulla versione di SQL Server e alla posizione dei database mirror installati.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il comando mostrato nell'esempio 1 verifica la configurazione del database di gestione centrale.

    Test-CsDatabase -CentralManagementDatabase

L'esempio 2 verifica tutti i database di Lync Server installati nel computer atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

Nell'esempio 3 la verifica viene eseguita solo per il database di archiviazione installato nel computer atl-sql-001.litwareinc.com. Tieni presente che il parametro SQLINSTANCENAME è incluso per specificare l'istanza di SQL Server (ARCHINST) in cui si trova il database di archiviazione.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

Il comando mostrato nell'esempio 4 Verifica i database installati nel computer locale.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se la connettività del database è configurata correttamente, si riceverà un output simile al seguente, con la proprietà succeed contrassegnata come **true**:

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

Origine dati

SqlServerVersion

ExpectedVersion : 10.13.2

InstalledVersion :

Successo: vero

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: LIS

Origine dati

SqlServerVersion

ExpectedVersion: 3.1.1

InstalledVersion :

Successo: vero

Se il database è configurato correttamente ma ancora disponibile, il campo successo verrà visualizzato come **falso**e verranno forniti avvisi e informazioni aggiuntive:

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

Origine dati

SqlServerVersion

ExpectedVersion : 10.13.2

InstalledVersion :

Operazione riuscita: false

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: LIS

Origine dati

SqlServerVersion

ExpectedVersion: 3.1.1

InstalledVersion :

Operazione riuscita: false

AVVISO: Test-CsDatabase ha rilevato errori. Consultare il file di log per un

analisi dettagliata e per assicurarsi che tutti gli errori (2) e gli avvisi (0) siano risolti

prima di continuare.

AVVISO: i risultati dettagliati possono essere trovati in

"C:\\utenti\\che\\testano\\AppData\\\\locale\\Temp 2 Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **Test-CsDatabase** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - Questo comando non riuscirà se il database non è configurato correttamente o non è stato ancora distribuito.

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

