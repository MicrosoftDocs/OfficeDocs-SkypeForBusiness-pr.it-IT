---
title: "Lync Server 2013: testare l'accesso degli utenti di dispositivi mobili"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6052785bdb8e748ac657d800a630ecc76415af9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Verificare l'accesso degli utenti di dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Mensile</p></td>
</tr>
<tr class="even">
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsMcxConference. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il servizio per dispositivi mobili consente agli utenti del dispositivo mobile di eseguire operazioni quali:

1.  Scambiare messaggi istantanei e informazioni sulla presenza.

2.  Archiviare e recuperare i messaggi vocali internamente anziché con il provider di servizi di rete.

3.  Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno. Il cmdlet Test-CsMcxConference consente di verificare rapidamente e facilmente che gli utenti possano partecipare a conferenze di Lync Server utilizzando un dispositivo mobile.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per eseguire il controllo, è necessario creare tre oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. È quindi necessario includere gli oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsMcxConference, come illustrato nell'esempio seguente:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se il controllo ha esito positivo, Test-CsMcxConference segnalerà un risultato di esito positivo:

FQDN di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:http://atl-cs-001.litwareinc.com:443/mcx

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se il controllo non ha avuto esito positivo, il Test-CsMcxConference segnalerà un risultato di esito negativo. Questo risultato del test sarà generalmente accompagnato da un messaggio di errore dettagliato e da una diagnosi. Ad esempio:

FQDN di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:https://atl-cs-001.litwareinc.com:443/mcx

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessuna risposta ricevuta per il servizio Web-Ticket.

Eccezione interna: la richiesta di HHTP non è autorizzata con il client

schema di negoziazione ' NTLM '. Intestazione di autenticazione ricevuta

dal server è stato ' Negotiate '.

Eccezione interna: il server remoto ha restituito un errore: (401)

Non autorizzato.

Diagnosi

Diagnosi interna: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com

Cache-Control: private

Content-Type: text/html; charset = UTF-8.

Server: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-Powered-by: ASP.NET

X-Content-Type-Options: nosniff

Data: Mer, 28 May 2014 19:22:19 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se Test-CsMcxConference ha esito negativo, è innanzitutto necessario verificare che il servizio per dispositivi mobili sia in esecuzione e che sia possibile accedervi. Che è possibile eseguire utilizzando un Web browser per verificare che sia possibile accedere all'URL del servizio per dispositivi mobili per il pool di Lync Server. Ad esempio, questo comando consente di verificare l'URL per il pool atl-cs-001.litwareinc.com:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Se è possibile accedere al servizio per dispositivi mobili, è necessario verificare che gli utenti di test dispongano di account Lync Server validi. È possibile recuperare le informazioni dell'account utilizzando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando ha esito negativo, significa che l'utente non dispone di un account Lync Server valido. È inoltre necessario verificare che ogni account utente sia abilitato per la mobilità. A tale scopo, determinare innanzitutto i criteri per dispositivi mobili assegnati all'account:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Una volta che si conosce il nome del criterio, utilizzare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio RedmondMobilityPolicy) la proprietà EnableMobility sia impostata su true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Se si riceve un messaggio di errore "intestazione di autenticazione" quando si esegue Test-CsMcxConference che spesso significa che non è stato specificato un account utente valido, verificare il nome utente e la password e quindi provare di nuovo il test. Se si è certi che l'account utente sia valido, utilizzare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth. Che vi dirà quali metodi di autenticazione sono abilitati nell'organizzazione.

Per ulteriori suggerimenti su come risolvere i problemi relativi al servizio per dispositivi mobili, vedere il post di Blog per la risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

