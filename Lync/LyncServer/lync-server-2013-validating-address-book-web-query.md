---
title: 'Lync Server 2013: convalida della query Web della Rubrica'
description: 'Lync Server 2013: convalida della query Web della Rubrica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547252"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Convalida della query Web della Rubrica in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsAddressBookWebQuery. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsAddressBookWebQuery consente agli amministratori di verificare che gli utenti possano utilizzare il servizio query Web della Rubrica per cercare un contatto specifico. Quando si esegue il cmdlet, Test-CsAddressBookWebQuery si connetterà prima al servizio ticket web per essere autenticato. Se l'autenticazione ha esito positivo, il cmdlet verrà quindi connesso al servizio query Web della Rubrica e cercherà il contatto specificato. Se tale contatto viene individuato, il cmdlet tenta di restituire tale informazione al computer locale. Il test verrà contrassegnato come esito positivo solo se tutti i passaggi possono essere completati.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsAddressBookWebQuery utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server e l'indirizzo SIP dell'utente che funge da destinazione della ricerca. Ad esempio:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario creare un oggetto credenziali di Windows PowerShell che contenga un nome utente e una password validi. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando il codice chiama Test-CsAddressBookWebQuery:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato è in grado di connettersi al servizio Rubrica e recuperare l'indirizzo utente di destinazione, verrà restituito un output simile al seguente, con la proprietà Result contrassegnata come operazione riuscita:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.2611356

Errore

Diagnosi

Se l'utente specificato non è in grado di connettersi o se non è possibile recuperare l'indirizzo dell'utente di destinazione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: la richiesta del servizio Web della Rubrica non è riuscita con il codice di risposta

NoEntryFound.

Diagnosi

L'output precedente dichiara che il test ha avuto esito negativo perché l'utente di destinazione non è stato trovato. È possibile determinare se un indirizzo SIP valido è stato passato a Test-CsAddressBookWebQuery eseguendo un comando simile al seguente:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Se Test-CsAddressBookWebQuery ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsAddressBookWebQuery restituirà un account dettagliato di ogni azione tentata durante il controllo della capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che Test-CsAddressBookWebQuery è stato in grado di connettersi al servizio Rubrica, ma non è stato in grado di individuare l'indirizzo SIP di destinazione:

Attività' QueryAddressBookWebService ' iniziata.

Servizio query Web della rubrica chiamante. ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Eccezione della query della Rubrica: la richiesta del servizio Web della Rubrica non è riuscita con il codice di risposta NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsAddressBookWebQuery potrebbero non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - L'utente di destinazione potrebbe non trovarsi nella rubrica.

  - La Rubrica potrebbe non essere completamente aggiornata e replicata. È possibile forzare un aggiornamento di tutti i server della Rubrica nell'organizzazione eseguendo il comando riportato di seguito:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

