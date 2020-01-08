---
title: 'Lync Server 2013: testing di conferenza UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Test di conferenza UCWA in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsUcwaConference</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **test-CsUcwaConference** verifica che una coppia di utenti di test possa pianificare, partecipare e quindi eseguire una conferenza online con l'API Web Unified Communications (UCWA). A questo scopo, il cmdlet usa il servizio ticket web di Lync Server per autenticare i due utenti di test e registrarli con Lync Server. Il cmdlet avvia quindi una conferenza con le credenziali dell'Organizzatore e invita il partecipante a partecipare alla riunione. Dopo l'aggiunta della riunione, il cmdlet **test-CsUcwaConference** verifica che gli utenti possano eseguire operazioni come il messaggio istantaneo di Exchange e i pool di conduzione, quindi disconnette la conferenza e Annulla la registrazione dei due utenti di test. La conferenza pianificata verrà eliminata anche al termine del test.

Il cmdlet **test-CsUcwaConference** può essere usato anche per determinare se gli utenti anonimi possono partecipare a conferenze online.

Tieni presente che il cmdlet **test-CsUcwaConference** non deve essere eseguito in un pool di Microsoft Lync Server 2010, a meno che non sia stato installato UCWA nel pool. Se UCWA non è stato installato, la chiamata al cmdlet **test-CsUcwaConference** non riuscirà.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il comando mostrato nell'esempio 1 Verifica che una coppia di utenti di test possa partecipare a una conferenza UCWA nel pool atl-cs-001.litwareinc.com. Tieni presente che questo comando non riesce se non hai predefinito una coppia di utenti di test di configurazione per il monitoraggio dell'integrità per atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

I comandi mostrati nell'esempio 2 verificano la possibilità di una coppia di utenti\\(litwareinc Pilar\\e litwareinc kenmyer) di partecipare a una conferenza di UCWA. A questo scopo, il primo comando nell'esempio usa il cmdlet Get-Credential per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman. Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziali risultante viene quindi archiviato in una variabile denominata $cred 1. Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.

Con i due oggetti credenziale disponibili, il terzo comando nell'esempio determina se i due utenti possono partecipare a una conferenza di UCWA. Per eseguire questa attività, viene chiamato il cmdlet **test-CsUcwaConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); OrganizerSipAddress (l'indirizzo SIP per l'organizzatore della riunione); OrganizerCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ParticipantSipAddress (l'indirizzo SIP per l'altro utente di test); e ParticipantCredential (l'oggetto interfaccia della riga di comando di Windows PowerShell che contiene le credenziali per l'altro utente).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se i servizi di conferenza sono configurati correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Risultato: successo

Latenza: 00:00:14.9862716

Messaggio di errore:

Diagnosi

Se gli utenti specificati non possono usare i servizi di conferenza, il risultato verrà visualizzato come **errore**e le informazioni aggiuntive verranno registrate nelle proprietà errore e diagnosi:

AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo

nome di dominio (FQDN). Uso del numero di porta registrar predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: non è stato assegnato un utente di test

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Verificare la configurazione degli utenti di test.

At line: 1 char: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. Rtc. Management. synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **test-CsUcwaConference** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - La possibilità di eseguire una conferenza dipende dai criteri di conferenza assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsUcwaConference** , ovvero il "mittente"). Se l'organizzatore non è autorizzato ad includere attività di collaborazione nella riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsUcwaConference** non riuscirà.

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

