---
title: 'Lync Server 2013: criteri posizione test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Test dei criteri di posizione in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsLocationPolicy. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsLocationPolicy verifica che un criterio di posizione venga assegnato a un utente. Il criterio di posizione viene usato per applicare le impostazioni relative alla funzionalità E9-1-1 e alla posizione del client. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, se la risposta è "Sì", qual è il comportamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero che compone una chiamata di emergenza (911 negli Stati Uniti), se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.

È possibile testare i criteri di posizione per gli utenti o le subnet di rete. Se si esegue il test in una subnet (specificando un valore per il parametro subnet), il cmdlet tenterà di risolvere i criteri di posizione per la subnet. Se alla subnet non viene assegnato alcun criterio di posizione, verranno recuperati i criteri di posizione per l'utente configurato. Se i criteri di subnet vengono recuperati correttamente, l'output includerà un valore LocationPolicyTagID che inizia con subnet-tagid. Se non è stato trovato un criterio di posizione per la subnet, LocationPolicyTagID inizierà con User-tagid.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsLocationPolicy può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsLocationPolicy:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato ha un criterio di posizione valido, riceverai un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

EnhancedEmergencyServicesEnabled: vero

LocationPolicyTagID: utente-TagId

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se non è possibile trovare un criterio di posizione valido per l'utente specificato, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

L'output precedente indica che il test non è riuscito perché l'utente specificato non è valido: l'account non esiste oppure l'utente non è stato abilitato per Lync Server. È possibile verificare la validità di un account e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsLocationPolicy non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsLocationPolicy restituirà un account dettagliato di ogni azione provata durante la verifica dei criteri di posizione. Ad esempio, questo output indica che Lync Server non è in grado di accedere all'utente di test, probabilmente perché è stata specificata una password non valida:

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

Ecco alcuni motivi comuni per cui Test-CsLocationPolicy potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

