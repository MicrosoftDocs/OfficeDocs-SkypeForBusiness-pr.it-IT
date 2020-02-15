---
title: 'Lync Server 2013: testing di servizi di audioconferenza di terze parti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2897e085ea35e17d65719874ecf103ed7f1475d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Verifica di servizi di audioconferenza di terze parti in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet test-CsAudioConferencingProvider. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Un provider di servizi di audioconferenza è una società di terze parti che fornisce servizi di conferenza alle organizzazioni. Tra le altre cose, i provider di servizi di audioconferenza consentono agli utenti che si trovano fuori sede, e non sono connessi alla rete aziendale o Internet, di partecipare alla parte audio di una conferenza o di una riunione. Tali provider offrono spesso servizi di qualità elevata quali traduzione immediata, trascrizione e assistenza diretta di un operatore durante la conferenza.

Il cmdlet **test-CsAudioConferencingProvider** viene utilizzato per verificare che un utente sia in grado di effettuare una connessione al proprio provider di servizi di audioconferenza. Si noti che questo cmdlet può essere eseguito in uno dei due modi. Molti amministratori utilizzeranno i cmdlet CsHealthMonitoringConfiguration per configurare utenti di test per ciascuno dei propri pool di registrazione. Questi utenti di test sono costituiti da una coppia di account utente preconfigurati per l'utilizzo con le transazioni sintetiche. In genere si tratta di account di prova e non di account che appartengono a utenti effettivi. Se gli utenti di test sono configurati per un pool, gli amministratori possono eseguire il cmdlet **test-CsAudioConferencingProvider** su tale pool senza dover specificare l'identità (e fornire le credenziali per) dell'account utente coinvolto nel test.

In alternativa, gli amministratori possono eseguire il cmdlet **test-CsAudioConferencingProvider** utilizzando un account utente effettivo. In questo caso, è necessario specificare nome di accesso e password per l'account.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Nell'esempio 1 viene verificato se un utente di prova definito per il pool atl-cs-001.litwareinc.com è in grado di connettersi al proprio provider di servizi di audioconferenza. Questo comando richiede che almeno un utente di test sia definito per il pool. Se non sono stati definiti utenti di test per atl-cs-001.litwareinc.com, il comando avrà esito negativo. Ciò è dovuto al fatto che il cmdlet **test-CsAudioConferencingProvider** non è in grado di riconoscere l'utente da utilizzare nel test. Se non sono stati definiti utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'account utente da utilizzare per la verifica della connessione a un provider di servizi di audioconferenza.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

I comandi mostrati nell'esempio 2 consentono di verificare la possibilità di un utente\\specifico (litwareinc kenmyer) di connettersi al proprio provider di servizi di audioconferenza. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet Get-Credential per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Ken di Microsoft. Poiché il nome di accesso litwareinc\\kenmyer è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Ken. L'oggetto credentials risultante viene archiviato in una variabile denominata $credential.

Nel secondo comando viene quindi verificato se l'utente può connettersi al proprio provider di servizi di audioconferenza. Per eseguire questa attività, viene chiamato il cmdlet test-CsAudioConferencingProvider, insieme a tre parametri: TargetFqdn (il nome di dominio completo del pool di registrazione). UserCredential (l'oggetto Windows PowerShell contenente le credenziali utente di Ken di Microsoft); e UserSipAddress (l'indirizzo SIP corrispondente alle credenziali utente fornite).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se il provider di servizi di audioconferenza è configurato correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

FQDN di destinazione: atl-sql-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

FQDN di destinazione: atl-sql-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa

non ha risposto correttamente dopo un determinato periodo di tempo oppure

connessione stabilita non riuscita perché l'host connesso ha

Impossibile rispondere \[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061

Eccezione interna: un tentativo di connessione non è riuscito perché il

la parte connessa non ha risposto correttamente dopo un periodo di

Data/ora o connessione stabilita non riuscita perché host connesso

non è stato in grado di rispondere

\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061

Diagnosi

Ad esempio, l'output precedente include la nota "la parte connessa non ha risposto correttamente" che indica in genere un problema con il server perimetrale.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **test-CsAudioConferencingProvider** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Come illustrato nell'esempio precedente, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - Si noti che il test avrà esito negativo se all'utente utilizzato dal cmdlet **test-CsAudioConferencingProvider** non è stato assegnato un provider di servizi di audioconferenza.

  - Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

