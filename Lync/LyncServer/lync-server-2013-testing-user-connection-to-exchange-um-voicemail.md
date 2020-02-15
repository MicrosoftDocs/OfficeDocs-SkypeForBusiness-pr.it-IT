---
title: 'Lync Server 2013: test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae68b9a5fb2e03fd08fbc7cd06507c54a383197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-01_


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
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExUMVoiceMail</strong> . Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet **test-CsExUMVoiceMail** consente agli amministratori di verificare che un utente possa accedere al servizio di messaggistica unificata di Microsoft Exchange Server 2013 e utilizzarlo. A tale scopo, il cmdlet si connette al servizio Messaggistica unificata di Exchange e lascia un messaggio in segreteria telefonica nella cassetta postale specificata. Il messaggio può essere fornito dal sistema o essere contenuto in un file WAV personalizzato registrato personalmente.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Nell'esempio seguente viene verificata la connettività della segreteria telefonica della messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com. Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com. Se necessario, il comando determinerà se il primo utente di test può utilizzare la segreteria telefonica di messaggistica unificata. Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

I comandi mostrati nell'esempio seguente verificano la connettività della segreteria telefonica di messaggistica unificata\\di Exchange per l'utente litwareinc kenmyer. A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell\\per l'utente litwareinc kenmyer. Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **test-CsExUMVoiceMail** possa eseguire il controllo.

Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se l'utente può connettersi alla segreteria telefonica di messaggistica unificata di Exchange.

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

Il comando riportato nell'esempio seguente è una variante del comando mostrato nell'esempio 1. in questo caso, il parametro OutLoggerVariable è incluso per generare un registro dettagliato di ogni passaggio effettuato dal **test-CsExUMVoiceMail** cmdletand l'esito positivo o negativo di ognuno di questi passaggi. A tale scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore del parametro ExumText; che determina l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest. Nel comando finale dell'esempio viene utilizzato il metodo ToXML () per convertire le informazioni del registro in formato XML. I dati XML vengono quindi scritti in un file denominato C:\\logs\\VoicemailTest. XML utilizzando il cmdlet out-file.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: esito positivo

Latenza: 00:00:02.9911345

Messaggio di errore:

Diagnosi

Se l'utente specificato non è in grado di connettersi alla segreteria telefonica, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:

AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo

nome di dominio (FQDN). Utilizzo del numero di porta di registrazione predefinito. Eccezione

System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.

a

Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN di destinazione: atl-cs-001.litwareinc.com

Risultato: errore

Latenza: 00:00:00

Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa

non ha risposto correttamente dopo un determinato periodo di tempo oppure

connessione stabilita non riuscita perché l'host connesso ha

non è stato possibile rispondere 10.188.116.96:5061

Eccezione interna: un tentativo di connessione non è riuscito perché il

la parte connessa non ha risposto correttamente dopo un periodo di

Data/ora o connessione stabilita non riuscita perché host connesso

non è riuscito a rispondere 10.188.116.96:5061

Diagnosi

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui **test-CsExUMVoiceMail** potrebbe non riuscire:

  - È stato specificato un valore di parametro non corretto. Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo. Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.

  - Questo comando avrà esito negativo se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

