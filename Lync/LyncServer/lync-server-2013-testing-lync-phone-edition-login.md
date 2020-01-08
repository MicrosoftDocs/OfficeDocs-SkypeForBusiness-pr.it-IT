---
title: "Lync Server 2013: verificare l'accesso a Lync Phone Edition"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2cf0dae748cf82e83e86389abf55c55c8c70e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Verificare l'accesso a Lync Phone Edition in Lync Server 2013

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
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsPhoneBootstrap. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsPhoneBootstrap consente agli amministratori di verificare che un utente specifico, usando il numero di telefono e il PIN assegnatigli, sia in grado di accedere al sistema da un dispositivo compatibile con Lync 2013 Phone Edition. (Nessun dispositivo è effettivamente necessario per eseguire il test).

Affinché Test-CsPhoneBootstrap esegua il controllo, il pool di registrar che ospita l'account utente testato deve essere individuabile tramite DHCP. Per determinare se un registrar è individuabile in questo modo, usa il cmdlet Get-CsRegistrarConfiguration e controlla il valore della proprietà EnableDHCPServer. Se questa proprietà è impostata su false, è necessario usare Set-CsRegistrarConfiguration per impostare il valore della proprietà su true e rendere il registrar individuabile tramite DHCP. Questa operazione può essere eseguita anche tramite il server DHCP aziendale e la configurazione delle opzioni specifiche di Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per eseguire il cmdlet Test-CsPhoneBootstrap, è necessario specificare almeno il numero di telefono e il PIN (client Personal Identification Number) per un utente di Lync Server valido. Ad esempio, questo comando verifica l'abilità di accesso per l'utente che ha il numero di telefono 12065551219 e il PIN 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Per un controllo più completo, puoi anche includere l'indirizzo SIP dell'utente. In questo caso, il numero di telefono, il PIN client e l'indirizzo SIP devono essere tutti validi affinché il test abbia successo:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se l'utente specificato è riuscito a connettersi a Lync Server, si riceverà un output simile a questo, con la proprietà Result contrassegnata come **riuscita:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: successo

Latenza: 00:00:06.3981276

Errore

Diagnosi

Se l'utente specificato non è in grado di effettuare una connessione, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:

TargetFqdn: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:04.1993845

Errore: errore-Nessuna risposta ricevuta per il servizio Ticket Web.

Diagnosi

L'output precedente indica che il test non è riuscito perché il servizio ticket web non ha risposto. Questo potrebbe essere dovuto a un problema relativo al servizio stesso oppure potrebbe essere dovuto all'indirizzo SIP, al numero di telefono o al PIN del client passato a Test-CsPhoneBootstrap. Puoi verificare l'indirizzo SIP e il numero di telefono dell'utente usando un comando simile al seguente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Puoi verificare che l'utente abbia un PIN valido usando un comando come segue:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Se Test-CsPhoneBootstrap non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Quando viene incluso il parametro Verbose, Test-CsPhoneBootstrap restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server. Ad esempio, ecco una parte dell'output per un accesso non riuscito, una sessione in cui è stato incluso un PIN errato:

Uso di PIN auth con\\il telefono Ext: 12065551219 pin: 0712

Impossibile ottenere il ticket web

CONTROLLO

\-L'URL del servizio Web è valido e i servizi Web sono funzionali

\-Se si usa\\PhoneNo pin per eseguire l'autenticazione, verificare che corrispondano all'URI dell'utente

\-Se si usa\\l'autenticazione Kerberos NTLM, verificare che siano state fornite credenziali valide

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsPhoneBootstrap potrebbe non riuscire:

  - Potrebbe essere stato specificato un indirizzo SIP non valido. Puoi verificare che un indirizzo SIP sia corretto usando un comando come questo:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Potrebbe essere stato specificato un PIN non valido. Anche se non si riesce a recuperare il numero PIN dell'utente, è possibile verificare che l'utente abbia almeno un numero di PIN usando un comando simile al seguente:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Potrebbe essere stato specificato un numero di telefono non valido. Per verificare il telefono di un utente, è possibile usare un comando simile al seguente:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Il pool di registrazione non è abilitato per DHCP. Per determinare se il pool di registrazione è abilitato per DHCP, eseguire il cmdlet Get-CsRegistrarConfiguration e controllare il valore della proprietà EnableDHCPServer. Ad esempio:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

