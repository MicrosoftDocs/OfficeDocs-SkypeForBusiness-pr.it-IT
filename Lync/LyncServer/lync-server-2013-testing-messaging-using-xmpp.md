---
title: 'Lync Server 2013: test di messaggistica tramite XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5a1840e344ee19114cca424822fa1df14028495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Test di messaggistica con XMPP in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsXmppIM</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il protocollo XMPP (Extensible Messaging and Presence Protocol) è un protocollo di comunicazione standard (basato su XML) usato per l'invio di messaggi tramite Internet. XMPP è stato originariamente chiamato Jabber ed è supportato da diverse applicazioni di messaggistica e comunicazione Internet, come Google Talk e la chat di Facebook. Il cmdlet **Test-CsXmppIM** verifica che un utente possa scambiare messaggi istantanei con un utente in una rete XMPP. Tieni presente che, per ottenere il successo di questo test, devi avere un indirizzo SIP valido per l'utente XMPP e che l'indirizzo SIP deve trovarsi in una rete configurata come partner XMPP consentito.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

L'esempio seguente verifica le funzionalità di messaggistica istantanea XMPP per il pool atl-cs-001.litwareinc.com. Questo comando funzionerà solo se gli utenti di test sono definiti per il pool atl-cs-001.litwareinc.com. Se necessario, il comando determinerà se il primo utente di test può inviare un messaggio istantaneo XMPP a un utente con l'indirizzo SIP adelaney@contoso.com.

Se gli utenti di test non sono definiti, il comando avrà esito negativo perché non conosce l'utente a cui eseguire l'accesso. Se non sono stati definiti utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'utente che deve essere usato dal comando durante il tentativo di accesso.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

I comandi mostrati nel prossimo esempio provano la possibilità di accedere a un utente\\specifico (litwareinc Pilar) per inviare un messaggio istantaneo XMPP all'utente adelaney@contoso.com. A questo scopo, il primo comando nell'esempio usa il cmdlet Get-Credential per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso litwareinc\\Pilar è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziale risultante viene quindi archiviato in una variabile denominata $cred 1.

Il secondo comando controlla quindi se l'utente può accedere al pool atl-cs-001.litwareinc.com e inviare il messaggio istantaneo XMPP. Per eseguire questa attività, viene chiamato il cmdlet **test-CsXmppIm** , insieme a quattro parametri: TargetFqdn (il nome di dominio completo del pool di registrar); Receiver (l'indirizzo SIP dell'utente a cui viene indirizzato il messaggio); UserCredential (l'oggetto Windows PowerShell che contiene le credenziali utente di Pilar Ackerman); e UserSipAddress (l'indirizzo SIP che corrisponde alle credenziali utente fornite).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se la messaggistica istantanea XMPP è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:02.5361946

Messaggio di errore:

Diagnosi

Se gli utenti specificati non possono usare la messaggistica istantanea XMPP, il risultato verrà visualizzato come **errore**e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo

nome di dominio (FQDN). Uso del numero di porta registrar predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

Ecco alcuni motivi comuni per cui **Test-CsXmppIM** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - Questo comando non riuscirà se la configurazione del gateway XMPP non è stata configurata correttamente o non è stata ancora distribuita.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

