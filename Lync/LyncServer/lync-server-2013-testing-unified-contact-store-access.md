---
title: "Lync Server 2013: verifica dell'accesso all'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5552c03ac18ddd373385674da03d872ce89eb585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503903"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Verifica dell'accesso all'archivio contatti unificato in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-05-15_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsUnifiedContactStore</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

L'archivio contatti unificato introdotto in Lync Server 2013 fornisce agli amministratori la possibilità di archiviare i contatti di un utente in Microsoft Exchange Server 2013 anziché in Lync Server. In questo modo l'utente può accedere allo stesso gruppo di contatti in Outlook Web Access oltre che a Lync 2013. In alternativa, è possibile continuare a archiviare i contatti in Lync Server. In tal caso, gli utenti dovranno gestire due gruppi di contatti distinti: uno per l'utilizzo con Outlook e Outlook Web Access e uno per l'utilizzo con Lync 2013.

È possibile determinare se i contatti di un utente sono stati spostati nell'archivio contatti unificato eseguendo il cmdlet **Test-CsUnifiedContactStore** . Il cmdlet **Test-CsUnifiedContactStore** prenderà l'account utente specificato, si connetterà all'archivio contatti unificato e tenterà di recuperare un contatto per l'utente. Se non è possibile recuperare i contatti, il comando avrà esito negativo insieme al messaggio "non sono stati ricevuti contatti per l'utente. Verificare che esistano contatti per l'utente".

Si noti che il cmdlet **Test-CsUnifiedContactStore** avrà esito negativo se l'utente ha eseguito correttamente la migrazione nell'archivio contatti unificato, ma non ha contatti nell'elenco contatti. L'utente specificato deve disporre di almeno un contatto per il completamento corretto del cmdlet **Test-CsUnifiedContactStore** .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

I comandi riportati nell'esempio seguente determinano se i contatti per l'utente litwareinc \\ kenmyer possono essere trovati nell'archivio contatti unificato. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell per l'utente litwareinc \\ kenmyer. Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **Test-CsUnifiedContactStore** possa eseguire il controllo.

Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc \\ kenmyer per determinare se i contatti possono essere trovati nell'archivio contatti unificato.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'accesso all'archivio contatti è configurato in modo corretto, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:14.9862716

Messaggio di errore:

Diagnosi

Se l'accesso all'archivio contatti non è configurato correttamente, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo

nome di dominio (FQDN). Utilizzo del numero di porta di registrazione predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

Di seguito sono riportate alcune ragioni comuni per cui **Test-CsUnifiedContactStore** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - La connessione all'archivio contatti unificato ha avuto esito negativo e non è stato possibile eseguire il tentativo di recupero di un contatto per l'utente. Potrebbero verificarsi problemi di connettività di rete.

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

