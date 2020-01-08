---
title: "Lync Server 2013: test della capacità di usare l'espansione del gruppo"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Possibilità di test per l'utilizzo dell'espansione di gruppo in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsGroupExpansion. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsGroupExpansion consente di determinare se l'espansione di gruppo sta funzionando all'interno dell'organizzazione. Quando l'espansione del gruppo è abilitata, gli utenti configurano i gruppi di distribuzione come contatto. Ciò significa che gli utenti possono quindi inviare lo stesso messaggio istantaneo a tutti i membri del gruppo indirizzando il messaggio al gruppo anziché ai singoli membri del gruppo. Espansione gruppo consente di visualizzare in modo semplice e rapido tutti i membri del gruppo e il relativo stato corrente.

Con il cmdlet Test-CsGroupExpansion, devi specificare un gruppo di distribuzione di Active Directory usando l'indirizzo di posta elettronica del gruppo. Test-CsGroupExpansion usa quindi l'espansione di gruppo per recuperare l'appartenenza al gruppo e confrontare l'elenco recuperato con l'appartenenza dell'indirizzo di posta elettronica del gruppo specificato. Se i due elenchi corrispondono, l'espansione del gruppo funziona correttamente. Tieni presente che puoi testare l'espansione del gruppo in due modi: testando il servizio stesso o provando il servizio Web associato.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsGroupExpansion può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare e l'indirizzo di posta elettronica per un gruppo di distribuzione valido. Ad esempio:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Lync Server contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsGroupExpansion:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato può usare l'espansione di gruppo, riceverai un output simile a quello con la proprietà Result contrassegnata come **riuscita:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:01.1234976

Errore

Diagnosi

Se l'utente specificato non può usare l'espansione di gruppo, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà errore e diagnosi:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore

Diagnosi

Test-CsGroupExpansion: l'endpoint non è stato in grado di eseguire la registrazione. Vedere il ErrorCode per un motivo specifico.

L'output precedente indica che il test non è riuscito perché l'utente specificato non è riuscito a eseguire la registrazione con Lync Server. In genere si verifica se l'account di test non esiste o non è abilitato per Lync Server. Puoi verificare che l'account esista e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsGroupExpansion non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Quando il parametro Verbose è incluso Test-CsGroupExpansion restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che non è stato possibile trovare il gruppo di distribuzione specificato:

Provare a ottenere un biglietto Web.

URL del servizio Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Uso dell'autenticazione NTLM/cordolo.

GetWebTicketActivity completata.

Attività' VerifyDistributionList ' iniziata.

Lo stato di risposta del servizio Web DLX è: NotFound.

Attività "VerifyDistributionList" completata in "0,2597923" secs.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsGroupExpansion potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - L'espansione del gruppo potrebbe essere disabilitata. È possibile disattivare l'espansione del gruppo. Se l'espansione del gruppo è stata disattivata, il cmdlet Test-CsGroupExpansion avrà esito negativo. Per determinare se l'espansione del gruppo è abilitata, usare un comando simile al seguente:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

