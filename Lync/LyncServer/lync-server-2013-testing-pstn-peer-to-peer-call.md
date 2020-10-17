---
title: 'Lync Server 2013: testing PSTN peer to peer Call'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33aa0447c90ea9c76a1956cb817f0e61ce0d626e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504043"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Testing PSTN peer to peer Call in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsPstnPeerToPeerCall. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsPstnPeerToPeerCall verifica la capacità di una coppia di utenti di effettuare una chiamata peer-to-peer sul gateway PSTN (Public Switched Telephone Network). Quando si chiama Test-CsPstnPeerToPeerCall, il cmdlet tenterà innanzitutto di accedere a due utenti di test a Lync Server. Presupponendo che gli accessi abbiano esito positivo, il cmdlet utilizzerà l'utente 1 per tentare di chiamare l'utente 2 sul gateway PSTN. Test-CsPstnPeerToPeerCall effettuerà la chiamata utilizzando il dial plan, il criterio vocale e altre impostazioni di configurazione e criteri assegnate all'utente di test. Se il test viene pianificato, il cmdlet verificherà che l'utente 2 sia stato in grado di rispondere alla chiamata e quindi disconnettere entrambi gli account di test dal sistema.

Test-CsPstnPeerToPeerCall effettua una telefonata reale, una che verifica che sia possibile effettuare una connessione e che trasmetta anche codici DTMF sulla rete per determinare se è possibile inviare un supporto tramite la connessione. La chiamata viene risolta dal cmdlet stesso e non è necessaria alcuna terminazione manuale della chiamata. (Ovvero, nessuno deve rispondere e quindi riagganciare il telefono che è stato chiamato).

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsPstnPeerToPeerCall utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server. Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account. Quando si chiama Test-CsPstnPeerToPeerCall, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se gli utenti specificati possono completare una chiamata peer-to-peer, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se gli utenti specificati non sono in grado di completare una chiamata peer-to-peer, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:0182361

Errore: 403, Forbidden

Diagnosi: ErrorCode = 12001, source = atl-cs-001.litwareinc.com,

Reason = il criterio utente non contiene l'utilizzo di route telefoniche

L'output precedente dichiara che il test ha avuto esito negativo perché il criterio vocale assegnato a almeno uno degli utenti specificati non include un utilizzo del telefono. (Gli usi telefonici collegano i criteri vocali alle route vocali. Se non si dispone di un criterio vocale e di una route vocale corrispondente, non è possibile effettuare chiamate tramite la rete PSTN.

Se Test-CsPstnPeerToPeerCall ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPstnPeerToPeerCall restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:

Creazione di una chiamata audio video a' SIP: + 12065551219@litwareinc. com; user = phone '.

Eccezione ' una risposta 404 (non trovata) è stata ricevuta dalla rete e l'operazione ha avuto esito negativo.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsPstnPeerToPeerCall potrebbero non riuscire:

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

