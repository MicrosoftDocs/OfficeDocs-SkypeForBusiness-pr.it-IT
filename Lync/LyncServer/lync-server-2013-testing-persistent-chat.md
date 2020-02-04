---
title: 'Lync Server 2013: test della chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Test della chat persistente in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsPersistentChatMessage</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **test-CsPersistentChatMessage** verifica che una coppia di utenti di test possa scambiare messaggi usando il servizio di chat persistente. A questo scopo, il cmdlet registra i due utenti in Lync Server 2013, connette gli utenti a una chat room persistente, scambia una coppia di messaggi, quindi chiude la chat room e disconnette i due utenti. Tieni presente che le chiamate a questo cmdlet avranno esito negativo se non hai creato nessuna chat room o se ai due account utente di test non viene assegnato un criterio di chat persistente che consente di accedere al servizio di chat persistente.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

I comandi mostrati nell'esempio seguente consentono di verificare la capacità di una coppia di utenti\\(litwareinc Pilar\\e litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di scambiare i messaggi usando il servizio di chat persistente. A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziali risultante viene quindi archiviato in una variabile denominata $cred 1. Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.

Con gli oggetti credenziale disponibili, il terzo comando determina se questi due utenti possono accedere a Lync Server 2013 e scambiare messaggi usando la chat persistente. Per eseguire questa attività, il cmdlet **test-CsPersistentChatMessage** viene chiamato usando i parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (l'oggetto Windows PowerShell che contiene le credenziali per l'altro utente di test).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato ha un criterio di posizione valido, riceverai un output simile al seguente, con la proprietà Result contrassegnata come **riuscita**:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se gli utenti specificati non possono scambiare messaggi usando il servizio chat persistente, il risultato verrà visualizzato come **errore**e verranno registrate altre informazioni nelle proprietà errore e diagnosi:

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

Ecco alcuni motivi comuni per cui **test-CsPersistentChatMessage** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Gli account di test necessari potrebbero non esistere o essere stati creati correttamente.

  - Potrebbe essersi verificato un problema di rete che causa un ritardo imprevisto che ha superato il test.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

