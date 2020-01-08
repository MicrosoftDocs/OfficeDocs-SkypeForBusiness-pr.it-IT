---
title: 'Lync Server 2013: verificare la configurazione vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Verificare la configurazione vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-20_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsVoiceTestConfiguration. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Lync Server include diversi cmdlet di Windows PowerShell, ad esempio Test-CsVoiceRoute e Test-CsVoicePolicy, Test-CsTrunkConfiguration, che consentono di verificare che i singoli elementi dell'infrastruttura vocale aziendale, ovvero le route vocali, la voce i criteri, trunk SIP, funzionano come previsto.

Mentre è importante con Enterprise Voice che tutti i singoli pezzi funzionano: è possibile avere una route vocale valida, un criterio vocale valido e un trunk SIP valido, ma gli utenti non possono ancora effettuare o ricevere chiamate telefoniche. Per questo motivo, Lync Server offre anche la possibilità di creare configurazioni di test vocali. Le configurazioni di test vocale rappresentano scenari comuni per le voci aziendali: è possibile specificare elementi come una route vocale, un criterio vocale e un dial plan, quindi verificare che questi singole voci funzionino in modo da collaborare per ottenere un servizio telefonico. Inoltre, puoi convalidare le tue aspettative in uno scenario specifico. Supponiamo ad esempio che si preveda che la combinazione di dial plan A e Policy vocale B comporterebbe la routing delle chiamate tramite la route vocale C. È possibile immettere la route vocale C come ExpectedRoute. Quando si esegue il test, se la route vocale C non viene usata, il test verrà contrassegnato come non riuscito.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Prima di testare le raccolte di configurazione vocale tramite Windows PowerShell, devi prima usare il cmdlet Get-CsVoiceTestConfiguration per recuperare un'istanza di queste impostazioni di configurazione. Questa istanza deve quindi essere inviata tramite pipe al Test-CsVoiceTestConfiguration. Ad esempio:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Per convalidare tutte le impostazioni di configurazione del test vocale contemporaneamente, usare questo comando:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Il cmdlet Test-CsVoiceTestConfiguration segnala se un test non è riuscito o è riuscito e fornisce informazioni aggiuntive su ogni test riuscito, ad esempio la regola di traduzione, la route vocale e l'utilizzo PSTN usato per completare l'attività:

Risultato: successo

TranslatedNumber: + 15551234

MatchingRule: Description =; Pattern = ^ (\\d{4}) $; Traduzione = + 1\\d; Name = test; IsInternalExtension = false

FirstMatchingRoute: sito: Redmond

MatchingUsage: local

Se il test ha esito negativo, il risultato viene segnalato come non riuscito:

Risultato: errore

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Dato che i test della configurazione del test vocale provano diversi elementi, tra cui i criteri vocali, i dial plan, le route vocali e così via, esistono diversi fattori che potrebbero causare un test non riuscito. Se un test ha esito negativo, il primo passaggio deve essere rivedere le impostazioni di configurazione tramite il cmdlet Get-CsVoiceTestConfiguration:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Se le impostazioni sembrano essere configurate correttamente, ripetere l'esecuzione del test, includendo il parametro Verbose:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Il parametro Verbose fornirà un account dettagliato di ogni azione eseguita da Test-CsVoiceTestConfiguration, come illustrato in questo esempio:

VERBOse: caricamento di dial plan: "globale"

VERBOse: caricamento dei criteri vocali: "" RedmondDialPlan ""

Questo account dettagliato potrebbe dare un indizio utile in merito alla posizione in cui il test non è effettivamente riuscito. In caso contrario, puoi quindi usare altri cmdlet di Windows PowerShell (ad esempio Test-CsVoicePolicy) e iniziare metodicamente a verificare i singoli componenti inclusi nelle impostazioni di configurazione del test vocale.

Oltre a ciò, tieni presente che è possibile che un test sia in grado di instradare una chiamata e che sia ancora contrassegnata come un errore. Ciò può verificarsi se si immettono valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e tutte le attese non vengono soddisfatte. Ad esempio, supponiamo che tu immetti la route vocale C come itinerario vocale previsto, ma il test completa effettivamente la chiamata usando la route vocale D. In questo caso, il test verrà contrassegnato come non riuscito perché non è stata usata la route vocale prevista. Se un test non riesce, è possibile rimuovere i valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e quindi eseguire di nuovo il test. Questo ti aiuterà a determinare se l'errore è stato perché la chiamata non è stata completata o perché ti aspetti una cosa e ne hai ricevuto un altro.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

