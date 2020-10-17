---
title: 'Lync Server 2013: verifica della condivisione nelle conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36cf05d0d3d5cce13a100d23cb541eb5aa186ef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530493"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Verifica della condivisione nelle conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsDataConference</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

In Lync Server 2013, una conferenza dati è una conferenza in cui vengono utilizzate attività di collaborazione come la lavagna o le annotazioni. Il cmdlet **test-CsDataConference** consente di verificare che una coppia di utenti sia in grado di partecipare a una conferenza dati.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il comando riportato nell'esempio 1 verifica che sia possibile tenere una conferenza dati nel pool atl-cs-001.litwareinc.com. Nel comando si presuppone che sia stata configurata una coppia di utenti di test per il pool specificato. Se non esistono utenti di test, il comando avrà esito negativo.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di utenti (litwareinc \\ Pilar e litwareinc \\ kenmyer) di accedere a Lync Server 2013 e quindi di condurre una conferenza dati. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso, litwareinc \\ Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Pilar Ackerman. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1. Il secondo comando effettua la stessa operazione, questa volta restituendo un oggetto credenziali per l'account Ken Myer.

Con gli oggetti Credential disponibili, il terzo comando determina se i due utenti possono accedere o meno a Lync Server 2013 e condurre una conferenza dati. Per eseguire questa attività, viene chiamato il cmdlet **test-CsDataConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrazione); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (oggetto Windows PowerShell contenente le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (oggetto Windows PowerShell contenente le credenziali per l'altro utente di test).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se i servizi di conferenza dati sono configurati correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se gli utenti specificati non possono utilizzare la condivisione dei dati, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa

non ha risposto correttamente dopo un determinato periodo di tempo oppure

connessione stabilita non riuscita perché l'host connesso ha

Impossibile rispondere \[ 2001:4898: E8: f39e: 5c9a: AD83:81b3:9944 \] : 5061

Eccezione interna: un tentativo di connessione non è riuscito perché il

la parte connessa non ha risposto correttamente dopo un periodo di

Data/ora o connessione stabilita non riuscita perché host connesso

non è stato in grado di rispondere

\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944: \] 5061

Diagnosi

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **test-CsDataConference** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - La possibilità di condurre una conferenza dati dipende dai criteri di conferenza che sono stati assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsDataConference** , che è il "mittente"). Se all'organizzatore non è consentito includere attività di collaborazione nella propria riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsDataConference** avrà esito negativo.

  - Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

