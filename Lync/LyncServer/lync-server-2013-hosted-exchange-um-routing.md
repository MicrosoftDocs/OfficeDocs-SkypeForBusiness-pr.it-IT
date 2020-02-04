---
title: 'Lync Server 2013: Routing della messaggistica unificata di Exchange ospitata'
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
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Routing della messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

L'applicazione di routing della messaggistica unificata di Exchange viene eseguita nel server front-end per instradare le chiamate a una distribuzione di messaggistica unificata locale di Microsoft Exchange Server o al servizio di messaggistica unificata di Exchange ospitata.

<div>

## <a name="the-exum-routing-application"></a>Applicazione di routing ExUM

L'applicazione di routing della messaggistica unificata di Lync Server 2013 usa le informazioni delle impostazioni degli account utente e i parametri dei criteri di segreteria telefonica ospitata per determinare come instradare le chiamate per i messaggi vocali ospitati, come illustrato nel diagramma seguente.

**Esempio di routing della messaggistica unificata di Exchange per la distribuzione**

![Distribuzione della messaggistica unificata di Exchange con Lync Server in locale](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange con Lync Server in locale")

Il routing della messaggistica unificata di Exchange può essere configurato per instradare le chiamate agli utenti abilitati per la messaggistica unificata di Exchange locale, agli utenti abilitati per la messaggistica unificata di Exchange ospitata o a una combinazione dei due.

Supponiamo ad esempio che la cassetta postale di Roy e il servizio di messaggistica unificata di Exchange vengano ospitati in una distribuzione di Exchange locale.

  - Le informazioni sull'indirizzo proxy dell'account utente di Roy forniscono le informazioni che l'applicazione di routing ExUM USA per instradare le chiamate a un server Messaggistica unificata locale di Exchange.

La cassetta postale di Alice e il servizio di messaggistica unificata di Exchange si trovano nel centro dati di un provider di servizi Exchange ospitati. Il routing delle chiamate di messaggistica unificata di Exchange è configurato nel modo seguente:

  - I valori impostati nell'attributo msExchUCVoiceMailSettings dell'account utente di Alice indicano all'applicazione di routing ExUM di controllare i dettagli di routing in un criterio di segreteria telefonica ospitata.
    
    <div>
    

    > [!NOTE]  
    > Il valore dell'attributo msExchUCVoiceMailSettings può essere impostato dal provider di servizi di Exchange o dall'amministratore di Lync Server 2013. Nell'esempio illustrato nel diagramma precedente il valore (CsHostedVoiceMail = 1) è stato impostato dall'amministratore di Lync Server 2013 per abilitare la segreteria telefonica ospitata per Alice. Per informazioni dettagliate su questo attributo, vedere <A href="lync-server-2013-hosted-exchange-user-management.md">gestione degli utenti di Exchange ospitata in Lync Server 2013</A>.

    
    </div>

  - I criteri di segreteria telefonica ospitati assegnati all'account utente di Alice forniscono informazioni dettagliate sul routing:
    
      - La destinazione è il provider di servizi di messaggistica unificata di Exchange ospitata (ls. ExUm. \<hostedExchangeServer\>. com in questo esempio).
    
      - Le organizzazioni sono identificate dagli ID tenant, ovvero gli FQDN di routing per i messaggi SIP per i tenant di Exchange Server che si trovano in ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com e Corp.litwareinc.com in questo esempio).
        
        <div>
        

        > [!NOTE]  
        > Il nome di dominio completo per Exchange Online è exap.um.outlook.com.

        
        </div>
        
        Per informazioni dettagliate, vedere Criteri per la segreteria [telefonica ospitati in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Se l'attributo msExchUCVoiceMailSettings e le impostazioni dell'indirizzo proxy di messaggistica unificata sono presenti in un account utente, l'attributo msExchUCVoiceMailSettings ha la precedenza.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

