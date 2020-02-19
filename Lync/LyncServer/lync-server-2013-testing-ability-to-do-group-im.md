---
title: 'Lync Server 2013: testare la capacità di eseguire un gruppo di messaggistica istantanea'
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
ms.openlocfilehash: ecb197f7ce8acbd4639be9ee20b93e6008922f3c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Verifica della capacità di eseguire un gruppo di messaggistica istantanea in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsGroupIM. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsGroupIM verifica che gli utenti dell'organizzazione possano condurre sessioni di messaggistica istantanea di gruppo. Quando si esegue Test-CsGroupIM, il cmdlet tenta di accedere a una coppia di utenti di test a Lync Server. Se l'accesso riesce, il cmdlet Test-CsGroupIM crea una nuova conferenza utilizzando il primo utente di test, quindi invita il secondo utente a parteciparvi. Dopo uno scambio di messaggi, entrambi gli utenti vengono disconnessi dal sistema. Si noti che tutto questo accade senza alcuna interazione dell'utente e senza influire su eventuali utenti effettivi. Si supponga, ad esempio, che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che dispone di un account Lync Server reale. In questo caso, il test verrà eseguito senza coinvolgere il vero Ken Myer. Ad esempio, anche quando l'account di test di Ken Myer si disconnette, il vero Ken Myer resterà connesso al sistema. Analogamente, il vero Ken non riceverà un invito a partecipare alla conferenza. L'invio verrà inviato all'account di test e da quest'ultimo accettato.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsGroupIM può essere eseguito utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Lync Server Management Shell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsGroupIM, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se i due utenti possono completare una sessione di messaggistica istantanea di gruppo, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.3812203

Errore

Diagnosi

Se i due utenti non sono in grado di completare la sessione di messaggistica istantanea, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

L'output precedente dichiara che il test ha avuto esito negativo perché almeno uno degli account di test non era valido, perché l'account non esiste o perché l'utente non è stato abilitato per Lync Server. È possibile verificare l'esistenza dell'account e se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Se Test-CsGroupIM ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsGroupIM restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità degli utenti specificati di partecipare a sessioni di messaggistica istantanea di un gruppo. Ad esempio, se il test ha esito negativo e si dice che uno o più account utente non sono validi, è possibile rieseguire il test utilizzando il parametro Verbose e determinare quale account utente non è valido:

Invio della richiesta di registrazione:

 FQDN di destinazione = atl-cs-001.litwareinc.com

 Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com

 Registrazione porta = 5061

Il tipo di autenticazione ' IWA ' è selezionato.

Eccezione ' il login è stato negato. Verificare che le credenziali corrette vengano utilizzate e che l'account sia attivo.

Come si può notare, in questo esempio l'utente con l'indirizzo SIP sip:kenmyer@litwareinc.com non è stato in grado di eseguire l'accesso.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsGroupIM potrebbe non riuscire:

  - È stato specificato un account utente non corretto. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - Il servizio di messaggistica istantanea potrebbe non essere disponibile. Con Lync Server, è possibile configurare il sistema in modo che la messaggistica istantanea non sia disponibile se non è possibile accedere al database di archiviazione. È possibile verificare che eseguendo un comando simile al seguente:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Se BlockOnArchiveFailure è impostato su true, è necessario determinare se il database di archiviazione è disponibile o meno. È possibile restituire le posizioni dei database di archiviazione utilizzando il comando seguente:
    
        Get-CsService -ArchivingDatabase

  - Il server di archiviazione potrebbe non essere disponibile. Per recuperare il nome di dominio completo dei server di archiviazione, è possibile utilizzare il comando seguente:
    
        Get-CsService -ArchivingServer
    
    È quindi possibile eseguire il ping del server appropriato per verificare che sia disponibile. Ad esempio:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

