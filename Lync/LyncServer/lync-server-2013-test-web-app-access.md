---
title: "Lync Server 2013: verificare l'accesso alle app Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Verificare l'accesso alle app Web in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsWebApp. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsWebApp verifica che gli utenti autenticati possano partecipare a conferenze di Lync Server tramite Lync Web App. Quando si esegue il cmdlet, Test-CsWebApp Contatta il servizio ticket web per ottenere i ticket web per gli utenti specificati. Questi biglietti agiscono efficacemente come "ticket di ammissione" alla conferenza di Lync Server. Se i ticket possono essere recuperati e se gli utenti possono essere autenticati, Test-CsWebApp contatterà Lync Server e tenterà di stabilire conferenze separate per la messaggistica istantanea, la condivisione delle applicazioni e la collaborazione ai dati.

Tieni presente che Test-CsWebApp verifica solo le API e le connessioni usate per creare queste conferenze. Il cmdlet è progettato per verificare che Lync Web app possa essere usato per creare e partecipare a conferenze. Tuttavia, in realtà non crea e conduce una conferenza.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsWebApp può essere eseguito usando una coppia di account di test preconfigurati o gli account di due utenti abilitati per Lync Server. Per eseguire questo controllo con gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server testato. Ad esempio:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsWebApp:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Tieni presente che Test-CsWebApp è stato deprecato per l'uso in Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se Test-CsWebApp può partecipare agli utenti alle proprie conferenze, il cmdlet restituirà il risultato del test:

FQDN di destinazione:

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se gli utenti non possono partecipare alle conferenze necessarie, il risultato del test verrà contrassegnato come errore. In genere Test-CsWebApp riporterà anche un messaggio di errore e una diagnosi dettagliati:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web

Diagnosi: la richiesta HTTP non è autorizzata con il client

schema di autenticazione "NTLM". L'autenticazione

l'intestazione ricevuta dal server è "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Gli errori di Test-CsWebApp in genere comportano errore di autenticazione degli utenti. Se Test-CsWebApp non riesce, verificare prima di tutto che gli utenti specificati dispongano di account utente validi e siano abilitati per Lync Server. Puoi recuperare le informazioni dell'account usando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido. Dovresti anche verificare che le password fornite al cmdlet siano valide.

</div>

</div>

<span> </span>

</div>

</div>

</div>

