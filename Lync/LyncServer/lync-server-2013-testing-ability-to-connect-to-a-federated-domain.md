---
title: 'Lync Server 2013: verifica della possibilità di connettersi a un dominio federato'
description: 'Lync Server 2013: verifica della possibilità di connettersi a un dominio federato.'
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
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560822"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Verifica della possibilità di connettersi a un dominio federato da Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsFederatedPartner. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Test-CsFederatedPartner consente di verificare la possibilità di connessione al dominio di un partner federato. Per verificare la connettività a un dominio, tale dominio deve essere elencato nell'insieme dei domini consentiti (federati). È possibile recuperare un elenco di domini nell'elenco dei domini consentiti utilizzando questo comando:

    Get-CsAllowedDomain

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-FederatedPartner richiede due informazioni: il nome di dominio completo del server perimetrale e il nome di dominio completo del partner federato. Ad esempio, questo comando consente di testare la possibilità di connettersi al dominio contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Questo comando consente di testare le connessioni a tutti i domini attualmente presenti nell'elenco dei domini consentiti:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se il dominio specificato può essere contattato, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:00

Errore

Diagnosi

Se il dominio specificato non può essere contattato, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 504, timeout del server

Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See

codice di risposta e frase del motivo.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo a causa di un errore del timeout del server. Questo indica in genere i problemi di connettività di rete o i problemi che contattano il server perimetrale.

Se Test-CsFederatedPartner ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsFederatedPartner potrebbero non riuscire:

  - Il server perimetrale potrebbe non essere disponibile. È possibile utilizzare questo comando per i nomi FQDN dei server perimetrali:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    È quindi possibile eseguire il ping di ogni server perimetrale per verificare che sia possibile accedervi tramite la rete. Ad esempio:
    
        ping atl-edge-001.litwareinc.com

  - Il dominio specificato potrebbe non essere elencato nell'elenco dei domini consentiti. Per verificare i domini che sono stati aggiunti all'elenco dei domini consentiti, utilizzare il seguente comando:
    
        Get-CsAllowedDomain
    
    Se si desidera visualizzare un elenco di domini ai quali gli utenti sono stati bloccati dalla comunicazione, utilizzare questo comando:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

