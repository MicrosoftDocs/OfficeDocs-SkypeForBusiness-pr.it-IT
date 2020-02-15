---
title: "Lync Server 2013: testare l'accesso anonimo per le applicazioni Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5001b7c318c9d165d9e20bbcde83e7f34b3b7cc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Verificare l'accesso anonimo per le applicazioni Web in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsWebAppAnonymous. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsWebAppAnonymous verifica che un utente anonimo sia in grado di partecipare alle conferenze di Lync Server utilizzando Lync Web App. Quando si esegue il cmdlet, Test-CsWebAppAnonymous Contatta il servizio ticket web per ottenere un ticket web per l'utente anonimo. Se il cmdlet ha esito positivo per ottenere questo ticket, Test-CsWebAppAnonymous contatterà Lync Server e tenterà di stabilire conferenze separate per la messaggistica istantanea, la condivisione di applicazioni e la collaborazione dati.

Si noti che Test-CsWebAppAnonymous verifica solo le API e le connessioni utilizzate per creare queste conferenze. In realtà, il cmdlet non crea e conduce conferenze.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsWebAppAnonymous può essere eseguito utilizzando una coppia di account di test preconfigurati o gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Lync Server Management Shell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsWebAppAnonymous, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet Test-CsWebAppAnonymous. Si noti che Test-CsWebAppAnonymous è obsoleto per l'utilizzo su Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsWebAppAnonymous può unirsi all'utente anonimo per le conferenze, il cmdlet restituirà il risultato del test esito positivo:

FQDN di destinazione:

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se l'utente anonimo non è in grado di partecipare alle conferenze necessarie, il risultato del test verrà contrassegnato come errore. In genere Test-CsWebAppAnonymous riporterà anche un messaggio di errore dettagliato e una diagnosi:

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:05.9746266

Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web

Diagnosi: la richiesta HTTP non è autorizzata con il client

schema di autenticazione ' NTLM '. L'autenticazione

l'intestazione ricevuta dal server è "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Gli errori di Test-CsWebAppAnonymous in genere ruotano attorno a un errore di autenticazione degli utenti: è necessario eseguire il test utilizzando un account utente valido anche se il cmdlet verifica la capacità di un utente anonimo di connettersi a Lync Server. Se Test-CsWebAppAnonymous ha esito negativo, è necessario verificare che l'utente specificato abbia un account utente di Lync Server valido. È possibile recuperare le informazioni sull'account di Lync Server utilizzando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando ha esito negativo, significa che l'utente non dispone di un account Lync Server valido.

È inoltre necessario verificare che la password fornita quando si esegue il cmdlet sia una password valida.

I problemi di configurazione del server Office Web Apps possono anche causare l'esito negativo di Test-CsWebAppAnonymous; Questo sarà spesso il caso se si riceve la diagnosi seguente:

La richiesta HTTP non è autorizzata con lo schema di autenticazione client ' NTLM '. L'intestazione di autenticazione ricevuta dal server è stata ' Negotiate, NTLM '.

Per ulteriori informazioni sulla diagnosi e la risoluzione dei problemi del server Office Web Apps, vedere il post di Blog [Office Web Apps server 2013-le macchine vengono sempre segnalate come non integre](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

