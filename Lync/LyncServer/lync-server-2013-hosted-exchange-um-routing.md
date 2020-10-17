---
title: 'Lync Server 2013: routing della messaggistica unificata di Exchange ospitata'
description: 'Lync Server 2013: routing della messaggistica unificata di Exchange ospitata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72fbdee5550ae53d5ff5e7513ea384cedad62c5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550132"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Routing della messaggistica unificata di Exchange ospitata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

L'applicazione di routing della messaggistica unificata di Exchange viene eseguita nel front end server per instradare le chiamate a una distribuzione di messaggistica unificata di Microsoft Exchange Server locale o a un servizio di messaggistica unificata di Exchange ospitata.

<div>

## <a name="the-exum-routing-application"></a>Applicazione di routing della messaggistica unificata di Exchange

L'applicazione di routing della messaggistica unificata di Lync Server 2013 Exchange utilizza le informazioni dalle impostazioni degli account utente e dai parametri dei criteri di segreteria telefonica ospitata per determinare come instradare le chiamate per i messaggi vocali ospitati, come illustrato nel diagramma seguente.

**Esempio di routing della messaggistica unificata di Exchange con distribuzione mista**

![Distribuzione della messaggistica unificata di Exchange in locale di Lync Server](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange in locale di Lync Server")

Il routing della messaggistica unificata di Exchange può essere configurato per instradare le chiamate agli utenti abilitati alla messaggistica unificata di Exchange locale, agli utenti abilitati alla messaggistica unificata di Exchange ospitata o a una combinazione dei due.

Si supponga, ad esempio, che la cassetta postale di Roy e il servizio di messaggistica unificata di Exchange siano ospitati in una distribuzione di Exchange locale.

  - Le informazioni sull'indirizzo proxy provenienti dall'account utente di Roy forniscono le informazioni che l'applicazione di routing di ExUM utilizza per instradare le chiamate a un server Messaggistica unificata di Exchange locale.

La cassetta postale di Alice e il servizio di messaggistica unificata di Exchange si trovano nel Data Center di un provider di servizi di Exchange ospitato. Il routing per le chiamate di messaggistica unificata di Exchange è configurato come indicato di seguito:

  - Il valore impostato nell'attributo msExchUCVoiceMailSettings dell'account utente di Alice indica all'applicazione di routing della messaggistica unificata di Exchange di controllare i dettagli relativi al routing in criteri di segreteria telefonica ospitata.
    
    <div>
    

    > [!NOTE]  
    > Il valore dell'attributo msExchUCVoiceMailSettings può essere impostato dal provider di servizi di Exchange o dall'amministratore di Lync Server 2013. Nell'esempio riportato nel diagramma precedente, il valore (CsHostedVoiceMail = 1) è stato impostato dall'amministratore di Lync Server 2013 per abilitare la segreteria telefonica ospitata per Alice. Per informazioni dettagliate su questo attributo, vedere <A href="lync-server-2013-hosted-exchange-user-management.md">gestione degli utenti di Exchange ospitati in Lync Server 2013</A>.

    
    </div>

  - I criteri di segreteria telefonica ospitata assegnati all'account utente di Alice offrono informazioni dettagliate sul routing:
    
      - La destinazione è il provider di servizi di messaggistica unificata di Exchange ospitati (ls. ExUm. \<hostedExchangeServer\> . com in questo esempio).
    
      - Le organizzazioni sono identificate dagli ID tenant, ovvero gli FQDN di routing per i messaggi SIP per i tenant di Exchange Server che si trovano in ls. ExUm. \<hostedExchangeServer\> . com (corp.contoso.com e corp.litwareinc.com in questo esempio).
        
        <div>
        

        > [!NOTE]  
        > Per Exchange Online, l'FQDN è exap.um.outlook.com.

        
        </div>
        
        Per ulteriori informazioni, vedere [criteri di segreteria telefonica ospitata in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Se l'attributo msExchUCVoiceMailSettings e le impostazioni dell'indirizzo proxy di messaggistica unificata sono entrambi presenti in un account utente, l'attributo msExchUCVoiceMailSettings ha la precedenza.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

