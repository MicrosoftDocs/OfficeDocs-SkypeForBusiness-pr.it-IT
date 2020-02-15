---
title: "Lync Server 2013: testare l'accesso a un'applicazione Web"
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
ms.openlocfilehash: a48580561a1a070b44b202e5d49c89261518dafe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42017847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Verificare l'accesso alle app Web in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsWebApp. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsWebApp verifica che gli utenti autenticati siano in grado di partecipare alle conferenze di Lync Server utilizzando Lync Web App. Quando si esegue il cmdlet, Test-CsWebApp Contatta il servizio ticket web per ottenere i ticket web per gli utenti specificati. Questi ticket agiscono efficacemente come ' ticket di ammissione ' alla conferenza di Lync Server. Se i ticket possono essere recuperati e se gli utenti possono essere autenticati, Test-CsWebApp contatterà Lync Server e tenterà di stabilire conferenze separate per la messaggistica istantanea, la condivisione di applicazioni e la collaborazione dati.

Si noti che Test-CsWebApp verifica solo le API e le connessioni utilizzate per creare queste conferenze. Il cmdlet è stato creato per verificare che Lync Web app possa essere utilizzato per creare e partecipare a conferenze. Tuttavia, in realtà non crea e conduce una conferenza.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsWebApp può essere eseguito utilizzando una coppia di account di test preconfigurati o gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsWebApp, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Si noti che Test-CsWebApp è obsoleto per l'utilizzo su Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsWebApp è in grado di aggiungere gli utenti alle rispettive conferenze, il cmdlet restituirà il risultato del test:

FQDN di destinazione:

Risultato: esito positivo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se gli utenti non sono in grado di partecipare alle conferenze necessarie, il risultato del test verrà contrassegnato come errore. In genere Test-CsWebApp riporterà anche un messaggio di errore dettagliato e una diagnosi:

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web

Diagnosi: la richiesta HTTP non è autorizzata con il client

schema di autenticazione ' NTLM '. L'autenticazione

l'intestazione ricevuta dal server è "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Gli errori di Test-CsWebApp in genere riguardano l'errore di autenticazione degli utenti. Se Test-CsWebApp ha esito negativo, è innanzitutto necessario verificare che gli utenti specificati dispongano di account utente validi e siano abilitati per Lync Server. È possibile recuperare le informazioni dell'account utilizzando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se la proprietà Enabled non è uguale a true o se il comando ha esito negativo, significa che l'utente non dispone di un account Lync Server valido. È inoltre necessario verificare che le password fornite al cmdlet siano valide.

</div>

</div>

<span> </span>

</div>

</div>

</div>

