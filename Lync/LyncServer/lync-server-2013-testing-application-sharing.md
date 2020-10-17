---
title: 'Lync Server 2013: verifica della condivisione di applicazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11130c1882fd6d12784cf6c25559a4249453f5d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530533"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a>Verifica della condivisione di applicazioni in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsASConference. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsASConference** verifica che una coppia di utenti di test sia in grado di partecipare a una conferenza online che include la condivisione di applicazioni. A tale scopo, il cmdlet registra i due utenti con Lync Server 2013 e quindi utilizza uno degli account utente per creare una nuova conferenza che includa la condivisione delle applicazioni. Il cmdlet verifica quindi che il secondo utente sia in grado di partecipare alla conferenza.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il comando riportato nell'esempio 1 verifica che sia possibile tenere una conferenza di condivisione applicazioni nel pool atl-cs-001.litwareinc.com. Nel comando si presuppone che sia stata configurata una coppia di utenti di test per il pool specificato. Se non esistono utenti di test, il comando avrà esito negativo.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

Nell'esempio 2 viene verificato che il servizio Join Launcher possa partecipare a una conferenza di condivisione applicazioni nel pool atl-cs-001.litwareinc.com. Questo comando verifica solo il servizio. Non è necessario alcun dispositivo mobile per eseguire il comando.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di utenti (litwareinc \\ Pilar e litwareinc \\ kenmyer) di accedere a Lync Server 2013 e quindi di condurre una conferenza di condivisione di applicazioni. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet Get-Credential per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso, litwareinc \\ Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Pilar Ackerman. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1. Il secondo comando effettua la stessa operazione, questa volta restituendo un oggetto credenziali per l'account Ken Myer.

Con gli oggetti Credential disponibili, il terzo comando determina se i due utenti possono accedere o meno a Lync Server 2013 e condurre una conferenza di condivisione di applicazioni. Per eseguire questa attività, viene chiamato il cmdlet **Test-CsASConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrazione); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (oggetto Windows PowerShell contenente le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (oggetto Windows PowerShell contenente le credenziali per l'altro utente di test).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se la condivisione di applicazioni è configurata correttamente, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:01

Messaggio di errore:

Diagnosi

Se gli utenti specificati non sono in grado di condividere le applicazioni, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

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

Ad esempio, l'output precedente include la nota "la parte connessa non ha risposto correttamente" che indica in genere un problema con il server perimetrale.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **Test-CsASConference** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - Questo comando avrà esito negativo se agli utenti di test sono stati assegnati criteri di conferenza che impediscono l'utilizzo della condivisione delle applicazioni.

  - Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

