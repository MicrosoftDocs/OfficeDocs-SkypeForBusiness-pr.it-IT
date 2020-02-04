---
title: 'Lync Server 2013: test del servizio di replica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Test del servizio di replica in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsReplica</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsReplica** verifica che il servizio di replica di Lync Server 2013 sia in uso nel computer locale. Il cmdlet **Test-CsReplica** esegue le attività seguenti:

  - controllo dello stato dell'agente di replica e dei servizi di agente di registrazione centralizzato

  - Verifica della apertura delle porte necessarie in Windows Firewall

  - Verificare che esistano i gruppi di sicurezza di Active Directory e di computer locali necessari.

Tieni presente che questo cmdlet deve essere eseguito localmente. In altri casi, deve essere eseguito nello stesso computer in cui è in esecuzione il servizio di replica. Non sono disponibili opzioni per l'eseguire il cmdlet **Test-CsReplica** su un server remoto.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il comando mostrato nell'esempio 1 verifica il servizio di replica di Lync Server 2013 nel computer locale. In questo esempio, il parametro Verbose viene usato per garantire che le informazioni sul test, incluso l'eventuale errore o il successo del test e la posizione del report generato dal test, vengano visualizzate sullo schermo.

    Test-CsReplica -Verbose

L'esempio 2 è una variante del comando mostrato nell'esempio 1. In questo caso, il parametro report viene incluso per specificare un percorso e un nome di cartella per il report generato dal test. Se non si specifica un percorso del report, al report verrà assegnato un nome generato automaticamente in modo simile al seguente:

C:\\utenti\\Administrator. litwareinc\\AppData\\locale\\temp\\1\\test-CS-replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Inserire il corpo della sezione qui.

VERBOse: creazione di un nuovo file di log\\"\\C\\:\\gli\\utenti\\che provano la prova locale Temp di AppData-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".

VERBOse: creazione di un nuovo file di log\\"\\C\\:\\gli\\utenti\\che provano la prova locale Temp di AppData-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".

VERBOse: l'elaborazione "Test-CsReplica" è stata completata correttamente.

VERBOse: i risultati dettagliati possono essere trovati in "\\C\\:\\utenti\\che\\provano la prova locale temp\\di AppData-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".

VERBOse: creazione di un nuovo file di log

"C:\\utenti\\che\\testano\\AppData\\\\locale\\Temp 2 Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e

d3bd0e4a083. xml ".

VERBOse: creazione di un nuovo file di log

"C:\\utenti\\che\\testano\\AppData\\\\locale\\Temp 2 Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e

d3bd0e4a083. html ".

AVVISO: Test-CsReplica non riuscito.

AVVISO: i risultati dettagliati possono essere trovati in

"C:\\utenti\\che\\testano\\AppData\\\\locale\\Temp 2 Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e

d3bd0e4a083. html ".

Test-CsReplica: l'esecuzione del comando non è riuscita: l'accesso richiesto al registro di sistema non è

consentiti.

At line: 1 char: 1

\+Test-CsReplica-verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], sicurezza

Eccezione

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. Rtc. Management. deploy

mento. TestReplicaCmdlet

PS C:\\test\\degli utenti\>

PS C:\\utenti\\che\> provano test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo

nome di dominio (FQDN). Uso del numero di porta registrar predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: non è stato assegnato un utente di test

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Verificare la configurazione degli utenti di test.

At line: 1 char: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. Rtc. Management. synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui **Test-CsReplica** potrebbe non riuscire:

  - Potrebbe essersi verificato un problema più grande con l'agente di replica e i servizi di agente di registrazione centralizzati

  - Le porte obbligatorie potrebbero non essere aperte in Windows Firewall

  - I gruppi di sicurezza di Active Directory e di computer locali necessari potrebbero non esistere

</div>

</div>

<span> </span>

</div>

</div>

</div>

