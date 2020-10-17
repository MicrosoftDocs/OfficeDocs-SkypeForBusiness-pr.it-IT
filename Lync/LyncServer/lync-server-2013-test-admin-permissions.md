---
title: 'Lync Server 2013: testare le autorizzazioni di amministratore'
description: 'Lync Server 2013: testare le autorizzazioni di amministratore.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568522"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a>Verificare le autorizzazioni di amministratore in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Dopo la distribuzione iniziale di Lync Server. Se necessario, se si verificano problemi relativi alle autorizzazioni.</p></td>
</tr>
<tr class="even">
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsOUPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Quando si installa Lync Server 2013 1 delle attività eseguite dal programma di installazione, vengono fornite al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per la gestione di utenti, computer, contatti, contatti di applicazioni e persone di InetOrg. Se l'ereditarietà delle autorizzazioni disabilitata nel programma di installazione di Active Directory non è in grado di assegnare tali autorizzazioni. Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Lync Server. Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio.

Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie per la gestione degli utenti, dei computer e di altri oggetti siano impostate su un contenitore di Active Directory. Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Si noti che Grant-CsOUPermission possibile assegnare autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins. Non è possibile utilizzare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario. Se si desidera che un utente o un gruppo diverso disponga delle autorizzazioni per la gestione degli utenti, è necessario aggiungere tale utente (o gruppo) al gruppo RTCUniversalUserAdmins.

Per ulteriori informazioni sulle autorizzazioni di unità organizzativa, vedere l'articolo [autorizzazioni l'ereditarietà è disabilitata su computer, utenti o contenitori InetOrgPerson in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per verificare che le autorizzazioni di gestione siano impostate su un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni che si sta verificando. Ad esempio, questo comando consente di controllare se le autorizzazioni utente sono impostate nell'unità organizzativa OU = Redmond, DC = litwareinc, DC = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Per verificare più autorizzazioni utilizzando un singolo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi utilizzando le virgole. Ad esempio, questo comando consente di verificare le autorizzazioni utente, computer e contatti:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta a una sola parola:

Vero

Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore false. Potrebbe essere necessario cercare un momento per trovare questo valore. In genere viene incorporato all'interno di diversi avvisi di accompagnamento. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001 \\ RTCUniversalUserReadOnlyGroup; Consenti; ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

AVVISO: le voci di controllo di accesso (ACE) dell'oggetto "OU = NorthAmerica, DC = atl-cs-001 \\ DC = litwareinc, DC = com" non sono pronte.

False

AVVISO: l'elaborazione di "Test-CsOUPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante la fase di esecuzione.

AVVISO: i risultati dettagliati sono disponibili in "C: \\ Users \\ admin \\ AppData \\ Local \\ temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se Test-CsOUPermission ha esito negativo che in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins. È possibile risolvere il problema e assegnare le autorizzazioni necessarie utilizzando il cmdlet Grant-CsOUPermission. Ad esempio, questo comando fornisce le autorizzazioni di unità organizzativa per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

