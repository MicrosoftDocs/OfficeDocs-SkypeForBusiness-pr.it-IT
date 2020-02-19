---
title: 'Lync Server 2013: verifica della capacità di un utente di accedere a Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71629cb844b8f65ab6f54c0d604fad0d152705d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Verifica della capacità di un utente di accedere a Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsRegistration consente di verificare che gli utenti dell'organizzazione possano accedere a Lync Server. Quando si esegue Test-CsRegistration, il cmdlet tenta di eseguire l'accesso a un utente di test a Lync Server e quindi, se ha esito positivo, disconnette l'utente di test dal sistema. Tutta la procedura viene eseguita senza alcuna interazione da parte degli utenti e senza che questi vengano coinvolti. Si supponga, ad esempio, che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che dispone di un account Lync Server reale. In questo caso, il test verrà eseguito senza coinvolgere il vero Ken Myer. Quando l'account di test di Ken è disconnesso dal sistema, Ken è la persona che continuerà a essere connessa.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsRegistration utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo del pool di registrazione di Lync Server in fase di test. Ad esempio:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato può accedere a (e quindi disconnettersi da) Lync Server, verrà visualizzato un output simile al seguente con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 1003, source = atl-cs-001. litwareinc. com, Reason = utente

non esiste

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato trovato. È possibile determinare se un indirizzo SIP è valido (e se l'utente assegnato l'indirizzo SIP è abilitato per Lync Server) eseguendo il comando seguente:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Se Test-CsRegistration ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsRegistration restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio:

VERBOse: attività di registrazione avviata.

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-011.litwareinc.com

Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com

Porta di registrazione = 5061.

Il tipo di autenticazione ' attendibile ' è selezionato.

Eccezione ' l'endpoint non è in grado di effettuare la registrazione. Per un motivo specifico si è verificato l'errore durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflow. STRegistrerWorkflow.

Stack di chiamate di eccezione: in Microsoft. Rtc. signaling. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsRegistration potrebbe non riuscire:

  - È stato specificato un account utente non corretto. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - È stato specificato un pool di registrazione non corretto. È possibile restituire i nomi FQDN dei pool di registrazione utilizzando il comando seguente:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Il pool di registrazione non è attualmente disponibile. Provare a eseguire il ping del pool per verificare se risponde:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

