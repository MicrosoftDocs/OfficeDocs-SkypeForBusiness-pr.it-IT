---
title: 'Lync Server 2013: convalida della query Web Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Convalida della query Web della Rubrica in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsAddressBookWebQuery. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsAddressBookWebQuery consente agli amministratori di verificare che gli utenti possano usare il servizio query Web Rubrica per cercare un contatto specifico. Quando si esegue il cmdlet, Test-CsAddressBookWebQuery si connette prima al servizio ticket web per l'autenticazione. Se l'autenticazione ha esito positivo, il cmdlet si connetterà al servizio query Web della Rubrica e cercherà il contatto specificato. Se tale contatto viene trovato, il cmdlet tenterà di restituire tali informazioni al computer locale. Il test verrà contrassegnato come successo solo se tutti questi passaggi possono essere completati.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsAddressBookWebQuery può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server e l'indirizzo SIP dell'utente che funge da destinazione della ricerca. Ad esempio:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Per eseguire questo controllo usando un account utente effettivo, devi creare un oggetto credenziali di Windows PowerShell che contiene un nome utente e una password validi. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando il codice chiama Test-CsAddressBookWebQuery:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato può connettersi al servizio Rubrica e recuperare l'indirizzo utente di destinazione, si restituirà l'output simile a quello con la proprietà Result contrassegnata come riuscita:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.2611356

Errore

Diagnosi

Se l'utente specificato non riesce a connettersi o se l'indirizzo utente di destinazione non può essere recuperato, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: la richiesta di un servizio Web della Rubrica non è riuscita con il codice di risposta

NoEntryFound.

Diagnosi

L'output precedente dichiara che il test non è riuscito perché l'utente di destinazione non è stato trovato. È possibile determinare se un indirizzo SIP valido è stato passato a Test-CsAddressBookWebQuery eseguendo un comando simile al seguente:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Se Test-CsAddressBookWebQuery non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsAddressBookWebQuery restituirà un account dettagliato di ogni azione provata durante il controllo della capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che Test-CsAddressBookWebQuery è stato in grado di connettersi al servizio Rubrica, ma non è stato in grado di individuare l'indirizzo SIP di destinazione:

Attività' QueryAddressBookWebService ' iniziata.

Servizio query Web della rubrica chiamate. URL ABWS =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Eccezione query Rubrica: la richiesta di servizio Web della Rubrica non è riuscita con il codice di risposta NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsAddressBookWebQuery potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - L'utente di destinazione potrebbe non essere presente nella rubrica.

  - La Rubrica potrebbe non essere completamente aggiornata e replicata. È possibile forzare l'aggiornamento di tutti i server della rubrica dell'organizzazione eseguendo il comando seguente:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

