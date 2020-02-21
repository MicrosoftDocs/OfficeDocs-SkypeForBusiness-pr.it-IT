---
title: Supporto di Lync Server 2013 per l'integrazione della messaggistica unificata di Exchange ospitata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c87de9c57abaf4938b350aa40e8deea1150d22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Supporto per l'integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

L'applicazione di routing di Lync Server 2013 ExUM supporta l'integrazione con la messaggistica unificata di Exchange in un ambiente locale, in cui Lync Server 2013 e la messaggistica unificata di Exchange sono entrambi installati localmente all'interno dell'organizzazione o con la messaggistica unificata di Exchange ospitata da un provider di servizi, come illustrato nel diagramma seguente.

![Distribuzione della messaggistica unificata di Exchange in locale di Lync Server](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange in locale di Lync Server")

Sono supportate le modalità seguenti:

  - **La modalità**   locale Lync Server 2013 e la messaggistica unificata di Exchange sono entrambi distribuiti nei server locali all'interno dell'organizzazione.

  - **Modalità cross-premise**   Lync Server 2013 è distribuito nei server locali all'interno dell'organizzazione e la messaggistica unificata di Exchange è ospitata nella struttura di un provider di servizi online, ad esempio un Data Center di Microsoft Exchange Online.

  - **Modalità mista**   la distribuzione di Lync Server 2013 dispone di alcune cassette postali utente nei server locali che eseguono Microsoft Exchange Server all'interno dell'azienda e di alcune cassette postali ospitate in un data center del servizio di Exchange ospitato.
    
    <div>
    

    > [!NOTE]  
    > La modalità mista può essere utilizzata come soluzione di transizione durante la valutazione e la migrazione graduale degli utenti alla messaggistica unificata di Exchange ospitata o come soluzione permanente se si decide di mantenere i servizi di messaggistica unificata di Exchange in locale dopo la migrazione di altri utenti.

    
    </div>

Per integrare Lync Server 2013 con messaggistica unificata di Exchange ospitata, è necessario configurare uno *spazio di indirizzi SIP condiviso* (denominato anche *dominio diviso*). In questa configurazione, sia Lync Server 2013 che il provider di servizi di messaggistica unificata di Exchange ospitati di terze parti possono accedere allo stesso spazio di indirizzi del dominio SIP. Per informazioni dettagliate, vedere [Hosted Exchange UM Integration Architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

