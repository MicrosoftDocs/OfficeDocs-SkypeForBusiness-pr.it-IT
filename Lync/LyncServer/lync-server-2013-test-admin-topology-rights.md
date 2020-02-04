---
title: 'Lync Server 2013: verificare i diritti della topologia di amministratore'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3681a3328f0e1e659377947919bbfc782f1fea7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Testare i diritti di topologia di amministratore in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Dopo la distribuzione iniziale di Lync Server. Se necessario, se sorgono problemi relativi alle autorizzazioni.</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsSetupPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Per impostazione predefinita, solo gli amministratori di dominio possono abilitare una topologia di Lync Server e apportare grandi modifiche all'infrastruttura di Lync Server. Non si tratta di un problema purché gli amministratori di dominio e gli amministratori di Lync Server siano uno e lo stesso. In molte organizzazioni gli amministratori di Lync Server non detieneno diritti amministrativi per l'intero dominio. Per impostazione predefinita, questo significa che questi amministratori (definiti come membri del gruppo RTCUniversalServerAdmins) non possono apportare modifiche alla topologia di Lync Server. Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di apportare modifiche alla topologia, è necessario assegnare le autorizzazioni di Active Directory necessarie usando il cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

Il cmdlet Test-CsSetupPermission verifica che le autorizzazioni necessarie per installare Lync Server o uno dei relativi componenti siano configurate nel contenitore di Active Directory specificato. Se le autorizzazioni non sono assegnate, è possibile eseguire il cmdlet Grant-CsSetupPermission per assegnare ai membri del gruppo RTCUniversalServerAdmins il diritto di installare e abilitare Lync Server.

<div>


> [!NOTE]  
> Per un elenco dettagliato delle autorizzazioni assegnate da Grant-CsSetupPermission, vedere il post di Blog <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission e Grant-CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per determinare se le autorizzazioni di configurazione sono assegnate per un contenitore di Active Directory, chiama il cmdlet Test-CsSetupPermission. Specificare il nome distinto del contenitore da controllare. Questo comando, ad esempio, verifica le autorizzazioni di configurazione per il contenitore ou = CsServers, DC = litwareinc, DC = com:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se Test-CsSetupPermission determina che le autorizzazioni necessarie sono già state impostate in un contenitore di Active Directory, il cmdlet restituirà il valore true:

True

Se le autorizzazioni non sono impostate, Test-CsSetupPermission restituirà il valore false. Tieni presente che questo valore verrà in genere racchiuso in molti messaggi di avviso. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs\\-001 RTCUniversalServerAdmins; Consentire ExtendedRight; Nessuno Nessuno 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

AVVISO: le voci di controllo di accesso (ACE) nell'oggetto "CN = Computers, DC = litwareinc, DC = com" non sono pronte.

False

AVVISO: l'elaborazione "Test-CsSetupPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante l'esecuzione.

AVVISO: i risultati dettagliati sono disponibili in "C\\:\\Users\\admin\\\\AppData\\local Temp Test-CsSetupPermission-1da99ba6-Abe2-45e4-8b16-dfd244763118. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Anche se esistono eccezioni rare, se Test-CsSetupPermission non riesce in genere significa che le autorizzazioni di configurazione non vengono assegnate per il contenitore di Active Directory specificato. Queste autorizzazioni possono essere assegnate usando il cmdlet Grant-CsSetupPermission. Questo comando, ad esempio, concede le autorizzazioni di configurazione al contenitore di computer nel dominio litwareinc.com:

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

