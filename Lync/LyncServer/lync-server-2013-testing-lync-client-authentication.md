---
title: "Lync Server 2013: verificare l'autenticazione del client Lync"
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
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Test dell'autenticazione del client Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Quotidiana</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsClientAuth. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsClientAuth consente di determinare se un utente può accedere al server Lync usando un certificato client, è possibile eseguire il cmdlet Test-CsClientAuth. Dopo aver chiamato Test-CsClientAuth, il cmdlet contatterà il servizio di provisioning dei certificati e scaricherà una copia dei certificati client per l'utente specificato. Se è possibile trovare e scaricare un certificato client, Test-CsClientAuth cercherà di accedere tramite tale certificato. Se l'accesso riesce, Test-CsClientAuth si disconnetterà e riferirà che il test è riuscito. Se non è possibile trovare o scaricare un certificato oppure se il cmdlet non riesce ad accedere con tale certificato, Test-CsClientAuth segnalerà che il test non è riuscito.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsClientAuth viene eseguito usando l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsClientAuth:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato può accedere a Lync Server usando un certificato client, si riceverà un output simile a questo, con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non riesce ad accedere, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:03.3645259

Errore: non è stato possibile scaricare un certificato CS per l'utente specifico. Verificare se

URI e credenziali specificati sono corretti.

Diagnosi

Ad esempio, l'output precedente indica che il test non è riuscito perché un certificato client valido non è stato individuato per l'utente specificato. È possibile restituire un elenco dei certificati client rilasciati a un utente eseguendo un comando come indicato di seguito:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Se Test-CsClientAuth non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Quando viene incluso il parametro Verbose, Test-CsClientAuth restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio:

Provare a scaricare un certificato CS per l'utente: kenmyer@litwareinc.com endpoint: STEpid

URL del servizio Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Impossibile scaricare un certificato CS dal servizio Web.

CONTROLLO

\-L'URL del servizio Web è valido e i servizi Web sono funzionali

\-Se si usa\\\\PhoneNo pin per eseguire l'autenticazione, verificare che corrispondano all'URI dell'utente

\-Se si usa\\l'autenticazione Kerberos NTLM, verificare che siano state fornite credenziali valide

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsClientAuth potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - L'utente di test potrebbe non avere un certificato client valido. Puoi restituire informazioni sui certificati client assegnati a un utente usando un comando simile al seguente:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

