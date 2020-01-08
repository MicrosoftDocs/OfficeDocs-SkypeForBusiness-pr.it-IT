---
title: 'Lync Server 2013: test della condivisione in conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Test della condivisione in conferenze in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsDataConference</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

In Lync Server 2013 una conferenza dati è una conferenza in cui vengono usate attività di collaborazione come la lavagna o le annotazioni. Il cmdlet **test-CsDataConference** consente di verificare che una coppia di utenti sia in grado di partecipare a una conferenza dati.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il comando mostrato nell'esempio 1 Verifica che una conferenza dati possa essere eseguita nel pool atl-cs-001.litwareinc.com. Questo comando presuppone che sia stata configurata una coppia di utenti di test per il pool specificato. Se non esistono utenti di test di questo tipo, il comando avrà esito negativo.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di\\utenti (litwareinc\\Pilar e litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di eseguire una conferenza dati. A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziale risultante viene quindi archiviato in una variabile denominata $cred 1. Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.

Con gli oggetti credenziale in mano, il terzo comando determina se questi due utenti possono accedere a Lync Server 2013 e condurre una conferenza dati. Per eseguire questa attività, viene chiamato il cmdlet **test-CsDataConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (l'oggetto Windows PowerShell che contiene le credenziali per l'altro utente di test).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se i servizi di conferenza dati sono configurati correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se gli utenti specificati non possono usare la condivisione dei dati, il risultato verrà visualizzato come **errore**e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa

non ha risposto correttamente dopo un periodo di tempo o

connessione stabilita non riuscita perché l'host connesso ha

Impossibile rispondere \[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061

Eccezione interna: tentativo di connessione non riuscito perché il

la parte connessa non ha risposto correttamente dopo un periodo di

l'ora o la connessione stabilita non è riuscita perché l'host connesso

non è riuscito a rispondere

\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061

Diagnosi

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **test-CsDataConference** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - La possibilità di eseguire una conferenza dati dipende dai criteri di conferenza assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsDataConference** , ovvero il "mittente"). Se l'organizzatore non è autorizzato ad includere attività di collaborazione nella riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsDataConference** non riuscirà.

  - Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

