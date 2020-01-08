---
title: "Lync Server 2013: verificare l'accesso degli utenti di dispositivi mobili"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda2ec2d02fe4189c8e34cf700f6f1fd07895ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Testare l'accesso degli utenti di dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-07_


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
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsMcxConference. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il servizio di mobilità consente agli utenti di dispositivi mobili di eseguire operazioni come:

1.  Scambiare messaggi istantanei e informazioni sulla presenza.

2.  Archiviare e recuperare i messaggi vocali internamente anziché con il provider wireless.

3.  Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno. Il cmdlet Test-CsMcxConference offre un modo semplice e rapido per verificare che gli utenti possano partecipare e partecipare alle conferenze di Lync Server usando un dispositivo mobile.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per eseguire questo controllo, è necessario creare tre oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsMcxConference, come illustrato nell'esempio seguente:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se il controllo ha esito positivo, Test-CsMcxConference segnalerà un risultato di test positivo:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:http://atl-cs-001.litwareinc.com:443/mcx

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se il controllo non è riuscito, il Test CsMcxConference segnalerà un risultato di errore. Questo risultato del test sarà in genere accompagnato da un messaggio di errore e una diagnosi dettagliati. Ad esempio:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:https://atl-cs-001.litwareinc.com:443/mcx

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web.

Eccezione interna: la richiesta HHTP non è autorizzata con il client

schema di negoziazione "NTLM". Intestazione di autenticazione ricevuta

dal server è stato "negozia".

Eccezione interna: il server remoto ha restituito un errore: (401)

Autorizzato.

Diagnosi

Diagnosi interna: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com

Cache-Control: private

Content-Type: text/html; charset = UTF-8.

Server: Microsoft-IIS/8.5

Autenticazione WWW: negozia, NTLM

X-Powered-by: ASP.NET

X-Content-Type-Options: nosniffing

Data: Mer, 28 mag 2014 19:22:19 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsMcxConference non riesce, è necessario iniziare verificando che il servizio di mobilità sia in funzione ed è possibile accedervi. Questa operazione può essere eseguita usando un Web browser per verificare che sia possibile accedere all'URL del servizio di mobilità per il pool di Lync Server. Questo comando, ad esempio, verifica l'URL per il pool atl-cs-001.litwareinc.com:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Se è possibile accedere al servizio di mobilità, verificare che gli utenti di test dispongano di account di Lync Server validi. Puoi recuperare le informazioni dell'account usando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido. Dovresti anche verificare che ogni account utente sia abilitato per la mobilità. A questo scopo, determina prima di tutto i criteri di mobilità assegnati all'account:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Dopo aver conosciuto il nome del criterio, usare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio RedmondMobilityPolicy) disponga della proprietà EnableMobility impostata su true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Se viene visualizzato un messaggio di errore "intestazione di autenticazione" quando si esegue Test-CsMcxConference, che spesso significa che non è stato specificato un account utente valido, verificare il nome utente e la password e quindi riprovare il test. Se si è certi che l'account utente sia valido, usare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth. In questo modo verranno spiegati i metodi di autenticazione abilitati nell'organizzazione.

Per altre informazioni su come risolvere i problemi relativi al servizio di mobilità, vedere il post di Blog risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

