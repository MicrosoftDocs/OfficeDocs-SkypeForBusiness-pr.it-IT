---
title: 'Lync Server 2013: convalidare le conferenze audio/video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0bfeef1abcf7b5859c365b7c64b4fcc84f49ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503703"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Convalidare le conferenze audio/video in Lync Server 2013

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Pianificazione della verifica</p></td>
<td><p>Giornaliero</p></td>
</tr>
<tr class="odd">
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsAVConference. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsAVConference verifica se due utenti di test possono partecipare a una conferenza audio/video (A/V). Quando viene eseguito il cmdlet, i due utenti vengono connessi al sistema. Dopo aver eseguito l'accesso con esito positivo, il primo utente crea una conferenza A/V e quindi attende che il secondo utente partecipi alla conferenza. Dopo un breve scambio di dati, la conferenza viene eliminata e i due utenti vengono disconnessi.

Si noti che Test-CsAVConference non esegue una conferenza audio/video effettiva tra i due utenti di test. Al contrario, il cmdlet verifica che i due utenti possano effettuare tutte le connessioni necessarie per condurre una conferenza.

Ulteriori esempi per questo comando sono disponibili in [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsAVConference utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. È quindi necessario includere gli oggetti Credentials e gli indirizzi SIP dei due account quando chiamano Test-CsAVConference:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se gli utenti specificati possono completare correttamente una conferenza audio/video, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:02.6841765

Errore

Diagnosi

Se gli utenti non riescono a completare la conferenza, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché almeno uno dei due account utente non era valido, perché l'account non esiste o perché l'account non è stato abilitato per Lync Server. È possibile verificare l'esistenza dei due account di test e se sono stati abilitati per Lync Server, eseguendo un comando simile al seguente:

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Se Test-CsAVConference ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose Test-CsAVConference restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità degli utenti specificati di partecipare a una conferenza AV. Ad esempio, si supponga che il test abbia esito negativo e che venga ricevuta la seguente diagnosi:

ErrorCode = 1008, source = accessproxy. litwareinc. com, Reason = non è in grado di risolvere il record DNS SRV

Se si esegue di nuovo il test utilizzando il parametro Verbose, le informazioni dettagliate restituite includono un output simile al seguente:

VERBOse: attività di registrazione avviata.

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-001.litwareinc.com

Indirizzo SIP dell'utente = sip:davidlongmire@litwareinc.com

Porta di registrazione = 5061.

Il tipo di autenticazione ' attendibile ' è selezionato.

Attività' Register ' iniziata.

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-001.litwareinc.com

Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com

Porta di registrazione = 5061.

Il tipo di autenticazione ' attendibile ' è selezionato.

Eccezione ' l'endpoint non è stato in grado di registrare. Per motivi specifici, vedere ErrorCode. si è verificato durante il flusso di lavoro

L'ultima riga di tale output indica che l'utente sip:kenmyer@litwareinc.com non è stato in grado di eseguire la registrazione con Lync Server. Questo significa che è necessario verificare che l'indirizzo SIP sip:kenmyer@litwareinc.com sia valido e che l'utente associato sia abilitato per Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsAVConference potrebbero non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
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

