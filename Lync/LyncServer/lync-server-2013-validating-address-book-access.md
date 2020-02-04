---
title: "Lync Server 2013: convalida dell'accesso alla Rubrica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Convalida dell'accesso alla Rubrica in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsAddressBookService. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsAddressBookService offre un modo per verificare che un utente possa connettersi al servizio Web di download rubrica. Quando si esegue il cmdlet, Test-CsAddressBookService si connette al servizio Web di download rubrica nel pool specificato e richiede la posizione dei file della Rubrica. Se il servizio Web di download della Rubrica fornisce tale posizione, il test viene considerato riuscito. Se la richiesta viene rifiutata, il test viene considerato un errore.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsAddressBookService può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di prova, è sufficiente specificare il nome di dominio completo (FQDN) del pool di Lync Server da testare. Ad esempio:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato è in grado di connettersi al servizio Rubrica, verrà restituito l'output simile a questo, con la proprietà Result contrassegnata come **riuscita**:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.2260399

Errore

Diagnosi

Se l'utente specificato non è in grado di eseguire questa connessione, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test non è riuscito perché l'utente specificato (ovvero "URI di destinazione") non esiste o non è stato abilitato per Lync Server. È possibile verificare se un account utente è valido e verificare che sia stato fornito l'indirizzo SIP corretto eseguendo un comando come questo:

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsAddressBookService non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose

Quando il parametro Verbose è incluso Test-CsAddressBookService restituirà un account dettagliato di ogni azione che ha tentato quando controlla la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output di esempio mostra che Test-CsAddressBookService, almeno in questo esempio, è stato in grado di scaricare il file della Rubrica:

Invio della richiesta GET HTTP.

Percorso file =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Numero tentativo = 1

TimeOut (msec) = 60000

È stato scaricato correttamente il file ABShttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsAddressBookService potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

