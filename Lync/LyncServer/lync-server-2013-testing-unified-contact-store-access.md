---
title: "Lync Server 2013: test dell'accesso all'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Test dell'accesso all'archivio contatti unificato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-05-15_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsUnifiedContactStore</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

L'archivio contatti unificato introdotto in Lync Server 2013 offre agli amministratori la possibilità di archiviare i contatti di un utente in Microsoft Exchange Server 2013 anziché in Lync Server. In questo modo l'utente deve accedere allo stesso set di contatti in Outlook Web Access oltre a Lync 2013. In alternativa, è possibile continuare a archiviare i contatti in Lync Server. In questo caso, gli utenti dovranno gestire due set distinti di contatti: uno da usare con Outlook e Outlook Web Access e uno da usare con Lync 2013.

È possibile determinare se i contatti di un utente sono stati spostati nell'archivio contatti unificato eseguendo il cmdlet **Test-CsUnifiedContactStore** . Il cmdlet **Test-CsUnifiedContactStore** prenderà l'account utente specificato, si collegherà all'archivio contatti unificato e tenterà di recuperare un contatto per l'utente. Se non è possibile recuperare contatti, il comando non riuscirà insieme al messaggio "non sono stati ricevuti contatti per l'utente. Verificare che i contatti siano presenti per l'utente. "

Si noti che il cmdlet **Test-CsUnifiedContactStore** non riesce se l'utente ha eseguito correttamente la migrazione nell'archivio contatti unificato, ma non ha contatti nell'elenco contatti. Per completare correttamente il cmdlet **Test-CsUnifiedContactStore** , l'utente specificato deve avere almeno un contatto.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

I comandi mostrati nell'esempio seguente determinano se i contatti per l'\\utente litwareinc kenmyer possono essere trovati nell'archivio contatti unificato. A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziali dell'interfaccia della riga di comando di Windows PowerShell per l'\\utente litwareinc kenmyer. Tieni presente che devi specificare la password per questo account per creare un oggetto credenziali valido e per verificare che il cmdlet **Test-CsUnifiedContactStore** possa eseguire il controllo.

Il secondo comando nell'esempio usa l'oggetto credentials fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se i contatti sono disponibili nell'archivio contatti unificato.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'accesso all'archivio contatti è configurato correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:14.9862716

Messaggio di errore:

Diagnosi

Se l'accesso all'archivio contatti non è configurato correttamente, il risultato verrà visualizzato come **errore**e verranno registrate altre informazioni nelle proprietà errore e diagnosi:

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

Ecco alcuni motivi comuni per cui **Test-CsUnifiedContactStore** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - Connettersi all'archivio contatti unificato non riuscito e il tentativo di recuperare un contatto per l'utente non è stato possibile. Potrebbero verificarsi problemi di connettività di rete.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

