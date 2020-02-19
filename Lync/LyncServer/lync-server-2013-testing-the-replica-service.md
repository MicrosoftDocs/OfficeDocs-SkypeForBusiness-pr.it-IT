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
ms.openlocfilehash: 2784796d0eaca5d37aa841ee3db351a841c3c397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Test del servizio di replica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-03_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsReplica</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **Test-CsReplica** verifica che il servizio di replica di Lync Server 2013 sia in esecuzione nel computer locale. Il cmdlet **Test-CsReplica** consente di eseguire le attività seguenti:

  - controllo dello stato dell'agente di replica e dei servizi dell'agente di registrazione centralizzato

  - Verifica che le porte necessarie siano state aperte in Windows Firewall

  - Verificare che esistano i gruppi di sicurezza di Active Directory e del computer locale necessari.

Si noti che questo cmdlet deve essere eseguito localmente. In altri casi, deve essere eseguito nello stesso computer in cui è in esecuzione il servizio di replica. Non sono disponibili opzioni per l'esecuzione del cmdlet **Test-CsReplica** su un server remoto.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il comando riportato nell'esempio 1 verifica il servizio di replica di Lync Server 2013 nel computer locale. In questo esempio viene utilizzato il parametro Verbose per garantire che le informazioni sul test, tra cui l'eventuale esito negativo o esito positivo del test e la posizione del report generato dal test, vengano visualizzate sullo schermo.

    Test-CsReplica -Verbose

L'esempio 2 è una variazione del comando illustrato nell'esempio 1. In questo caso, il parametro report è incluso per specificare un percorso e un nome di cartella per il report generato dal test. Se non si specifica un percorso, al report verrà assegnato un nome generato automaticamente simile al seguente:

C:\\Users\\Administrator.\\litwareinc\\AppData\\Local\\temp\\1 test-CS-replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Inserire qui il corpo della sezione.

VERBOse: creazione di un nuovo file di registro\\"\\C\\:\\utenti\\che\\testano la temperatura locale Test-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".

VERBOse: creazione di un nuovo file di registro\\"\\C\\:\\utenti\\che\\testano la temperatura locale Test-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".

VERBOse: l'elaborazione "Test-CsReplica" è stata completata correttamente.

VERBOse: i risultati dettagliati sono disponibili in "C\\:\\Users testing\\AppData\\Local\\temp\\Test-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".

VERBOse: creazione di un nuovo file di registro

"C:\\utenti\\che\\eseguono\\il\\testing di AppData Local temp\\2\\Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e

d3bd0e4a083. xml ".

VERBOse: creazione di un nuovo file di registro

"C:\\utenti\\che\\eseguono\\il\\testing di AppData Local temp\\2\\Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e

d3bd0e4a083. html ".

AVVISO: Test-CsReplica non riuscito.

AVVISO: i risultati dettagliati sono disponibili all'indirizzo

"C:\\utenti\\che\\eseguono\\il\\testing di AppData Local temp\\2\\Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e

d3bd0e4a083. html ".

Test-CsReplica: esecuzione del comando non riuscita: non è stato richiesto l'accesso al registro di sistema

consentiti.

At line: 1 char: 1

\+Test-CsReplica-verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], sicurezza

Eccezione

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. Rtc. Management. deploy

mento. TestReplicaCmdlet

PS C:\\test\\degli utenti\>

PS C:\\utenti\\che\> testano test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo

nome di dominio (FQDN). Utilizzo del numero di porta di registrazione predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: non è stato assegnato un utente di test

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Verificare la configurazione dell'utente di test.

At line: 1 char: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. Rtc. Management. synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **Test-CsReplica** potrebbe non riuscire:

  - Potrebbe verificarsi un problema maggiore con l'agente di replica e i servizi agente di registrazione centralizzato

  - Le porte necessarie potrebbero non essere aperte nel firewall di Windows

  - Potrebbero non esistere i gruppi di sicurezza di Active Directory e del computer locale necessari

</div>

</div>

<span> </span>

</div>

</div>

</div>

