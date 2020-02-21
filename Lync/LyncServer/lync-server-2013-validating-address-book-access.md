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
ms.openlocfilehash: 665ee384afd85c4be5c82182691953e1c78c9659
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Convalida dell'accesso alla Rubrica in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsAddressBookService. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsAddressBookService consente di verificare che un utente possa connettersi al servizio Web di download della Rubrica. Quando si esegue il cmdlet, Test-CsAddressBookService si connette al servizio Web per il download della Rubrica nel pool specificato e richiede il percorso dei file della Rubrica. Se il servizio Web di download della Rubrica fornisce tale percorso, il test viene considerato completato. Se la richiesta viene rifiutata, l'esito del test è negativo.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsAddressBookService utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo (FQDN) del pool di Lync Server da testare. Ad esempio:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato è in grado di connettersi al servizio Rubrica, verrà restituito un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.2260399

Errore

Diagnosi

Se l'utente specificato non è in grado di effettuare questa connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test ha avuto esito negativo perché l'utente specificato (ovvero "URI di destinazione") non esiste o non è stato abilitato per Lync Server. È possibile verificare se un account utente è valido e verificare di aver fornito l'indirizzo SIP corretto eseguendo un comando simile al seguente:

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, abilitato

Se Test-CsAddressBookService ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose

Quando viene incluso il parametro Verbose Test-CsAddressBookService restituirà un account dettagliato di ogni azione tentata quando si verifica la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, in questo output di esempio viene mostrato che Test-CsAddressBookService, almeno in questo esempio, è stato in grado di scaricare il file della Rubrica:

Invio della richiesta HTTP GET.

Percorso file =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Numero tentativo = 1

TimeOut (msec) = 60000

Scaricato correttamente il file ABShttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsAddressBookService potrebbe non riuscire:

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

