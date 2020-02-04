---
title: 'Lync Server 2013: test della chiamata audio/video peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Test della chiamata audio/video peer-to-peer in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsP2PAV. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Test-CsP2PAV viene usato per determinare se una coppia di utenti di test può partecipare a una conversazione a/V peer-to-peer. Per verificare questo scenario, il cmdlet si avvia effettuando la registrazione dei due utenti in Lync Server. Supponendo che i due accessi abbiano successo, il primo utente invita quindi il secondo utente a partecipare a una chiamata A/V. Il secondo utente accetta la chiamata, la connessione tra i due utenti viene testata e la chiamata viene terminata e gli utenti di test vengono disconnessi dal sistema.

Test-CsP2PAV non esegue effettivamente una chiamata A/V. Le informazioni multimediali non vengono scambiate tra gli utenti di test. Al contrario, il cmdlet verifica semplicemente che le connessioni appropriate possano essere effettuate e che i due utenti possano eseguire tale chiamata.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsP2PAV può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server. Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti credenziali di Lync Server (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsP2PAV:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se i due utenti di test possono completare una chiamata A/V peer-to-peer, riceverai un output simile a quello con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se gli utenti di test non riescono a completare la chiamata, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 480, temporaneamente non disponibile

Diagnosi: ErrorCode = 15030, source = atl-cs-001. litwareinc. com, Reason = failed

per instradare a Exchange Server

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test non è riuscito perché non è stato possibile contattare il server di Microsoft Exchange. Questo messaggio di errore indica in genere un problema la configurazione della messaggistica unificata di Exchange.

Se Test-CsP2PAV non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-verbose

Quando viene incluso il parametro Verbose, Test-CsP2PAV restituirà un account dettagliato di ogni azione provata mentre controlla la capacità dell'utente specificato di accedere a Lync Server. Supponiamo ad esempio che il test non sia riuscito con la diagnosi seguente:

ErrorCode = 6003, source = atl-cs-001. litwareinc. com, Reason = non supportato dalla richiesta di finestra di dialogo

Se si riesegue Test-CsP2PAV e si include il parametro Verbose, si otterrà un output simile al seguente:

VERBOse: è stata avviata l'attività "Register".

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-011.litwareinc.com

Indirizzo SIP utente = sip:kenmyer@litwareinc.com

Porta registrar = 5062.

Viene selezionato il tipo di autenticazione "IWA".

Eccezione "l'endpoint non è stato in grado di eseguire la registrazione. Vedere il ErrorCode per un motivo specifico. si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflows. STP2PAVWorkflow.

Anche se potrebbe non essere immediatamente evidente, se esamini attentamente l'output vedrai che è stata specificata una porta di registrazione non corretta (porta 5062). A sua volta, il test ha causato un errore.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsP2PAV potrebbe non riuscire:

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

