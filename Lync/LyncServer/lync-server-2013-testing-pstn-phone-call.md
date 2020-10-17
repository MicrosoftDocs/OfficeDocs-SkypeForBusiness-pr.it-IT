---
title: 'Lync Server 2013: testing PSTN Phone Call'
description: 'Lync Server 2013: testing PSTN Phone Call.'
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
ms.openlocfilehash: b42ea6dd46145961a34386d704f8f44e9b7909ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547402"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Testing PSTN Phone Call in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsPstnOutboundCall verifica la capacità di un utente di effettuare una chiamata a un numero di telefono che si trova nella rete PSTN. Quando si esegue Test-CsPstnOutboundCall, il cmdlet tenta innanzitutto di accedere all'utente di test su Lync Server. Se l'accesso ha esito positivo, il cmdlet tenterà di effettuare una chiamata telefonica sul gateway PSTN. Questa telefonata verrà effettuata utilizzando il dial plan, il criterio vocale e gli altri criteri e le impostazioni assegnati all'account di test. Quando si riceve una risposta alla chiamata, il cmdlet invia codici DTMF (Dual-Tone Multi-Frequency) sulla rete per verificare la connettività multimediale.

Nel corso del test, il cmdlet Test-CsPstnOutboundCall effettua una vera chiamata telefonica: il telefono di destinazione squillerà e sarà necessario rispondere affinché il test possa considerarsi riuscito. Questa chiamata deve essere terminata manualmente dall'amministratore.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsPstnOutboundCall utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo del pool di Lync Server da testare e il numero di telefono PSTN chiamato. Ad esempio:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato è in grado di effettuare la chiamata e, se la chiamata ha esito positivo, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se l'utente specificato non è in grado di effettuare la chiamata o se la chiamata non è stata risolta, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:0987365

Errore: 403, Forbidden

Diagnosi: ErrorCode = 12001, source = atl-cs-001. litwareinc. com, Reason = User

Il criterio non contiene l'utilizzo di route telefoniche

L'output precedente dichiara che il test ha avuto esito negativo perché il criterio vocale assegnato all'utente specificato non include un utilizzo del telefono. (Gli usi telefonici collegano i criteri vocali alle route vocali. Senza un criterio vocale e una route vocale corrispondente, non è possibile effettuare chiamate tramite la rete PSTN.

Se Test-CsPstnOutboundCall ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPstnOutboundCall restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:

Creazione di una chiamata audio video a' SIP: + 12065551219@litwareinc. com; user = phone '.

Eccezione ' una risposta 404 (non trovata) è stata ricevuta dalla rete e l'operazione ha avuto esito negativo.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsPstnOutboundCall potrebbero non riuscire:

  - È stato specificato un account utente non valido. È possibile verificare che esista un account utente eseguendo un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server. Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.

  - I criteri vocali assegnati all'utente specificato non dispongono di un utilizzo PSTN valido. Per determinare il criterio vocale assegnato a un utente, è possibile utilizzare un comando simile al seguente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    È quindi possibile determinare gli utilizzi PSTN (se presenti) assegnati a tale criterio utilizzando un comando simile al seguente, in cui vengono recuperate le informazioni sul criterio vocale per utente RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

