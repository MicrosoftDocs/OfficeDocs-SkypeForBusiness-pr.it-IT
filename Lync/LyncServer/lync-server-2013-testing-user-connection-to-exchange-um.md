---
title: 'Lync Server 2013: test della connessione utente alla messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc54577e94f7679e833f06a4a5de060aaf761a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Test della connessione utente alla messaggistica unificata di Exchange in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-11-01_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsExUMConnectivity</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **test-CsExUMConnectivity** verifica che l'utente specificato possa connettersi al servizio di messaggistica unificata di Microsoft Exchange Server 2013. Tieni presente che questo cmdlet verifica che sia possibile effettuare una connessione al servizio. Il servizio non viene testato. Per testare il servizio di messaggistica unificata eseguendo un cmdlet di transazione sintetica che lascia effettivamente un messaggio di segreteria telefonica nella cassetta postale di un utente, usare il cmdlet test-CsExUMVoiceMail.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

L'esempio seguente verifica la connettività di messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com. Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com. Se necessario, il comando determinerà se il primo utente di test può connettersi alla messaggistica unificata. Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

I comandi illustrati nell'esempio seguente verificano la connettività di messaggistica unificata di Exchange\\per l'utente litwareinc kenmyer. A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziali dell'interfaccia della riga di comando di Windows PowerShell per l'\\utente litwareinc kenmyer. Tieni presente che devi specificare la password per questo account per creare un oggetto credenziali valido e per verificare che il cmdlet **test-CsExUMConnectivity** possa eseguire il controllo.

Il secondo comando nell'esempio usa l'oggetto credentials fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se l'utente può connettersi alla messaggistica unificata di Exchange.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Il comando mostrato nell'esempio seguente è una variante del comando appena visualizzato. In questo caso, il parametro OutLoggerVariable è incluso per generare un log dettagliato di ogni passaggio eseguito dal **test-CsExUMConnectivity** cmdletand l'esito positivo o negativo di ognuno di questi passaggi. A questo scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore di parametro ExumText; che causa l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest. Nel comando finale dell'esempio viene usato il metodo ToXML () per convertire le informazioni del log in formato XML. I dati XML vengono quindi scritti in un file denominato C:\\logs\\ExumTest. XML usando il cmdlet out-file.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita**:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se l'utente specificato non può ricevere notifiche, il risultato verrà visualizzato come **errore**e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa

non ha risposto correttamente dopo un periodo di tempo o

connessione stabilita non riuscita perché l'host connesso ha

Impossibile rispondere 10.188.116.96:5061

Eccezione interna: tentativo di connessione non riuscito perché il

la parte connessa non ha risposto correttamente dopo un periodo di

l'ora o la connessione stabilita non è riuscita perché l'host connesso

non è riuscito a rispondere 10.188.116.96:5061

Diagnosi

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **test-CsExUMConnectivity** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - Questo comando non riuscirà se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.

  - Questo comando non riuscirà se il server di Exchange non è raggiungibile tramite la rete.

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

