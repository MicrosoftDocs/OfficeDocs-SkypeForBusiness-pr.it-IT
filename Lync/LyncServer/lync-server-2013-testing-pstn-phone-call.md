---
title: 'Lync Server 2013: test di chiamata telefonica PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8095b4b0bb6aa4e6920d291c3fde3885ae6bfb03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Test di chiamata telefonica PSTN in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsRegistration. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsPstnOutboundCall verifica la possibilità di un utente di effettuare una chiamata a un numero di telefono situato nella rete PSTN. Quando si esegue Test-CsPstnOutboundCall, il cmdlet tenta prima di tutto di registrare l'utente di test in Lync Server. Se l'accesso viene eseguito correttamente, il cmdlet tenterà di effettuare una chiamata telefonica attraverso il gateway PSTN. Questa chiamata telefonica verrà eseguita tramite il dial plan, il criterio vocale e altri criteri e impostazioni assegnati all'account di test. Quando la chiamata viene risolta, il cmdlet invia codici DTMF (Dual-Tone Multi-Frequency) tramite la rete per verificare la connettività multimediale.

Durante l'esecuzione del test, Test-CsPstnOutboundCall effettuerà una chiamata telefonica effettiva: il telefono di destinazione suonerà e dovrà rispondere affinché il test abbia successo. Anche questa chiamata deve essere terminata manualmente dall'amministratore.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsPstnOutboundCall può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare e il numero di telefono PSTN che viene chiamato. Ad esempio:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password. Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato può effettuare la chiamata e se la chiamata viene risolta, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non può effettuare la chiamata o se la chiamata non viene risolta, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:0987365

Errore: 403, Forbidden

Diagnosi: ErrorCode = 12001, source = atl-cs-001. litwareinc. com, Reason = User

Il criterio non contiene l'utilizzo della route telefonica

L'output precedente dichiara che il test non è riuscito perché il criterio vocale assegnato all'utente specificato non include un uso del telefono. (Gli usi telefonici collegano i criteri vocali alle route vocali. Senza un criterio vocale e una route vocale corrispondente non è possibile effettuare chiamate tramite la rete PSTN.

Se Test-CsPstnOutboundCall non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPstnOutboundCall restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:

Creazione di videochiamata audio in ' SIP: + 12065551219@litwareinc. com; user = phone '.

È stata ricevuta una risposta di 404 (non trovata) dalla rete e l'operazione non è riuscita.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsPstnOutboundCall potrebbe non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - Il criterio vocale assegnato all'utente specificato non ha un uso PSTN valido. Puoi determinare il criterio vocale assegnato a un utente usando un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    E quindi puoi determinare gli usi PSTN (se presenti) assegnati a tale criterio usando un comando simile al seguente, che recupera le informazioni sul criterio vocale per utente RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

