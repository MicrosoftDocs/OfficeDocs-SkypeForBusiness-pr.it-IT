---
title: 'Lync Server 2013: test della chiamata peer-to-peer PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Test della chiamata peer-to-peer PSTN in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsPstnPeerToPeerCall. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsPstnPeerToPeerCall verifica la capacità di una coppia di utenti di eseguire una chiamata peer-to-peer sul gateway PSTN (Public Switched Telephone Network). Quando si chiama Test-CsPstnPeerToPeerCall, il cmdlet cercherà prima di accedere a due utenti di test a Lync Server. Supponendo che gli accessi abbiano esito positivo, il cmdlet User 1 tenterà di chiamare l'utente 2 tramite il gateway PSTN. Test-CsPstnPeerToPeerCall effettuerà questa chiamata usando il dial plan, il criterio vocale e altre impostazioni di criteri e configurazione assegnate all'utente di test. Se il test viene impostato come pianificato, il cmdlet verificherà che l'utente 2 abbia potuto rispondere alla chiamata e quindi disconnettere entrambi gli account di test dal sistema.

Test-CsPstnPeerToPeerCall effettua una chiamata telefonica effettiva, che verifica che sia possibile effettuare una connessione e che trasmetta anche i codici DTMF sulla rete per determinare se l'elemento multimediale può essere inviato tramite la connessione. La chiamata viene risolta dal cmdlet stesso e non è necessaria una terminazione manuale della chiamata. (Ovvero, nessuno deve rispondere e quindi appendere il telefono che è stato chiamato.)

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsPstnPeerToPeerCall può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server. Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account. È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsPstnPeerToPeerCall:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se gli utenti specificati possono completare una chiamata peer-to-peer, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.8630376

Errore

Diagnosi

Se gli utenti specificati non riescono a completare una chiamata peer-to-peer, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:0182361

Errore: 403, Forbidden

Diagnosi: ErrorCode = 12001, source = atl-cs-001.litwareinc.com,

Reason = il criterio utente non contiene l'utilizzo della route telefonica

L'output precedente dichiara che il test non è riuscito perché il criterio vocale assegnato ad almeno uno degli utenti specificati non include un uso del telefono. (Gli usi telefonici collegano i criteri vocali alle route vocali. Senza un criterio vocale e una route vocale corrispondente, non è possibile effettuare chiamate tramite la rete PSTN.

Se Test-CsPstnPeerToPeerCall non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPstnPeerToPeerCall restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:

Creazione di videochiamata audio in ' SIP: + 12065551219@litwareinc. com; user = phone '.

È stata ricevuta una risposta di 404 (non trovata) dalla rete e l'operazione non è riuscita.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsPstnPeerToPeerCall potrebbe non riuscire:

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

