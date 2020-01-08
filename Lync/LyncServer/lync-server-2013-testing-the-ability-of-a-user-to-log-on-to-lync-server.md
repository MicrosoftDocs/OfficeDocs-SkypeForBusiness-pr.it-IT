---
title: 'Lync Server 2013: verifica della capacità di un utente di accedere a Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Verifica della capacità di un utente di accedere a Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsRegistration. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsRegistration consente di verificare che gli utenti dell'organizzazione possano accedere a Lync Server. Quando si esegue Test-CsRegistration, il cmdlet tenta di accedere a un utente di test a Lync Server e quindi, se riesce, disconnette l'utente di test dal sistema. Tutto questo avviene senza alcuna interazione con l'utente e senza influenzare gli utenti effettivi. Supponiamo ad esempio che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che ha un vero account di Lync Server. In questo caso, il test verrà condotto senza interruzioni per il vero Ken. Quando l'account di test di Ken si disconnette dal sistema, Ken si connette alla persona che rimarrà connesso.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsRegistration può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di registrazione di Lync Server testato. Ad esempio:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato può accedere a (e quindi disconnettersi da) Lync Server, si riceverà un output simile a quello con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non riesce ad accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 1003, source = atl-cs-001. litwareinc. com, Reason = l'utente non

non esiste

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test non è riuscito perché non è stato possibile trovare l'utente specificato. È possibile determinare se un indirizzo SIP è valido (e se l'utente ha assegnato l'indirizzo SIP abilitato per Lync Server) eseguendo questo comando:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Se Test-CsRegistration non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsRegistration restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio:

VERBOse: è stata avviata l'attività "Register".

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-011.litwareinc.com

Indirizzo SIP utente = sip:kenmyer@litwareinc.com

Porta registrar = 5061.

È selezionato il tipo di autenticazione "attendibile".

Eccezione ' l'endpoint non è in grado di eseguire la registrazione. Vedi l'errore per il motivo specifico che si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflow. STRegistrerWorkflow.

Stack di chiamate di eccezione: at Microsoft. Rtc. signaling. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsRegistration potrebbe non riuscire:

  - È stato specificato un account utente non corretto. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - È stato specificato un pool di registrar errato. Puoi restituire gli FQDN dei pool di registrar usando questo comando:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Il pool di registrazione non è attualmente disponibile. Provare a eseguire il ping del pool per verificare se risponde:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

