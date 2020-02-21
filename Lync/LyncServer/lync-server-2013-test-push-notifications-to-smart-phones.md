---
title: 'Lync Server 2013: testare le notifiche push negli Smart Phone'
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
ms.openlocfilehash: 06684665819e14540628e5cd45309ef2c920b227
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Testare le notifiche push agli Smart Phone in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-15_


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
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsMcxPushNotification. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il servizio di notifica push (Apple Push Notification Service e Microsoft Push Notification Service) è in grado di inviare notifiche su eventi come nuovi messaggi istantanei o un nuovo sistema di caselle vocali ai dispositivi mobili come iPhone e Windows Phone, anche se il client Lync i dispositivi sono attualmente sospesi o in esecuzione in background. Il servizio di notifica push è un servizio basato su cloud in esecuzione nei server Microsoft. Per sfruttare al meglio le notifiche push, è necessario essere in grado di connettersi ed essere autenticati tramite la barra di compensazione notifiche push. Il cmdlet Test-CsMcxPushNotification consente agli amministratori di verificare che le richieste di notifica push possano essere instradate attraverso il server perimetrale per la compensazione notifiche push.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per testare il servizio di notifica push, chiamare il cmdlet Test-CsMcxPushNotification. Assicurarsi di specificare il nome di dominio completo del server perimetrale:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsMcxPushNotification ha esito positivo, il cmdlet restituirà il risultato del test:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:00

Errore

Diagnosi

Se Test-CsMcxPushNotification non è in grado di connettersi alla barra di compensazione notifiche push, il cmdlet in genere non restituisce un risultato del test di errore. Al contrario, il comando di solito avrà esito negativo. Ad esempio:

Test-CsMcxPushNotification: un 504 (timeout del server) la risposta è stata ricevuta dalla rete e l'operazione ha avuto esito negativo. Per ulteriori informazioni, vedere l'eccezione details.

At line: 1 char: 27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. Rtc. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se il servizio di notifica push ha esito negativo che in genere indica problemi di comunicazione con il server perimetrale o problemi di comunicazione con la casa di compensazione notifiche push. Se si verificano problemi durante l'esecuzione di Test-CsMcxPushNotification, la prima cosa da fare è verificare che il server perimetrale funzioni correttamente. È possibile utilizzare il cmdlet test-CsAVEdgeConnectivity per eseguire le operazioni seguenti:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Questo controllo verifica che un utente specificato sia in grado di connettersi al server perimetrale.

Se il server perimetrale sembra funzionare correttamente, significa spesso che non è possibile connettersi alla barra di compensazione notifiche push. In genere, questo significa che non è stato configurato correttamente l'URI di compensazione o che non si dispone di un record DNS SRV che punta a questo URL. È possibile verificare che l'URI sia impostato sul valore corretto (sip:push@push.lync.com) eseguendo il comando seguente:

    Get-CsMcxConfiguration

Se la proprietà PushNotificationProxyUri è impostata su un valore diverso da sip:push@push.lync.com, è possibile risolvere il problema utilizzando il cmdlet Set-McxConfiguration. Ad esempio, questo comando imposta correttamente l'URI all'interno dell'organizzazione:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Se l'URI è configurato correttamente, il passaggio successivo consiste nel verificare di disporre di un record DNS SRV che si risolve nel dominio SIP e nel server perimetrale. Per ulteriori informazioni su come configurare questi record, vedere l'argomento della Guida DNS requirements for Mobility. Si noti che il seguente messaggio di errore indica in genere un problema relativo ai record DNS:

Una risposta di 504 (timeout del server) è stata ricevuta dalla rete e l'operazione ha avuto esito negativo. Per ulteriori informazioni, vedere l'eccezione details.

È anche possibile che test-CsMcxConfiguration non venga eseguito correttamente con questo messaggio di errore:

Test-CsMcxPushNotification: la richiesta di notifica push è stata rifiutata.

At line: 1 char: 27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. Rtc. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

Il messaggio "richiesta di notifica push è stato rifiutato" in genere si verifica se è stato abilitato il filtro URL e si bloccano i prefissi http: e https:. È possibile determinare quali prefissi vengono bloccati utilizzando un comando simile al seguente:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Se http: o https: sono visualizzati nei risultati, è necessario rimuoverli dall'elenco dei prefissi bloccati per il funzionamento delle notifiche push. Che può essere ottenuto utilizzando comandi simili ai seguenti:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

