---
title: 'Lync Server 2013: verificare la possibilità di connettersi a un dominio federato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Verifica della possibilità di connettersi a un dominio federato da Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsFederatedPartner. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Test-CsFederatedPartner verifica la possibilità di connettersi al dominio di un partner federato. Per verificare la connettività a un dominio, tale dominio deve essere elencato nella raccolta di domini consentiti (federati). Puoi recuperare un elenco dei domini nell'elenco di domini consentiti usando questo comando:

    Get-CsAllowedDomain

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet test-FederatedPartner richiede due informazioni: il nome di dominio completo del server perimetrale e il nome di dominio completo del partner federato. Ad esempio, questo comando verifica la possibilità di connettersi al dominio contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Questo comando consente di testare le connessioni a tutti i domini attualmente presenti nell'elenco dei domini consentiti:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se il dominio specificato può essere contattato, si riceverà un output simile a quello con la proprietà Result contrassegnata come **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:00

Errore

Diagnosi

Se il dominio specificato non può essere contattato, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 504, timeout del server

Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See

codice di risposta e frase motivo.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test non è riuscito a causa di un errore di timeout del server. Questo indica in genere i problemi di connettività di rete o i problemi di contatto con il server perimetrale.

Se Test-CsFederatedPartner non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsFederatedPartner potrebbe non riuscire:

  - Il server perimetrale potrebbe non essere disponibile. Puoi usare questo comando per gli FQDN degli Edge Server:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    È quindi possibile eseguire il ping di ogni Edge Server per verificare che sia possibile accedervi tramite la rete. Ad esempio:
    
        ping atl-edge-001.litwareinc.com

  - Il dominio specificato potrebbe non essere elencato nell'elenco dei domini consentiti. Per verificare i domini aggiunti all'elenco dei domini consentiti, usare questo comando:
    
        Get-CsAllowedDomain
    
    Se si vuole visualizzare un elenco dei domini a cui gli utenti sono stati bloccati dalla comunicazione, usare questo comando:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

