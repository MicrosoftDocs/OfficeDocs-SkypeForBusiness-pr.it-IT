---
title: 'Lync Server 2013: testing della sessione di conferenza telefonica con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7c3251ef5ff907dbf9964daaca222584953e75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536083"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Testing della sessione di conferenza telefonica con accesso esterno in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsDialInConferencing. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsDialInConferencing verifica se un utente può partecipare a una conferenza telefonica con accesso esterno. Test-CsDialInConferencing è compatibile con il tentativo di registrare un utente di test nel sistema. Se l'accesso ha esito positivo, il cmdlet utilizzerà le credenziali e le autorizzazioni dell'utente per provare tutti i numeri di accesso per le conferenze telefoniche in ingresso disponibili. L'esito positivo o negativo di ogni tentativo di accesso esterno verrà annotato, quindi l'utente di prova verrà disconnesso da Lync Server. Test-CsDialInConferencing verifica solo che sia possibile effettuare le connessioni appropriate. Con il cmdlet non vengono infatti effettuate chiamate telefoniche né create conferenze telefoniche con accesso esterno a cui possano partecipare altri utenti.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsDialInConferencing utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP account the calling Test-CsDialInConferencing:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato può accedere a Lync Server e quindi eseguire una connessione utilizzando uno dei numeri di accesso per le conferenze telefoniche in ingresso disponibili, riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non è in grado di effettuare questa connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: l'accesso è stato negato. Verificare che le credenziali appropriate siano

utilizzato e l'account è attivo.

Eccezione interna: NegotiateSecurityAssociation non riuscita, errore:-

2146893044

Diagnosi

L'output precedente indica che all'utente di test è stato negato l'accesso a Lync Server stesso. Questo significa in genere che le credenziali utente passate a Test-CsDialInConferencing non sono valide. A sua incirca, è necessario ricreare l'oggetto credenziali di Windows PowerShell. Anche se è possibile recuperare la password per l'account utente, è possibile verificare l'indirizzo SIP utilizzando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsDialInConferencing potrebbero non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - È possibile che si disponga di un numero di accesso per le conferenze telefoniche. È possibile restituire l'elenco attualmente configurato dei numeri di accesso per le conferenze telefoniche con chiamata in ingresso utilizzando il comando seguente:
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

