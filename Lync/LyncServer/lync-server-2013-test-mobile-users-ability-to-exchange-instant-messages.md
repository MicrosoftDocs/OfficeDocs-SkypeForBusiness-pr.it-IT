---
title: 'Lync Server 2013: testare la possibilità per gli utenti di dispositivi mobili di scambiare messaggi istantanei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84e4a79f511247b3c335872b7a1ec31fb9f2201e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Testare la possibilità per gli utenti di dispositivi mobili di scambiare messaggi istantanei in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsMcxP2PIM. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il servizio per dispositivi mobili consente agli utenti del dispositivo mobile di eseguire operazioni quali:

1.  Scambiare messaggi istantanei e informazioni sulla presenza.

2.  Archiviare e recuperare i messaggi vocali internamente anziché con il provider di servizi di rete.

3.  Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.

Il cmdlet test-CsMxcP2PIM consente di verificare in modo semplice e rapido che gli utenti possano utilizzare il servizio per dispositivi mobili per scambiare messaggi istantanei.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per eseguire questo test, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsMcxP2PIM, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se i due utenti di test possono scambiare messaggi istantanei utilizzando il servizio per dispositivi mobili, Test-CsMcxP2PIM restituirà il risultato del test:

FQDN di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:http://atl-cs-001.litwareinc.com:443/mcx

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se il test ha esito negativo, il risultato verrà impostato su errore e verrà visualizzato un messaggio di errore dettagliato e la diagnosi:

FQDN di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:https://atl-cs-001.litwareinc.com:443/mcx

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessuna risposta ricevuta per il servizio Web-Ticket.

Eccezione interna: la richiesta di HHTP non è stata autorizzata con

schema di negoziazione client ' NTLM '. L'autenticazione

l'intestazione ricevuta dal server è "Negotiate, NTLM".

Eccezione interna: il server remoto ha restituito un errore:

(401) non autorizzato.

Diagnosi

Diagnosi interna: X-MS-Server-Fqdb: atl-cs-

001.litwareinc.com

Cache-Control: private

Content-Type: text/html; charset = UTF-8.

Server: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-Powered-by: ASP.NET

X-Content-Type-Options: nosniff

Data: Mer, 28 May 2014 19:16:05 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se Test-CsMcxP2PIM ha esito negativo, il primo passaggio consiste nel verificare che il servizio per dispositivi mobili sia attivo e in esecuzione. Che è possibile eseguire utilizzando un Web browser per verificare che sia possibile accedere all'URL del servizio per dispositivi mobili per il pool di Lync Server. Ad esempio, questo comando consente di verificare l'URL per il pool atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Se il servizio per dispositivi mobili sembra essere in esecuzione, verificare che i due utenti di test dispongano di account di Lync Server validi. È possibile recuperare le informazioni dell'account utilizzando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando ha esito negativo, significa che l'utente non dispone di un account Lync Server valido.

È inoltre necessario verificare che l'utente sia abilitato per la mobilità. A tale scopo, determinare innanzitutto i criteri per dispositivi mobili assegnati all'account:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Una volta che si conosce il nome del criterio, utilizzare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio RedmondMobilityPolicy) la proprietà EnableMobility sia impostata su true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Se viene visualizzato un messaggio di errore con intestazioni di autenticazione, significa che spesso non è stato specificato un account utente valido. Verificare il nome utente e la password e quindi provare a eseguire di nuovo il test. Se si è certi che l'account utente sia valido, utilizzare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth. Che vi dirà quali metodi di autenticazione sono abilitati nell'organizzazione. Per ulteriori suggerimenti su come risolvere i problemi relativi al servizio per dispositivi mobili, vedere il post di Blog per la risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

