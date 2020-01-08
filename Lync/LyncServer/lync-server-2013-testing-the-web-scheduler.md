---
title: "Lync Server 2013: testare l'utilità di pianificazione Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Test della utilità di pianificazione Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-11-03_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsWebScheduler</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsWebScheduler** consente di determinare se un utente specifico può pianificare una riunione usando l'utilità di pianificazione Web. L'utilità di pianificazione Web consente agli utenti che non hanno eseguito Outlook di pianificare riunioni online. Tra le altre cose, questa nuova funzionalità (che incorpora la funzionalità disponibile nello strumento utilità di pianificazione Web inclusa in Microsoft Lync Server 2010 Resource Kit) consente agli utenti di:

  - Pianificare una nuova riunione online.

  - Elenca tutte le riunioni pianificate.

  - Visualizzare/modificare una riunione esistente.

  - Eliminare una riunione esistente.

  - Inviare un invito tramite posta elettronica ai partecipanti alla riunione usando un server di posta elettronica SMTP preconfigurato.

  - Partecipare a una conferenza esistente.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Nell'esempio seguente viene verificata l'utilità di pianificazione Web per il pool atl-cs-001.litwareinc.com. Questo comando funzionerà solo se gli utenti di test sono definiti per il pool atl-cs-001.litwareinc.com. Se necessario, il comando determinerà se il primo utente di test può pianificare una riunione online usando l'utilità di pianificazione Web.

Se gli utenti di test non sono definiti, il comando avrà esito negativo perché non conosce l'utente a cui eseguire l'accesso. Se non sono stati definiti utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'utente che deve essere usato dal comando durante il tentativo di accesso.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

I comandi mostrati nel prossimo esempio consentono di verificare la capacità di un utente specifico\\(litwareinc kenmeyer) di pianificare una riunione online con l'utilità di pianificazione Web. A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Ken Meyer. Poiché il nome di accesso litwareinc\\kenmeyer è incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Ken Meyer. L'oggetto credenziale risultante viene quindi archiviato in una variabile denominata $cred 1.

Il secondo comando verifica quindi se l'utente può accedere al pool atl-cs-001.litwareinc.com e pianificare una riunione online. Per eseguire questa attività, viene chiamato il cmdlet **Test-CsWebScheduler** , insieme a tre parametri: TargetFqdn (il nome di dominio completo del pool di registrar); UserCredential (l'oggetto Windows PowerShell che contiene le credenziali utente di Pilar Ackerman); e UserSipAddress (l'indirizzo SIP che corrisponde alle credenziali utente fornite).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utilità di pianificazione Web è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita**:

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

Risultato: successo

Latenza: 00:00:00

Messaggio di errore:

Diagnosi

Se l'utilità di pianificazione Web non è configurata correttamente, il risultato verrà visualizzato come **errore**e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:

AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo

nome di dominio (FQDN). Uso del numero di porta registrar predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com

URI di destinazione:

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: nessun cluster corrispondente trovato nella topologia.

Diagnosi

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **Test-CsWebScheduler** potrebbe non riuscire:

  - È stato specificato un valore di parametro errato. Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.

  - Questo comando non riuscirà se l'utilità di pianificazione Web non è stata configurata correttamente o non è stata ancora distribuita.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

