---
title: "Lync Server 2013: verifica dell'autenticazione del client Lync"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308bb50e5365cd45c993875ea503b33b32617397
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519033"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Verifica dell'autenticazione del client Lync in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsClientAuth. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsClientAuth consente di determinare se un utente può accedere al server Lync utilizzando un certificato client, è possibile eseguire il cmdlet Test-CsClientAuth. Dopo aver chiamato Test-CsClientAuth, il cmdlet contatterà il servizio di provisioning dei certificati e scaricherà una copia di tutti i certificati client per l'utente specificato. Se è possibile trovare e scaricare un certificato client, Test-CsClientAuth tenterà di eseguire l'accesso utilizzando il certificato. Se l'accesso ha esito positivo, Test-CsClientAuth si disconnetterà e riporterà l'esito positivo del test. Se non è stato possibile trovare o scaricare un certificato oppure se il cmdlet non riesce ad ottenere l'accesso utilizzando quel certificato, il cmdlet Test-CsClientAuth segnalerà l'esito negativo del test.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsClientAuth viene eseguito utilizzando l'account di tutti gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsClientAuth:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato è in grado di accedere a Lync Server utilizzando un certificato client, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non è in grado di eseguire l'accesso, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:03.3645259

Errore: non è stato possibile scaricare un certificato CS per l'utente specificato. Controllare se

URI e credenziali specificati sono corretti.

Diagnosi

Ad esempio, l'output precedente dichiara che il test non ha avuto esito positivo perché non è stato possibile trovare un certificato client valido per l'utente specificato. È possibile restituire un elenco dei certificati client rilasciati a un utente eseguendo un comando come indicato di seguito:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Se Test-CsClientAuth ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Quando viene incluso il parametro Verbose, Test-CsClientAuth restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio:

Tentativo di download di un certificato CS per l'utente: kenmyer@litwareinc.com endpoint: STEpid

URL del servizio Web: https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Non è stato possibile scaricare un certificato CS dal servizio Web.

CONTROLLO

\- L'URL del servizio Web è valido e i servizi Web sono funzionali

\-Se si utilizza \\ \\ il pin di PhoneNo per eseguire l'autenticazione, assicurarsi che corrispondano all'URI dell'utente.

\- Se si utilizza l' \\ autenticazione Kerberos NTLM, accertarsi di aver specificato le credenziali valide

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsClientAuth potrebbero non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - L'utente di prova potrebbe non disporre di un certificato client valido. È possibile restituire informazioni sui certificati client assegnati a un utente utilizzando un comando simile al seguente:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

