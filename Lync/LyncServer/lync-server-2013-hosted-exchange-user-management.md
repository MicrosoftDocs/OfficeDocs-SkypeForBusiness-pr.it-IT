---
title: 'Lync Server 2013: gestione degli utenti di Exchange ospitata'
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
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504203"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gestione degli utenti di Exchange ospitati in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Per fornire servizi di segreteria telefonica per gli utenti di Lync Server 2013 le cui cassette postali si trovano in un servizio di Exchange ospitato, è necessario abilitare gli account utente per la segreteria telefonica ospitata.

<div>


> [!NOTE]  
> Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica all'account utente corrispondente. I criteri possono avere ambito globale, a livello di sito o per utente, purché siano applicabili all'utente da abilitare. Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>Attributo msExchUCVoiceMailSettings

Lync Server 2013 introduce un nuovo attributo utente denominato **msExchUCVoiceMailSettings**, creato come parte della preparazione dello schema di Active Directory di lync Server 2013. Questo attributo multivalore contiene le impostazioni della segreteria telefonica condivise da Lync Server 2013 e il servizio Exchange ospitato.

Il servizio Exchange ospitato può in alcuni casi impostare il valore dell'attributo msExchUCVoiceMailSettings nel processo di abilitazione della messaggistica unificata di Exchange oppure durante il trasferimento di cassette postali in un computer Exchange Server ospitato. Se questo attributo non è impostato da Exchange, l'amministratore di Lync Server 2013 deve impostarlo eseguendo il cmdlet Set-CsUser, come descritto in precedenza in questo argomento.

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
<th>Author</th>
<th>Significato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>L'utente è stato abilitato per l'accesso alla messaggistica unificata ospitata da Exchange Server. L'applicazione di routing della messaggistica unificata di Exchange verificherà i criteri di segreteria telefonica ospitata per i dettagli del routing.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>L'utente è stato disabilitato per l'accesso alla messaggistica unificata ospitata da Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>L'utente è stato abilitato per l'accesso alla messaggistica unificata ospitata da Lync Server 2013. L'applicazione di routing Lync Server 2013 ExUM verificherà i criteri di segreteria telefonica ospitata dell'utente per i dettagli del routing.</p></td>
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
> Se l'attributo ha già valori diversi da una delle coppie chiave/valore di Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), un avviso indicherà che l'attributo può essere gestito da un'altra applicazione. Questo messaggio di avviso verrà ad esempio visualizzato se la coppia chiave/valore ExchangeHostedVoiceMail=0 o ExchangeHostedVoiceMail=1 è già presente. In questo caso, è possibile modificare il valore in Active Directory o eseguire il cmdlet seguente per impostarlo su null:<BR>Set-CsUser –identity user –HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Abilitazione degli utenti per la segreteria telefonica ospitata

Per consentire l'instradamento delle chiamate alla segreteria telefonica di un utente nella messaggistica unificata di Exchange ospitata, è necessario eseguire il cmdlet Set-CsUser per impostare il valore del parametro *HostedVoiceMail*. Questo parametro segnala inoltre che Lync Server 2013 accende l'indicatore di "segreteria telefonica chiamata".

  - Nell'esempio seguente l'account utente di Luisa Cazzaniga viene abilitato per la segreteria telefonica ospitata:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    Il cmdlet verifica che i criteri di segreteria telefonica ospitata (globali, a livello di sito o per utente) siano applicabili all'utente. Se nessun criterio è applicabile il cmdlet non riesce.

  - Nell'esempio seguente l'account utente di Luisa Cazzaniga viene disabilitato per la segreteria telefonica ospitata:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Il cmdlet verifica che nessun criterio di segreteria telefonica ospitata (globali, a livello di sito o per utente) sia applicabile all'utente. Se un criterio è applicabile il cmdlet non riesce.

Per informazioni dettagliate sull'utilizzo del cmdlet Set-CsUser, vedere la documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

