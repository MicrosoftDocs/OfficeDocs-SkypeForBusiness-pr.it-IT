---
title: 'Lync Server 2013: Gestione di utenti di Exchange ospitati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23289399e4eee4a654b41f2978191a6329739b4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gestione di utenti di Exchange ospitati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Per specificare i servizi di segreteria telefonica per gli utenti di Lync Server 2013 le cui cassette postali si trovano in un servizio ospitato di Exchange, è necessario abilitare gli account utente per la segreteria telefonica ospitata.

<div>


> [!NOTE]  
> Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica all'account utente corrispondente. Il criterio può essere globale, sito o per utente nell'ambito, purché si applichi all'utente che si vuole abilitare. Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>Attributo msExchUCVoiceMailSettings

Lync Server 2013 introduce un nuovo attributo utente denominato **msExchUCVoiceMailSettings**, creato come parte della preparazione dello schema di Active Directory di lync Server 2013. Questo attributo multivalore contiene le impostazioni della segreteria telefonica condivise da Lync Server 2013 e dal servizio ospitato di Exchange.

Il servizio di Exchange ospitata può in alcuni casi impostare il valore dell'attributo msExchUCVoiceMailSettings nel processo di abilitazione della messaggistica unificata di Exchange o durante il processo di trasferimento delle cassette postali in un server di Exchange ospitata. Se questo attributo non è impostato da Exchange, l'amministratore di Lync Server 2013 deve impostarlo eseguendo il cmdlet Set-CsUser, come descritto in precedenza in questo argomento.

Le coppie chiave/valore dell'attributo e i relativi autori sono illustrati nella tabella seguente.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Coppie chiave/valore dell'attributo msExchUCVoiceMailSettings

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valore</th>
<th>Autore</th>
<th>Significato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>L'utente è stato abilitato per l'accesso di messaggistica unificata ospitata da Exchange Server. L'applicazione di routing della messaggistica unificata di Exchange verificherà i criteri di segreteria telefonica ospitata per i dettagli di routing.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>L'utente è stato disabilitato per l'accesso di messaggistica unificata ospitato da Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>L'utente è stato abilitato per l'accesso alla messaggistica unificata ospitata da Lync Server 2013. L'applicazione di routing di Lync Server 2013 ExUM controlla i criteri di segreteria telefonica ospitata dall'utente per i dettagli di routing.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>L'utente è stato disabilitato per l'accesso alla messaggistica unificata ospitata da Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se l'attributo contiene già valori diversi da una delle coppie chiave/valore di Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), un avviso indicherà che l'attributo può essere gestito da un'applicazione diversa. Ad esempio, viene visualizzato un avviso se la coppia chiave/valore ExchangeHostedVoiceMail = 0 o ExchangeHostedVoiceMail = 1 è già presente. In questo caso, è possibile modificare il valore modificando l'Active Directory oppure eseguire il cmdlet seguente per impostare il valore su null:<BR>Set-CsUser – Identity user-HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Abilitazione degli utenti per la segreteria telefonica ospitata

Per consentire alle chiamate di segreteria telefonica di un utente di essere instradate alla messaggistica unificata di Exchange ospitata, è necessario eseguire il cmdlet Set-CsUser per impostare il valore del parametro *HostedVoiceMail* . Questo parametro segnala inoltre a Lync Server 2013 di illuminare l'indicatore "chiama la segreteria telefonica".

  - L'esempio seguente consente di abilitare l'account utente di Pilar Ackerman per la segreteria telefonica ospitata:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    Il cmdlet verifica che un criterio di segreteria telefonica ospitata (globale, a livello di sito o per utente) si applichi a questo utente. Se non viene applicato alcun criterio, il cmdlet non riesce.

  - L'esempio seguente disabilita l'account utente di Pilar Ackerman per la segreteria telefonica ospitata:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Il cmdlet verifica che nessun criterio di segreteria telefonica ospitata (globale, a livello di sito o per utente) si applichi a questo utente. Se un criterio si applica, il cmdlet non riesce.

Per informazioni dettagliate sull'uso del cmdlet Set-CsUser, vedere la documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

