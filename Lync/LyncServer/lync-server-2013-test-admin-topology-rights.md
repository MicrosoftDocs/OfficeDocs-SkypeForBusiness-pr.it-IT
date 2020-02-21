---
title: 'Lync Server 2013: testare i diritti relativi alla topologia di amministratore'
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
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Testare i diritti relativi alla topologia di amministratore in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-08_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsSetupPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Per impostazione predefinita, solo gli amministratori di dominio possono abilitare una topologia di Lync Server e apportare modifiche importanti all'infrastruttura di Lync Server. Non si tratta di un problema a condizione che gli amministratori di dominio e gli amministratori di Lync Server siano identici. In molte organizzazioni gli amministratori di Lync Server non contengono diritti amministrativi per l'intero dominio. Per impostazione predefinita, questo significa che tali amministratori (definiti come membri del gruppo RTCUniversalServerAdmins) non possono apportare modifiche alla topologia di Lync Server. Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di apportare modifiche alla topologia, è necessario assegnare le autorizzazioni di Active Directory necessarie utilizzando il cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

Il cmdlet Test-CsSetupPermission verifica che le autorizzazioni necessarie per l'installazione di Lync Server o di uno dei relativi componenti siano configurate nel contenitore di Active Directory specificato. Se le autorizzazioni non sono assegnate, è possibile eseguire il cmdlet Grant-CsSetupPermission per assegnare ai membri del gruppo RTCUniversalServerAdmins il diritto di installare e abilitare Lync Server.

<div>


> [!NOTE]  
> Per un elenco dettagliato delle autorizzazioni assegnate da Grant-CsSetupPermission, vedere il post di Blog <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission e Grant-CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per determinare se le autorizzazioni di installazione sono assegnate a un contenitore di Active Directory, chiamare il cmdlet Test-CsSetupPermission. Specificare il nome distinto del contenitore da controllare. Ad esempio, questo comando consente di verificare le autorizzazioni di installazione sul contenitore ou = CsServers, DC = litwareinc, DC = com:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsSetupPermission determina che le autorizzazioni necessarie sono già state impostate su un contenitore di Active Directory, il cmdlet restituirà il valore true:

True

Se le autorizzazioni non sono impostate, Test-CsSetupPermission restituirà il valore false. Si noti che questo valore verrà in genere racchiuso in molti messaggi di avviso. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs\\-001 RTCUniversalServerAdmins; Consentire ExtendedRight; Nessuno Nessuno 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

AVVISO: le voci di controllo di accesso (ACE) dell'oggetto "CN = Computers, DC = litwareinc, DC = com" non sono pronte.

False

AVVISO: l'elaborazione di "Test-CsSetupPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante la fase di esecuzione.

AVVISO: i risultati dettagliati sono disponibili in "C\\:\\Users\\admin\\\\AppData\\local Temp Test-CsSetupPermission-1da99ba6-Abe2-45e4-8b16-dfd244763118. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Sebbene esistano eccezioni rare, se Test-CsSetupPermission ha esito negativo che in genere significa che le autorizzazioni di installazione non sono assegnate per il contenitore di Active Directory specificato. Tali autorizzazioni possono essere assegnate utilizzando il cmdlet Grant-CsSetupPermission. Ad esempio, questo comando concede le autorizzazioni di installazione al contenitore computer nel dominio litwareinc.com:

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

