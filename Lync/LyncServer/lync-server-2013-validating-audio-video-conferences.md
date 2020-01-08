---
title: 'Lync Server 2013: convalida di conferenze audio/video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0e608f0c765c4dd552645320ec947c7e8a54ac4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Convalida di conferenze audio/video in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-05_


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
<td><p>Quotidiana</p></td>
</tr>
<tr class="odd">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsAVConference. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsAVConference verifica se due utenti di test possono partecipare a una conferenza audio/video (A/V). Quando il cmdlet viene eseguito, i due utenti hanno effettuato l'accesso al sistema. Dopo aver eseguito l'accesso, il primo utente crea una conferenza A/V e quindi attende che il secondo utente partecipi alla conferenza. Dopo un breve scambio di dati, la conferenza viene eliminata e i due test gli utenti vengono disconnessi.

Tieni presente che Test-CsAVConference non esegue una conferenza A/V effettiva tra i due utenti di test. Il cmdlet verifica invece che i due utenti possano eseguire tutte le connessioni necessarie per eseguire una conferenza di questo tipo.

Altri esempi per questo comando sono disponibili in [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsAVConference può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server. Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando chiamano Test-CsAVConference:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se gli utenti specificati possono completare correttamente una conferenza A/V, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:02.6841765

Errore

Diagnosi

Se gli utenti non riescono a completare la conferenza, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test non è riuscito perché almeno uno dei due account utente non è valido, perché l'account non esiste o perché l'account non è stato abilitato per Lync Server. È possibile verificare l'esistenza dei due account di test e se sono stati abilitati per Lync Server eseguendo un comando simile al seguente:

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Se Test-CsAVConference non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando il parametro Verbose è incluso Test-CsAVConference restituirà un account dettagliato di ogni azione provata quando ha verificato la possibilità per gli utenti specificati di partecipare a una conferenza AV. Supponiamo ad esempio che il test non riesca e che venga ricevuta la diagnosi seguente:

ErrorCode = 1008, source = accessproxy. litwareinc. com, Reason = non è possibile risolvere il record SRV DNS

Se Riesegui il test usando il parametro Verbose, le informazioni dettagliate restituite includeranno l'output simile al seguente:

VERBOse: è stata avviata l'attività "Register".

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-001.litwareinc.com

Indirizzo SIP utente = sip:davidlongmire@litwareinc.com

Porta registrar = 5061.

È selezionato il tipo di autenticazione "attendibile".

Attività "Registra" iniziata.

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-001.litwareinc.com

Indirizzo SIP utente = sip:kenmyer@litwareinc.com

Porta registrar = 5061.

È selezionato il tipo di autenticazione "attendibile".

Eccezione "l'endpoint non è stato in grado di eseguire la registrazione. Vedere il ErrorCode per un motivo specifico. si è verificato durante il flusso di lavoro

L'ultima riga di tale output indica che l'utente sip:kenmyer@litwareinc.com non è riuscito a eseguire la registrazione con Lync Server. Questo significa che devi verificare che l'indirizzo SIP sip:kenmyer@litwareinc.com sia valido e che l'utente associato sia abilitato per Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsAVConference potrebbe non riuscire:

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

