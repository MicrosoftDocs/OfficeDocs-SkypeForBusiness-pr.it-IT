---
title: 'Lync Server 2013: criterio percorso di testing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2d08cdd1db5607b8565cd6b1cf0317b9db26de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Test del criterio percorso in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsLocationPolicy. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsLocationPolicy verifica che un criterio percorso sia assegnato a un utente. I criteri percorso vengono utilizzati per applicare impostazioni che mettono in relazione la funzionalità E9-1-1 con la posizione del client. I criteri percorso determinano se un utente è abilitato per il servizio E9-1-1 e, se la risposta è "Sì", qual è il comportamento di una chiamata di emergenza. Ad esempio, è possibile utilizzare il criterio percorso per definire il numero che costituisce una chiamata di emergenza (911 negli Stati Uniti), se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.

È possibile testare i criteri percorso su utenti o subnet di rete. Se si esegue il test su una subnet (specificando un valore per il parametro Subnet), il cmdlet tenterà di risolvere i criteri percorso per quella subnet. Se alla subnet non sono assegnati criteri percorso, verranno recuperati i criteri percorso per l'utente configurato. Se il criterio di subnet viene recuperato correttamente, l'output includerà un valore LocationPolicyTagID che inizia con subnet-tagid. Se non vengono trovati criteri percorso per la subnet, LocationPolicyTagID inizierà con user-tagid.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsLocationPolicy utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsLocationPolicy:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato ha un criterio di percorso valido, riceverà un output simile al seguente, con la proprietà Result contrassegnata come **Success:**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: User-TagId

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se non è possibile trovare un criterio percorso valido per l'utente specificato, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 404, non trovato

Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,

Reason = URI di destinazione non abilitato per SIP o non

esiste.

Microsoft. Rtc. signaling. DiagnosticHeader

L'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è valido: l'account non esiste oppure l'utente non è stato abilitato per Lync Server. È possibile verificare la validità di un account e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando analogo al seguente:

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsLocationPolicy ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsLocationPolicy restituirà un account dettagliato di ogni azione tentata quando si verifica il criterio percorso. Ad esempio, questo output indica che Lync Server non è stato in grado di accedere all'utente di test, probabilmente perché è stata fornita una password non valida:

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

Di seguito sono riportate alcune ragioni comuni per cui Test-CsLocationPolicy potrebbe non riuscire:

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

