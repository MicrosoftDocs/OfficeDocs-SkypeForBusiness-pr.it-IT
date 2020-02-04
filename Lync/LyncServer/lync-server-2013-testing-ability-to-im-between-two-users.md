---
title: 'Lync Server 2013: verifica della capacità di messaggistica istantanea tra due utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Verifica della capacità di messaggistica istantanea tra due utenti in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsIM. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsIM verifica che una coppia di utenti di test possa scambiare messaggi istantanei. Quando viene chiamato, il cmdlet Test-CsIM inizia provando ad accedere a una coppia di utenti di test a Lync Server. Supponendo che i due accessi abbiano esito positivo, il cmdlet avvia quindi una sessione di messaggistica istantanea tra i due utenti di test. L'utente 1 invita l'utente 2 a una sessione di messaggistica istantanea e l'utente 2 accetta l'invito. Dopo aver verificato che i messaggi possano essere scambiati tra i due utenti, Test-CsIM termina la sessione di messaggistica istantanea e disconnette entrambi gli utenti dal sistema.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsIM può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server. Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se i due utenti possono completare una sessione di messaggistica istantanea, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.6630911

Errore

Diagnosi

Se gli utenti di test non riescono a completare la sessione, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 504, timeout del server

Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See

codice di risposta e frase motivo.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente indica che il test non è riuscito perché non è stato possibile trovare l'utente specificato. È possibile determinare se un indirizzo SIP è valido (e se l'utente ha assegnato l'indirizzo SIP per Lync Server) eseguendo questo comando:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Se Test-CsIM non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsIM restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dei due utenti di test di partecipare a una sessione di messaggistica istantanea. Ad esempio, ecco l'output di esempio che si verifica quando viene fornito un set di credenziali utente non corretto (in questo caso una password non corretta) per Test-CsIM:

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-011.litwareinc.com

Indirizzo SIP utente = sip:kenmyer@litwareinc.com

Porta registrar = 5061

Viene selezionato il tipo di autenticazione "IWA".

Hit di registrazione su SIP/atl-cs-001. litwareinc. com

Attività "Register" completata in "0,0601795" secs.

Eccezione ' il log-in è stato negato. Verificare che vengano usate le credenziali corrette e che l'account sia attivo. si è verificato durante il flusso di lavoro.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsIM potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
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

