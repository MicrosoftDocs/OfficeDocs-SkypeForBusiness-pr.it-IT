---
title: 'Lync Server 2013: verificare le autorizzazioni di amministrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da940b30822a5cfcc1fed302ff3db1f34bd8380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Verificare le autorizzazioni di amministratore in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-18_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsOUPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Quando si installa Lync Server 2013 1 delle attività eseguite dal programma di installazione, il gruppo RTCUniversalUserAdmins offre le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti delle applicazioni e persone InetOrg. Se l'ereditarietà delle autorizzazioni disabilitata nella configurazione di Active Directory non sarà in grado di assegnare tali autorizzazioni. Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Lync Server. Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio.

Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie necessarie per gestire utenti, computer e altri oggetti vengano impostate in un contenitore di Active Directory. Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Tieni presente che Grant-CsOUPermission può assegnare le autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins. Non è possibile usare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario. Se si vuole che un utente o un gruppo diverso disponga delle autorizzazioni di gestione degli utenti, è necessario aggiungere l'utente (o il gruppo) al gruppo RTCUniversalUserAdmins.

Per altre informazioni sulle autorizzazioni dell'unità organizzativa, vedere l'articolo [autorizzazioni l'ereditarietà è disabilitata in computer, utenti o contenitori InetOrgPerson in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni da verificare. Questo comando, ad esempio, controlla se le autorizzazioni utente sono impostate nell'ou ou = Redmond, DC = litwareinc, DC = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Per verificare più autorizzazioni con un solo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi usando le virgole. Questo comando, ad esempio, verifica le autorizzazioni utente, computer e contatto:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se sono già state impostate le autorizzazioni necessarie, Test-CsOUPermission restituirà una risposta di una sola parola:

True

Se non sono impostate le autorizzazioni necessarie, Test-CsOUPermission restituirà il valore false. Potrebbe essere necessario cercare un momento per trovare questo valore. Verrà in genere incorporato all'interno di diversi avvisi di accompagnamento. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs\\-001 RTCUniversalUserReadOnlyGroup; consentire ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

AVVISO: le voci di controllo di accesso (ACE) nell'oggetto "OU = NorthAmerica, DC = atl-cs-\\001 DC = LITWAREINC, DC = com" non sono pronte.

False

AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante l'esecuzione.

AVVISO: i risultati dettagliati sono disponibili in "C\\:\\Users\\admin\\\\AppData\\local Temp Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsOUPermission non riesce, che in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins. È possibile risolvere il problema e assegnare le autorizzazioni necessarie usando il cmdlet Grant-CsOUPermission. Ad esempio, questo comando fornisce le autorizzazioni di UO per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

