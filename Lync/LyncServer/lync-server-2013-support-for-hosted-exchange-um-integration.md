---
title: "Lync Server 2013: Supporto per l'integrazione di messaggistica unificata di Exchange ospitata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Supporto per l'integrazione di messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

L'applicazione di routing ExUM di Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange in un ambiente locale, in cui Lync Server 2013 e la messaggistica unificata di Exchange sono installati localmente all'interno dell'organizzazione o con la messaggistica unificata di Exchange ospitata da un provider di servizi, come illustrato nel diagramma seguente.

Distribuzione di messaggistica unificata locale di Lync ![server Exchange]locale di Lync(images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Server")

Sono supportate le modalità seguenti:

  - **Modalità**   locale Lync Server 2013 e messaggistica unificata di Exchange sono entrambi distribuiti su server locali all'interno dell'organizzazione.

  - **Modalità cross-locale**   Lync Server 2013 è distribuito nei server locali all'interno dell'organizzazione e la messaggistica unificata di Exchange è ospitata in una struttura del provider di servizi online, ad esempio un Data Center di Microsoft Exchange Online.

  - **Modalità mista**   la distribuzione di Lync Server 2013 include alcune cassette postali utente in server locali che utilizzano Microsoft Exchange Server all'interno dell'organizzazione e alcune cassette postali ospitate in un centro dati del servizio Exchange ospitato.
    
    <div>
    

    > [!NOTE]  
    > La modalità mista può essere usata come soluzione transitoria durante la valutazione e la migrazione graduale degli utenti alla messaggistica unificata di Exchange ospitata o come soluzione permanente se si sceglie di conservare i servizi di messaggistica unificata di Exchange in locale dopo la migrazione di altri utenti.

    
    </div>

Per integrare Lync Server 2013 con UM ospitata di Exchange, è necessario configurare uno *spazio di indirizzi SIP condiviso* (detto anche *dominio diviso*). In questa configurazione, sia Lync Server 2013 che il provider di servizi di messaggistica unificata di Exchange ospitati di terze parti possono accedere allo stesso spazio di indirizzi del dominio SIP. Per informazioni dettagliate, vedere [architettura di integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

