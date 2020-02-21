---
title: "Lync Server 2013: test dell'account di accesso di Lync Phone Edition"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce22e6c7f5fb48132f3f67c79c33daaa568d93ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Test dell'account di accesso di Lync Phone Edition in Lync Server 2013

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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsPhoneBootstrap. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsPhoneBootstrap consente agli amministratori di verificare che un determinato utente, che utilizza il numero di telefono e il PIN assegnato a lui, sia in grado di accedere al sistema da un dispositivo compatibile con Lync 2013 Phone Edition. (Nessun dispositivo è effettivamente necessario per eseguire il test).

Per consentire al cmdlet Test-CsPhoneBootstrap di effettuare il controllo, il pool di registrazione che ospita l'account utente su cui viene eseguito il test deve risultare individuabile mediante protocollo DHCP. Per determinare se un servizio di registrazione è individuabile in questo modo, utilizzare il cmdlet Get-CsRegistrarConfiguration e controllare il valore della proprietà EnableDHCPServer. Se questa proprietà è impostata su false, è necessario utilizzare Set-CsRegistrarConfiguration per impostare il valore della proprietà su true e rendere individuabile il registrar tramite DHCP. È possibile eseguire questa operazione anche utilizzando il server DHCP aziendale e la configurazione delle opzioni specifiche di Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per eseguire il cmdlet Test-CsPhoneBootstrap, è necessario fornire almeno il numero di telefono e il PIN (Personal Identification Number) client per un utente di Lync Server valido. Ad esempio, questo comando verifica la capacità di accesso per l'utente che ha il numero di telefono 12065551219 e il PIN 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Per un controllo più esaustivo, è possibile includere anche l'indirizzo SIP dell'utente. In tal caso, il numero di telefono, il PIN client e l'indirizzo SIP devono essere tutti validi affinché il test venga eseguito correttamente:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'utente specificato è in grado di connettersi a Lync Server, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:06.3981276

Errore

Diagnosi

Se l'utente specificato non è in grado di effettuare una connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:04.1993845

Error: ERROR-No Response Received for Web-Ticket Service.

Diagnosi

L'output precedente dichiara che il test non ha avuto esito positivo perché il servizio ticket web non ha risposto. Questo potrebbe essere dovuto a un problema con il servizio stesso oppure potrebbe essere dovuto a un indirizzo SIP, a un numero di telefono o a un PIN client passato a Test-CsPhoneBootstrap. È possibile verificare l'indirizzo SIP e il numero di telefono dell'utente utilizzando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

È possibile verificare che l'utente disponga di un PIN valido utilizzando un comando come indicato di seguito:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Se Test-CsPhoneBootstrap ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPhoneBootstrap restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, di seguito viene fornita una parte dell'output per un accesso non riuscito, una sessione in cui è stato incluso un PIN errato:

Utilizzo dell'autenticazione PIN con\\il telefono Ext: 12065551219 pin: 0712

Impossibile ottenere il ticket web

CONTROLLO

\-L'URL del servizio Web è valido e i servizi Web sono funzionali

\-Se si utilizza\\il pin di PhoneNo per eseguire l'autenticazione, assicurarsi che corrispondano all'URI dell'utente.

\-Se si utilizza\\l'autenticazione Kerberos NTLM, accertarsi di aver specificato le credenziali valide

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsPhoneBootstrap potrebbe non riuscire:

  - Potrebbe essere stato specificato un indirizzo SIP non valido. È possibile verificare che un indirizzo SIP sia corretto utilizzando un comando simile al seguente:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Potrebbe essere stato specificato un PIN non valido. Anche se non è possibile recuperare il numero di PIN dell'utente, è possibile verificare che l'utente disponga almeno di un numero di PIN utilizzando un comando simile al seguente:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Potrebbe essere stato specificato un numero di telefono non valido. È possibile verificare il numero di telefono di un utente utilizzando un comando simile al seguente:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Il pool di registrazione non è abilitato per il protocollo DHCP. Per determinare se il pool di registrazione è abilitato per DHCP, eseguire il cmdlet Get-CsRegistrarConfiguration e controllare il valore della proprietà EnableDHCPServer. Ad esempio:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

