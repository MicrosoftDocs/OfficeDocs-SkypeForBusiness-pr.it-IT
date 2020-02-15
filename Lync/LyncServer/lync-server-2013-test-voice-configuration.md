---
title: 'Lync Server 2013: testare la configurazione vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Testare la configurazione vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-20_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsVoiceTestConfiguration. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Lync Server include diversi cmdlet di Windows PowerShell, ad esempio Test-CsVoiceRoute e Test-CsVoicePolicy, Test-CsTrunkConfiguration, che consentono di verificare che i singoli componenti dell'infrastruttura VoIP aziendale, ovvero le route vocali, la voce i criteri, trunk SIP, funzionano come previsto.

Anche se è importante con VoIP aziendale che tutti i singoli pezzi funzionino: è possibile avere una route vocale valida, un criterio vocale valido e un trunk SIP valido, ma gli utenti non possono ancora effettuare o ricevere chiamate telefoniche. Per questo motivo, Lync Server fornisce anche la possibilità di creare configurazioni di test vocale. Le configurazioni di test vocale rappresentano scenari di VoIP aziendale comuni: è possibile specificare elementi quali una route vocale, un criterio vocale e un dial plan e quindi verificare che i singoli elementi siano in grado di collaborare per fornire il servizio telefonico. È inoltre possibile convalidare le aspettative in un determinato scenario. Si supponga, ad esempio, che si preveda che la combinazione del dial plan A e del criterio vocale B comporterà l'instradamento delle chiamate tramite la route vocale C. È possibile immettere la route vocale C come ExpectedRoute. Quando si esegue il test, se la route vocale C non viene utilizzata, la verifica verrà contrassegnata come non riuscita.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Prima di testare le raccolte di configurazione vocale utilizzando Windows PowerShell, è necessario utilizzare il cmdlet Get-CsVoiceTestConfiguration per recuperare un'istanza di queste impostazioni di configurazione. Tale istanza deve quindi essere inviata tramite pipe al cmdlet Test-CsVoiceTestConfiguration. Ad esempio:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Per convalidare contemporaneamente tutte le impostazioni di configurazione del test vocale, utilizzare questo comando:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Il cmdlet Test-CsVoiceTestConfiguration segnala se un test non è riuscito o ha avuto esito positivo e fornisce ulteriori informazioni su ogni test corretto, ad esempio la regola di conversione, la route vocale e l'utilizzo PSTN utilizzati per completare l'attività:

Risultato: esito positivo

TranslatedNumber: + 15551234

MatchingRule: Description =; Pattern = ^ (\\d{4}) $; Translation = + 1\\d; Name = test; IsInternalExtension = false

FirstMatchingRoute: sito: Redmond

MatchingUsage: local

Se il test ha esito negativo, il risultato viene segnalato come non riuscito:

Risultato: esito negativo

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Poiché la configurazione del test vocale verifica vari elementi, tra cui criteri vocali, dial plan, route vocali e così via, esistono diversi fattori che potrebbero causare un test non riuscito. Se un test ha esito negativo, il primo passaggio consiste nell'esaminare le impostazioni di configurazione stesse utilizzando il cmdlet Get-CsVoiceTestConfiguration:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Se le impostazioni sembrano essere configurate correttamente, rieseguire il test con il parametro Verbose:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Il parametro Verbose fornirà un account dettagliato di ogni azione intrapresa da Test-CsVoiceTestConfiguration, come illustrato nell'esempio seguente:

VERBOse: Loading dial plan: "globale"

VERBOse: caricamento del criterio vocale: "RedmondDialPlan"

Questo account dettagliato potrebbe fornire un indizio utile in merito alla posizione in cui il test ha effettivamente avuto esito negativo. In caso contrario, è possibile utilizzare altri cmdlet di Windows PowerShell (come Test-CsVoicePolicy) e iniziare metodicamente a verificare i singoli componenti inclusi nelle impostazioni di configurazione del test vocale.

Inoltre, tenere presente che è possibile che un test sia in grado di instradare una chiamata ma che sia ancora contrassegnata come un errore. Ciò può verificarsi se si immettono valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e una qualsiasi di queste aspettative non viene soddisfatta. Si supponga, ad esempio, di immettere la route vocale C come route vocale prevista, ma il test esegue effettivamente la chiamata tramite la route vocale D. In tal caso, la verifica verrà contrassegnata come non riuscita perché non è stata utilizzata la route vocale prevista. Se un test ha esito negativo, è possibile rimuovere i valori per ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e quindi rieseguire il test. Ciò consentirà di stabilire se l'errore è dovuto al fatto che la chiamata non è stata completata o perché si prevede una cosa e ne viene effettivamente ricevuta un'altra.

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

