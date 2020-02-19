---
title: 'Lync Server 2013: testing UCWA Conferencing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8855abbb92accbae66048905869f20958e128019
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Testing di UCWA Conferencing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-03_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsUcwaConference</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **test-CsUcwaConference** verifica che una coppia di utenti di test sia in grado di pianificare, partecipare e quindi condurre una conferenza online utilizzando Unified Communications Web API (UCWA). A tale scopo, il cmdlet utilizza il servizio ticket web di Lync Server per autenticare i due utenti di test e registrarli con Lync Server. Il cmdlet avvia quindi una conferenza utilizzando le credenziali dell'Organizzatore e invita il partecipante a partecipare alla riunione. Dopo l'aggiunta della riunione, il cmdlet **test-CsUcwaConference** verifica che gli utenti possano eseguire operazioni come il messaggio istantaneo di Exchange e i pool di conduzione, quindi disconnette la conferenza e Annulla la registrazione dei due utenti di test. La conferenza pianificata verrà eliminata anche al termine del test.

È inoltre possibile utilizzare il cmdlet **test-CsUcwaConference** per determinare se gli utenti anonimi possono partecipare a conferenze online.

Si noti che il cmdlet **test-CsUcwaConference** non deve essere eseguito su un pool di Microsoft Lync Server 2010, a meno che non sia stato installato UCWA in quel pool. Se UCWA non è stato installato, la chiamata al cmdlet **test-CsUcwaConference** avrà esito negativo.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il comando riportato nell'esempio 1 consente di verificare che una coppia di utenti di test sia in grado di partecipare a una conferenza di UCWA nel pool atl-cs-001.litwareinc.com. Si noti che questo comando avrà esito negativo se non è stata predefinita una coppia di utenti di test di configurazione del monitoraggio dell'integrità per atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di\\utenti (litwareinc\\Pilar e litwareinc kenmyer) di partecipare a una conferenza di UCWA. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet Get-Credential per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credentials risultante viene quindi memorizzato in una variabile denominata $cred 1. Il secondo comando effettua la stessa operazione, questa volta restituendo un oggetto credenziali per l'account Ken Myer.

Con i due oggetti Credential disponibili, il terzo comando nell'esempio determina se i due utenti possono partecipare a una conferenza di UCWA. Per eseguire questa attività, viene chiamato il cmdlet **test-CsUcwaConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrazione); OrganizerSipAddress (l'indirizzo SIP per l'organizzatore della riunione); OrganizerCredential (oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ParticipantSipAddress (l'indirizzo SIP per l'altro utente di test); e ParticipantCredential (l'oggetto interfaccia della riga di comando di Windows PowerShell contenente le credenziali per l'altro utente).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se le conferenze sono configurate correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

FQDN di destinazione: atl-cs-001.litwareinc.com

URI di destinazione: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Risultato: esito positivo

Latenza: 00:00:14.9862716

Messaggio di errore:

Diagnosi

Se gli utenti specificati non possono utilizzare i servizi di conferenza, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo

nome di dominio (FQDN). Utilizzo del numero di porta di registrazione predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: non è stato assegnato un utente di test

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Verificare la configurazione dell'utente di test.

At line: 1 char: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. Rtc. Management. synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **test-CsUcwaConference** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - La possibilità di condurre una conferenza dipende dai criteri di conferenza assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsUcwaConference** , che è il "mittente"). Se all'organizzatore non è consentito includere attività di collaborazione nella propria riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsUcwaConference** avrà esito negativo.

  - Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

