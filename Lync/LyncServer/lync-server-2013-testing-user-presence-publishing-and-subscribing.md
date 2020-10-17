---
title: 'Lync Server 2013: verifica della pubblicazione e della sottoscrizione della presenza degli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335ad014595f855c1ccefab363f3cf34ad7c282b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503853"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Verifica della pubblicazione e della sottoscrizione della presenza degli utenti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-05_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsPresence. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Test-CsPresence viene utilizzato per determinare se una coppia di utenti di test può accedere a Lync Server e quindi scambiare informazioni sulla presenza. Per ottenere questo risultato il cmdlet deve far accedere i due utenti al sistema. Se entrambi gli accessi riescono il primo utente di prova chiede di ricevere le informazioni sulla presenza dal secondo utente. Il secondo utente pubblica queste informazioni e Test-CsPresence verifica che le informazioni vengano correttamente trasmesse al primo utente. Dopo lo scambio di informazioni sulla presenza, i due utenti di test vengono quindi disconnessi da Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsPresence utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsPresence, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se gli utenti specificati possono scambiare informazioni sulla presenza, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.3280315

Errore

Diagnosi

Se i due utenti non sono in grado di scambiare informazioni sulla presenza, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché almeno uno dei due account utente non è valido: l'account non esiste o non è stato abilitato per Lync Server. È possibile verificare che gli account esistano e determinare se sono abilitati per Lync Server, eseguendo un comando simile al seguente:

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

Se Test-CsPresence ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPresence restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio:

Richiesta di registrazione hit against Unknown

Attività' Register ' completata in ' 0,0345791' secs.

Attività' SelfSubscribeActivity ' iniziata.

Attività' SelfSubscribeActivity ' completata in ' 0,0041174' secs.

Attività' SubscribePresence ' iniziata.

Attività' SubscribePresence ' completata in ' 0,0038764' secs.

Attività' PublishPresence ' iniziata.

La notifica di presenza di un'eccezione non viene ricevuta entro 25 secondi. si è verificato l'esecuzione del flusso di lavoro rovinato Microsoft. Rtc. SyntheticTransactions. Workflows. STPresenceWorkflow.

Il fatto che la notifica di presenza non sia stata ricevuta entro 25 secondi potrebbe indicare che i problemi di rete impediscono lo scambio di informazioni.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsPresence potrebbero non riuscire:

  - È stato specificato un account utente non corretto. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

