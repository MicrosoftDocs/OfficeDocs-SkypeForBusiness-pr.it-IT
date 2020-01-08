---
title: 'Lync Server 2013: testing sessione di conferenza telefonica con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcc6d9277f7333989c59b812ed76087b9b6ca9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Test della sessione di conferenza telefonica con accesso esterno in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsDialInConferencing. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsDialInConferencing verifica se un utente può partecipare a una conferenza telefonica con accesso esterno. Test-CsDialInConferencing funziona provando a registrare un utente di test nel sistema. Se l'accesso viene eseguito correttamente, il cmdlet utilizzerà le credenziali e le autorizzazioni dell'utente per provare tutti i numeri di accesso per i servizi di conferenza telefonica in ingresso disponibili. L'esito positivo o negativo di ogni tentativo di chiamata in entrata verrà annotato, quindi l'utente di test verrà disconnesso da Lync Server. Test-CsDialInConferencing verifica solo che sia possibile effettuare le connessioni appropriate. Il cmdlet non effettua effettivamente chiamate telefoniche o crea alcuna conferenza telefonica con accesso esterno a cui possono partecipare altri utenti.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsDialInConferencing può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Per eseguire questo controllo usando un account utente effettivo, devi creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP dell'account il test di chiamata-CsDialInConferencing:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato può accedere a Lync Server e quindi effettuare una connessione usando uno dei numeri di accesso per i servizi di conferenza telefonica in ingresso disponibili, riceverai un output simile a questo, con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non può eseguire questa connessione, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: il log-in è stato negato. Verificare che le credenziali appropriate siano

in uso e l'account è attivo.

Eccezione interna: NegotiateSecurityAssociation non riuscito, errore:-

2146893044

Diagnosi

L'output precedente indica che all'utente di test è stato negato l'accesso a Lync Server stesso. Ciò significa in genere che le credenziali utente passate a Test-CsDialInConferencing non erano valide. A sua volta, devi ricreare l'oggetto credenziali di Windows PowerShell. Anche se è possibile recuperare la password per l'account utente, è possibile verificare l'indirizzo SIP usando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsDialInConferencing potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - Potrebbe essere presente un numero di accesso esterno per i servizi di conferenza telefonica non corretto. Puoi restituire l'elenco attualmente configurato dei numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso usando questo comando:
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

