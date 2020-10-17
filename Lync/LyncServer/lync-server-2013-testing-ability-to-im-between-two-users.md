---
title: 'Lync Server 2013: verifica della capacità di messaggistica istantanea tra due utenti'
description: 'Lync Server 2013: verifica della capacità di messaggistica istantanea tra due utenti.'
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
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560802"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Verifica della capacità di messaggistica istantanea tra due utenti in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsIM. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsIM verifica che una coppia di utenti di test sia in grado di scambiare messaggi istantanei. Quando viene chiamato, il cmdlet Test-CsIM inizia cercando di accedere a una coppia di utenti di test a Lync Server. Presupponendo che i due accessi abbiano esito positivo, il cmdlet avvia quindi una sessione di messaggistica istantanea tra i due utenti di test. (L'utente 1 invita l'utente 2 a una sessione di messaggistica istantanea e l'utente 2 accetta l'invito). Dopo aver verificato che i messaggi possono essere scambiati tra i due utenti, Test-CsIM termina la sessione di messaggistica istantanea e disconnette entrambi gli utenti dal sistema.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsIM utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsIM, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se i due utenti possono completare una sessione di messaggistica istantanea, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.6630911

Errore

Diagnosi

Se gli utenti di test non sono in grado di completare la sessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 504, timeout del server

Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See

codice di risposta e frase del motivo.

Microsoft. Rtc. signaling. DiagnosticHeader

Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato trovato. È possibile determinare se un indirizzo SIP è valido (e se l'utente assegnato l'indirizzo SIP è stato abilitato per Lync Server) eseguendo il comando seguente:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Se Test-CsIM ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsIM restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dei due utenti di test di prendere parte a una sessione di messaggistica istantanea. Ad esempio, ecco l'output di esempio che si verifica quando viene fornito un set di credenziali utente non corretto (in questo caso una password non corretta) a Test-CsIM:

Invio della richiesta di registrazione:

FQDN di destinazione = atl-cs-011.litwareinc.com

Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com

Porta di registrazione = 5061

Il tipo di autenticazione ' IWA ' è selezionato.

Hit di registrazione per SIP/atl-cs-001. litwareinc. com

Attività' Register ' completata in ' 0,0601795' secs.

Eccezione ' il login è stato negato. Verificare che le credenziali corrette vengano utilizzate e che l'account sia attivo. si è verificato durante il flusso di lavoro.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsIM potrebbero non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
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

