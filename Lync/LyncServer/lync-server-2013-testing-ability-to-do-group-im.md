---
title: 'Lync Server 2013: test della capacità di eseguire un messaggio istantaneo di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Test della capacità di eseguire un messaggio istantaneo di gruppo in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsGroupIM. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsGroupIM verifica che gli utenti dell'organizzazione possano eseguire sessioni di messaggistica istantanea di gruppo. Quando si esegue Test-CsGroupIM, il cmdlet tenta di accedere a una coppia di utenti di test a Lync Server. In caso di esito positivo, Test-CsGroupIM crea una nuova conferenza usando il primo utente di test, quindi invita il secondo utente a partecipare alla conferenza. Dopo uno scambio di messaggi, entrambi gli utenti vengono scollegati dal sistema. Tieni presente che tutto ciò avviene senza alcuna interazione con l'utente e senza influenzare gli utenti effettivi. Supponiamo ad esempio che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che ha un vero account di Lync Server. In questo caso, il test verrà condotto senza interruzioni per il vero Ken. Ad esempio, anche quando l'account di test di Ken si disconnette dal sistema, Ken si connette alla persona che rimarrà connesso. Allo stesso modo, il vero Ken non riceverà un invito a partecipare alla conferenza. Tale invito verrà inviato e accettato dall'account di test.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsGroupIM può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server. Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti credenziali di Lync Server Management Shell (oggetti che contengono il nome e la password dell'account) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsGroupIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se i due utenti possono completare una sessione di messaggistica istantanea di gruppo, si riceverà un output simile a quello con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.3812203

Errore

Diagnosi

Se i due utenti non riescono a completare la sessione di messaggistica istantanea, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

L'output precedente indica che il test non è riuscito perché almeno uno degli account di test non è valido, perché l'account non esiste o perché l'utente non è stato abilitato per Lync Server. Puoi verificare che l'account esista e se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Se Test-CsGroupIM non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsGroupIM restituirà un account dettagliato di ogni azione provata quando ha verificato la possibilità per gli utenti specificati di partecipare a una sessione di messaggistica istantanea di gruppo. Ad esempio, se il test non riesce e viene detto che uno o più account utente non sono validi, è possibile rieseguire il test usando il parametro Verbose e determinare quale account utente non è valido:

Invio della richiesta di registrazione:

 FQDN di destinazione = atl-cs-001.litwareinc.com

 Indirizzo SIP utente = sip:kenmyer@litwareinc.com

 Register Port = 5061

Viene selezionato il tipo di autenticazione "IWA".

Eccezione ' il log-in è stato negato. Verificare che vengano usate le credenziali corrette e che l'account sia attivo.

Come si può vedere, in questo esempio l'utente che ha l'indirizzo SIP sip:kenmyer@litwareinc.com non è stato in grado di accedere.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsGroupIM potrebbe non riuscire:

  - È stato specificato un account utente non corretto. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - Il servizio di messaggistica istantanea potrebbe non essere disponibile. Con Lync Server è possibile configurare il sistema in modo che la messaggistica istantanea non sia disponibile se non è possibile accedere al database di archiviazione. Puoi verificare che eseguendo un comando simile al seguente:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Se BlockOnArchiveFailure è impostato su true, devi determinare se il database di archiviazione è o meno disponibile. È possibile restituire le posizioni dei database di archiviazione usando il comando seguente:
    
        Get-CsService -ArchivingDatabase

  - Il server di archiviazione potrebbe non essere disponibile. Puoi recuperare il nome di dominio completo dei server di archiviazione usando questo comando:
    
        Get-CsService -ArchivingServer
    
    È quindi possibile eseguire il ping del server appropriato per verificare che sia disponibile. Ad esempio:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

