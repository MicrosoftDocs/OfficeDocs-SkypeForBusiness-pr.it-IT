---
title: Verifica della configurazione dell'account Kerberos assegnato a un sito
description: Verifica della configurazione dell'account Kerberos assegnato a un sito.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560692"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Verifica della configurazione dell'account Kerberos assegnato a un sito in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsKerberosAccountAssignment. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsKerberosAccountAssignment consente di verificare che un account Kerberos sia associato a un determinato sito, che questo account sia configurato correttamente e che l'account funzioni come previsto. Gli account Kerberos sono account computer che possono fungere da entità di autenticazione per tutti i computer di un sito in cui è in esecuzione Internet Information Server (IIS). Poiché tali account utilizzano il protocollo di autenticazione Kerberos, gli account sono noti come account Kerberos e il nuovo processo di autenticazione è noto come autenticazione Web Kerberos. In questo modo è possibile gestire tutti i server IIS utilizzando un singolo account.

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per impostazione predefinita, Test-CsKerberosAccountAssignment Visualizza un output molto poco visualizzato sullo schermo. Al contrario, le informazioni restituite dal cmdlet vengono scritte in un file HTML. Per questo motivo, si consiglia di includere il parametro Verbose e il parametro report ogni volta che si esegue Test-CsKerberosAccountAssignment. Il parametro Verbose fornirà un output leggermente più dettagliato sullo schermo durante l'esecuzione del cmdlet. Il parametro report consente di specificare un percorso di file e un nome di file per il file HTML generato da Test-CsKerberosAccountAssignment. Se non si include il parametro report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

Quando si esegue il Test-CsKerberosAccountAssignment, è inoltre necessario specificare un'identità del sito. Gli account Kerberos vengono assegnati nell'ambito del sito.

Il comando seguente consente di eseguire Test-CsKerberosAccountAssignment e di salvare l'output in un file denominato C: \\ Logs \\KerberosTest.html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Il cmdlet Test-CsKerberosAccountAssignment non restituisce una semplice indicazione di esito positivo o negativo. Al contrario, è necessario visualizzare il file HTML generato tramite Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsKerberosAccountAssignment potrebbero non riuscire:

  - È possibile che sia stata specificata un'identità di sito non corretta. Per restituire un elenco di identità del sito valido, utilizzare questo comando:
    
        Get-CsSite | Select-Identity Identity
    
    L'identità di un sito in genere è simile alla seguente:
    
    sito: Redmond

  - Il sito specificato potrebbe non disporre di un account Kerberos assegnato. È possibile determinare se un account Kerberos è assegnato o meno a un sito eseguendo un comando simile al seguente:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - È possibile che l'account Kerberos disponga di una password non valida. Se viene visualizzato il messaggio di errore riportato di seguito nel report, è probabile che sia necessario reimpostare la password dell'account Kerberos:
    
    InvalidKerberosConfiguration: la configurazione Kerberos non è valida.
    
    InvalidKerberosConfiguration: la configurazione Kerberos in atl-cs001.litwareinc.com non è valida. L'account assegnato previsto è litwareinc \\ kerberostest. Assicurarsi che l'account non sia scaduto e che la password configurata sul computer corrisponda alla password di Active Directory dell'account.
    
    È possibile impostare la password utilizzando il cmdlet [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

