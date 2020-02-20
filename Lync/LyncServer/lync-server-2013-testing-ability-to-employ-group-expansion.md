---
title: "Lync Server 2013: testare la possibilità di utilizzare l'espansione dei gruppi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3178b96d156b64fc55f05403d50b3f7fcaa246bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Verifica della capacità di utilizzare l'espansione dei gruppi in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsGroupExpansion. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsGroupExpansion consente di determinare se l'espansione di gruppo sta funzionando all'interno dell'organizzazione. Quando l'espansione dei gruppi è abilitata, gli utenti configurano i gruppi di distribuzione come contatto. Questo significa che gli utenti possono quindi inviare lo stesso messaggio istantaneo a tutti i membri del gruppo, indirizzando il messaggio al gruppo anziché ai singoli membri di tale gruppo. l'espansione dei gruppi consente di visualizzare in modo semplice e rapido tutti i membri di un gruppo e il relativo stato corrente.

Con il cmdlet Test-CsGroupExpansion, è necessario specificare un gruppo di distribuzione di Active Directory utilizzando l'indirizzo di posta elettronica del gruppo. Test-CsGroupExpansion utilizza quindi l'espansione dei gruppi per recuperare l'appartenenza al gruppo e confrontare l'elenco recuperato con l'appartenenza all'indirizzo di posta elettronica del gruppo specificato. Se i due elenchi corrispondono, l'espansione dei gruppi sta funzionando correttamente. Si noti che è possibile testare l'espansione dei gruppi in due modi: testando il servizio stesso o testando il servizio Web associato.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsGroupExpansion utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare e l'indirizzo di posta elettronica per un gruppo di distribuzione valido. Ad esempio:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Lync Server che contenga il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsGroupExpansion:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato è in grado di utilizzare l'espansione dei gruppi, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:01.1234976

Errore

Diagnosi

Se l'utente specificato non è in grado di utilizzare l'espansione di gruppo, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore

Diagnosi

Test-CsGroupExpansion: l'endpoint non è stato in grado di eseguire la registrazione. Per motivi specifici, vedere ErrorCode.

L'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato in grado di eseguire la registrazione con Lync Server. Ciò si verifica in genere se l'account di test non esiste o non è abilitato per Lync Server. È possibile verificare che l'account esista e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsGroupExpansion ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose Test-CsGroupExpansion restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che non è stato possibile trovare il gruppo di distribuzione specificato:

Tentativo di ottenere il ticket web.

URL del servizio Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Utilizzo dell'autenticazione NTLM/cordolo.

GetWebTicketActivity completata.

Attività' VerifyDistributionList ' iniziata.

Lo stato di risposta del servizio Web DLX è: NotFound.

Attività' VerifyDistributionList ' completata in ' 0,2597923' secs.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsGroupExpansion potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - L'espansione del gruppo potrebbe essere disattivata. È possibile disattivare l'espansione dei gruppi. Se l'espansione del gruppo è stata disabilitata, il cmdlet Test-CsGroupExpansion avrà esito negativo. Per determinare se l'espansione dei gruppi è abilitata, utilizzare un comando simile al seguente:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

