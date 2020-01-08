---
title: 'Lync Server 2013: verificare la capacità degli utenti mobili di scambiare messaggi istantanei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Testare la capacità degli utenti mobili di scambiare messaggi istantanei in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsMcxP2PIM. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il servizio di mobilità consente agli utenti di dispositivi mobili di eseguire operazioni come:

1.  Scambiare messaggi istantanei e informazioni sulla presenza.

2.  Archiviare e recuperare i messaggi vocali internamente anziché con il provider wireless.

3.  Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.

Il cmdlet test-CsMxcP2PIM offre un modo semplice e rapido per verificare che gli utenti possano usare il servizio mobilità per scambiare messaggi istantanei.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per eseguire questo test, è necessario creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsMcxP2PIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se i due utenti di test possono scambiare messaggi istantanei usando il servizio mobilità, Test-CsMcxP2PIM restituirà il risultato del test:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:http://atl-cs-001.litwareinc.com:443/mcx

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se il test ha esito negativo, il risultato verrà impostato su errore e verrà visualizzato un messaggio di errore e una diagnosi dettagliati:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:https://atl-cs-001.litwareinc.com:443/mcx

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web.

Eccezione interna: la richiesta di HHTP non è autorizzata con

schema di negoziazione client "NTLM". L'autenticazione

l'intestazione ricevuta dal server è "Negotiate, NTLM".

Eccezione interna: il server remoto ha restituito un errore:

(401) non autorizzato.

Diagnosi

Diagnosi interna: X-MS-Server-Fqdb: atl-cs-

001.litwareinc.com

Cache-Control: private

Content-Type: text/html; charset = UTF-8.

Server: Microsoft-IIS/8.5

Autenticazione WWW: negozia, NTLM

X-Powered-by: ASP.NET

X-Content-Type-Options: nosniffing

Data: Mer, 28 mag 2014 19:16:05 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsMcxP2PIM non riesce, il primo passaggio deve essere verificare che il servizio di mobilità sia attivo e funzionante. Questa operazione può essere eseguita usando un Web browser per verificare che sia possibile accedere all'URL del servizio di mobilità per il pool di Lync Server. Questo comando, ad esempio, verifica l'URL per il pool atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Se il servizio di mobilità sembra essere in corso, verificare che i due utenti di test dispongano di account di Lync Server validi. Puoi recuperare le informazioni dell'account usando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido.

Dovresti anche verificare che l'utente sia abilitato per la mobilità. A questo scopo, determina prima di tutto i criteri di mobilità assegnati all'account:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Dopo aver conosciuto il nome del criterio, usare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio RedmondMobilityPolicy) disponga della proprietà EnableMobility impostata su true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Se viene visualizzato un messaggio di errore con le intestazioni di autenticazione, significa che spesso non è stato specificato un account utente valido. Verificare il nome utente e la password e quindi riprovare il test. Se si è certi che l'account utente sia valido, usare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth. In questo modo verranno spiegati i metodi di autenticazione abilitati nell'organizzazione. Per altre informazioni su come risolvere i problemi relativi al servizio di mobilità, vedere il post di Blog risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

