---
title: 'Lync Server 2013: testing delle chiamate audio/video peer-to-peer'
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
ms.openlocfilehash: 462442b7afea193866dc96aaf57085d780f43a39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Test delle chiamate audio/video peer-to-peer in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsP2PAV. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Test-CsP2PAV viene utilizzato per determinare se una coppia di utenti di test è in grado di partecipare a una conversazione a/V peer-to-peer. Per testare questo scenario, il cmdlet inizia dalla registrazione dei due utenti a Lync Server. Presupponendo che i due accessi abbiano esito positivo, il primo utente invita quindi il secondo utente a partecipare a una chiamata A/V. Dopo che il secondo utente ha accettato la chiamata, viene testata la connessione tra i due utenti e quindi la chiamata viene terminata e gli utenti di test vengono disconnessi dal sistema.

Test-CsP2PAV non esegue effettivamente una chiamata A/V. Le informazioni multimediali non vengono scambiate tra gli utenti di test. Al contrario, il cmdlet verifica solo che è possibile effettuare le connessioni appropriate e che i due utenti possono eseguire tale chiamata.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsP2PAV può essere eseguito utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Lync Server (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsP2PAV, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se i due utenti di test possono completare una chiamata A/V peer-to-peer, verrà visualizzato un output simile al seguente con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se gli utenti di test non sono in grado di completare la chiamata, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 480, temporaneamente non disponibile

Diagnosi: ErrorCode = 15030, source = atl-cs-001. litwareinc. com, Reason = failed

per instradare a Exchange Server

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente dichiara che il test non ha avuto esito positivo perché il server di Microsoft Exchange non è stato contattato. Questo messaggio di errore indica in genere un problema relativo alla configurazione della messaggistica unificata di Exchange.

Se Test-CsP2PAV ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-verbose

Quando viene incluso il parametro Verbose, Test-CsP2PAV restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Si supponga, ad esempio, che il test non abbia avuto esito positivo con la diagnosi seguente:

ErrorCode = 6003, source = atl-cs-001. litwareinc. com, Reason = non supportato dalla richiesta di finestra di dialogo

Se si esegue nuovamente Test-CsP2PAV e si include il parametro Verbose, si otterrà un output simile al seguente:

VERBOse: attività di registrazione avviata.

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-011.litwareinc.com

Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com

Porta di registrazione = 5062.

Il tipo di autenticazione ' IWA ' è selezionato.

Eccezione ' l'endpoint non è stato in grado di registrare. Per motivi specifici, vedere ErrorCode. si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflows. STP2PAVWorkflow.

Anche se potrebbe non essere immediatamente evidente, se si esamina l'output con attenzione, si noterà che è stata specificata una porta di registrazione non corretta (porta 5062). A sua incirca, ciò ha causato l'esito negativo del test.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsP2PAV potrebbe non riuscire:

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

