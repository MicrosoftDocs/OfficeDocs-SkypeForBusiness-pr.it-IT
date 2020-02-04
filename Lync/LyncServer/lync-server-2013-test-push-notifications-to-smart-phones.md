---
title: 'Lync Server 2013: testare le notifiche push in Smart Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94daa288757e2a0af446b455b951af9a990147b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Testare le notifiche push agli smartphone in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-03-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Mensile</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsMcxPushNotification. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il servizio di notifica push (servizio notifica push Apple e servizio notifica push Microsoft) può inviare notifiche su eventi come nuovi messaggi istantanei o un nuovo messaggio vocale a dispositivi mobili come iPhone e telefoni Windows, anche se il client Lync in questi dispositivi è attualmente sospesa o in corso in background. Il servizio di notifica push è un servizio basato su cloud in uso nei server Microsoft. Per sfruttare le notifiche push, è necessario essere in grado di connettersi e di essere autenticati tramite la finestra di compensazione delle notifiche push. Il cmdlet Test-CsMcxPushNotification consente agli amministratori di verificare che le richieste di notifica push possano essere instradate tramite il server perimetrale alla compensazione delle notifiche push.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per testare il servizio di notifica push, chiama il cmdlet Test-CsMcxPushNotification. Verificare di aver specificato il nome di dominio completo del server perimetrale:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se Test-CsMcxPushNotification ha esito positivo il cmdlet restituirà il risultato del test:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:00

Errore

Diagnosi

Se Test-CsMcxPushNotification non è in grado di connettersi alla barra di notifica push, il cmdlet non restituirà in genere un risultato di verifica dell'errore. Al contrario, il comando fallirà in genere completamente. Ad esempio:

Test-CsMcxPushNotification: una risposta di 504 (timeout del server) è stata ricevuta dalla rete e l'operazione non è riuscita. Per altre informazioni, vedere i dettagli sull'eccezione.

At line: 1 carattere: 27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. Rtc. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se il servizio di notifica push non riesce che in genere indica i problemi di comunicazione con il server perimetrale o i problemi di comunicazione con la camera di compensazione delle notifiche push. Se si verificano problemi durante l'esecuzione di Test-CsMcxPushNotification, la prima operazione da eseguire è verificare che il server perimetrale funzioni correttamente. Un modo per eseguire questa operazione consiste nell'usare il cmdlet test-CsAVEdgeConnectivity:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Questo controllo verifica che un utente specificato possa connettersi al server perimetrale.

Se il server perimetrale sembra funzionare correttamente, significa spesso che non si riesce a connettersi alla finestra di compensazione delle notifiche push. A sua volta, ciò significa in genere che l'URI di compensazione non è stato configurato correttamente o che non si ha un record SRV DNS che punta a questo URL. Puoi verificare che l'URI sia impostato sul valore corretto (sip:push@push.lync.com) eseguendo questo comando:

    Get-CsMcxConfiguration

Se la proprietà PushNotificationProxyUri è impostata su un valore diverso da sip:push@push.lync.com, è possibile risolvere il problema usando il cmdlet Set-McxConfiguration. Questo comando, ad esempio, imposta correttamente l'URI nell'intera organizzazione:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Se l'URI è configurato correttamente, il passaggio successivo deve essere verificare di avere un record SRV DNS che venga risolto nel dominio SIP e nel server perimetrale. Per altre informazioni su come configurare questi record, vedere l'argomento della Guida requisiti DNS per la mobilità. Tieni presente che il messaggio di errore seguente indica in genere un problema con i record DNS:

Una risposta di 504 (timeout del server) è stata ricevuta dalla rete e l'operazione non è riuscita. Per altre informazioni, vedere i dettagli sull'eccezione.

È anche possibile che test-CsMcxConfiguration non riesca con questo messaggio di errore:

Test-CsMcxPushNotification: la richiesta di notifica push è stata rifiutata.

At line: 1 carattere: 27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. Rtc. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

Il messaggio "richiesta di notifica push è stato rifiutato" in genere si verifica se è stato abilitato il filtro URL e si bloccano i prefissi http: e https:. Puoi determinare quali prefissi vengono bloccati usando un comando simile al seguente:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Se http: o https: vengono visualizzati nei risultati, è necessario rimuoverli dall'elenco di prefissi bloccati per il lavoro delle notifiche push. Questa operazione può essere eseguita usando comandi simili ai seguenti:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

