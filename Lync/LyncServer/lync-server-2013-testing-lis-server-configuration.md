---
title: 'Lync Server 2013: test della configurazione del server LIS'
description: 'Lync Server 2013: test della configurazione del server LIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560612"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Test della configurazione del server LIS in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsLisConfiguration. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsLisConfiguration verifica la possibilità di contattare il servizio Web LIS. Se il servizio Web può essere contattato, il test sarà considerato un esito positivo, indipendentemente dal fatto che sia possibile trovare posizioni specifiche.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

È possibile eseguire il cmdlet Test-CsLisConfguration utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server. Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare. Ad esempio:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account. È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsLisConfiguration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se la LIS è configurata correttamente, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.1616913

Errore

Diagnosi

Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Errore: 11004, il nome richiesto è valido ma nessun dato del richiesto

il tipo è stato trovato

Diagnosi

Test-CsLisConfiguration: nessun cluster corrispondente trovato nella topologia.

Ad esempio, nell'output precedente è inclusa la nota "Nessun cluster corrispondente trovato nella topologia". Questo indica in genere un problema con il server perimetrale: l'LIS che utilizza il server perimetrale per connettersi al provider di servizi e convalidare gli indirizzi.

Se Test-CsLisConfiguration ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando viene incluso il parametro Verbose, Test-CsLisConfiguration restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio:

Servizio informazioni percorso di chiamata.

Percorso servizio = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

PortId =

PortIdSubType = tipo non definito

Mac

Eccezione ' richiesta di servizio Web informazioni percorso non riuscita con un codice di risposta Item400'. si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTrsnactions. Workflows. STLisConfigurationWorkflow.

Se si esamina l'output precedente da vicino, si noterà che il cmdlet ha avuto esito negativo dopo la chiamata al servizio informazioni percorso. Uno dei parametri che sono stati utilizzati in tale chiamata è stato il seguente:

BssId = 5

Questo non è un valore valido per l'identificatore del set di servizi di base (BssID). Al contrario, un BssID dovrebbe essere simile al seguente:

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsLisConfiguration potrebbero non riuscire:

  - È stato specificato un valore di parametro non corretto. Come illustrato nell'esempio precedente, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

