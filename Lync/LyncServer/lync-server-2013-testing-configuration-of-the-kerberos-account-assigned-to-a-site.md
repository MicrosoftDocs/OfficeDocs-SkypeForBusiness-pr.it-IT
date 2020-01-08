---
title: Verifica della configurazione dell'account Kerberos assegnato a un sito
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Verifica della configurazione dell'account Kerberos assegnato a un sito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-05_


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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsKerberosAccountAssignment. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsKerberosAccountAssignment consente di verificare che un account Kerberos sia associato a un sito specifico, che l'account sia configurato correttamente e che l'account funzioni come previsto. Gli account Kerberos sono account computer che possono fungere da entità di autenticazione per tutti i computer di un sito che eseguono Internet Information Server (IIS). Poiché questi account usano il protocollo di autenticazione Kerberos, gli account sono noti come account Kerberos e il nuovo processo di autenticazione è noto come autenticazione Web Kerberos. In questo modo è possibile gestire tutti i server IIS con un solo account.

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per impostazione predefinita, Test-CsKerberosAccountAssignment Visualizza un output molto piccolo sullo schermo. Le informazioni restituite dal cmdlet vengono invece scritte in un file HTML. Per questo motivo, è consigliabile includere il parametro Verbose e il parametro report ogni volta che si esegue Test-CsKerberosAccountAssignment. Il parametro Verbose fornirà un output leggermente più dettagliato sullo schermo durante l'esecuzione del cmdlet. Il parametro report consente di specificare un percorso file e un nome file per il file HTML generato da Test-CsKerberosAccountAssignment. Se non si include il parametro di report, il file HTML verrà salvato automaticamente nella cartella utenti e verrà assegnato un nome simile al seguente: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

Quando si esegue Test-CsKerberosAccountAssignment, è necessario specificare anche un'identità del sito. Gli account Kerberos vengono assegnati nell'ambito del sito.

Il comando seguente esegue Test-CsKerberosAccountAssignment e salva l'output in un file denominato C:\\logs\\KerberosTest. html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Il cmdlet Test-CsKerberosAccountAssignment non restituisce una semplice indicazione di esito positivo o negativo. È invece necessario visualizzare il file HTML generato usando Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsKerberosAccountAssignment potrebbe non riuscire:

  - Potrebbe essere stata specificata un'identità di sito non corretta. Per restituire un elenco di identità del sito valido, usare questo comando:
    
        Get-CsSite | Select-Identity Identity
    
    L'identità di un sito in genere è simile alla seguente:
    
    sito: Redmond

  - Al sito specificato potrebbe non essere assegnato un account Kerberos. Per determinare se un account Kerberos viene assegnato o meno a un sito, è possibile eseguire un comando simile al seguente:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - L'account Kerberos potrebbe avere una password non valida. Se viene visualizzato il messaggio di errore seguente nel report, è probabile che sia necessario reimpostare la password dell'account Kerberos:
    
    InvalidKerberosConfiguration: la configurazione Kerberos non è valida.
    
    InvalidKerberosConfiguration: la configurazione Kerberos in atl-cs001.litwareinc.com non è valida. L'account assegnato previsto è litwareinc\\kerberostest. Verificare che l'account non sia scaduto e che la password configurata nel computer corrisponda alla password di Active Directory dell'account.
    
    Puoi impostare la password usando il cmdlet [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

