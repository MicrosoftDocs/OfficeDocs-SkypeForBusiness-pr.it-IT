---
title: 'Lync Server 2013: test della connessione utente alla messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72552f56041103e381291bf13ab13283a3c47ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Test della connessione utente alla messaggistica unificata di Exchange in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-01_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExUMConnectivity</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **test-CsExUMConnectivity** verifica che l'utente specificato sia in grado di connettersi al servizio di messaggistica unificata di Microsoft Exchange Server 2013. Si noti che questo cmdlet verifica solo che sia possibile effettuare una connessione al servizio. Il servizio non viene testato. Per verificare il servizio di messaggistica unificata (eseguendo un cmdlet di transazione sintetica che lascia un messaggio in segreteria telefonica nella cassetta postale di un utente), utilizzare il cmdlet Test-CsExUMVoiceMail.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Nell'esempio seguente viene verificata la connettività di messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com. Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com. Se necessario, il comando determinerà se il primo utente di test può connettersi alla messaggistica unificata. Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

I comandi riportati nell'esempio seguente testano la connettività di messaggistica unificata di Exchange per\\l'utente litwareinc kenmyer. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell\\per l'utente litwareinc kenmyer. Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **test-CsExUMConnectivity** possa eseguire il controllo.

Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se l'utente può connettersi alla messaggistica unificata di Exchange.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Il comando riportato nell'esempio seguente è una variante del comando appena mostrato. In questo caso, il parametro OutLoggerVariable è incluso per generare un registro dettagliato di ogni passaggio effettuato dal **test-CsExUMConnectivity** cmdletand l'esito positivo o negativo di ognuno di questi passaggi. A tale scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore del parametro ExumText; che determina l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest. Nel comando finale dell'esempio viene utilizzato il metodo ToXML () per convertire le informazioni del registro in formato XML. I dati XML vengono quindi scritti in un file denominato C:\\logs\\ExumTest. XML utilizzando il cmdlet out-file.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se l'utente specificato non è in grado di ricevere notifiche, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa

non ha risposto correttamente dopo un determinato periodo di tempo oppure

connessione stabilita non riuscita perché l'host connesso ha

non è stato possibile rispondere 10.188.116.96:5061

Eccezione interna: un tentativo di connessione non è riuscito perché il

la parte connessa non ha risposto correttamente dopo un periodo di

Data/ora o connessione stabilita non riuscita perché host connesso

non è riuscito a rispondere 10.188.116.96:5061

Diagnosi

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **test-CsExUMConnectivity** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - Questo comando avrà esito negativo se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.

  - Questo comando avrà esito negativo se il server di Exchange non è raggiungibile tramite la rete.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

