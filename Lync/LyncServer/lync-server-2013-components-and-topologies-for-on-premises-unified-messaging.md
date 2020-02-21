---
title: 'Lync Server 2013: componenti e topologie per la messaggistica unificata locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a21f24e87f889213a92123886a871dd1f5209ed1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Componenti e topologie per la messaggistica unificata locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-25_

In questo argomento vengono descritti i componenti di Microsoft Exchange Server 2013 necessari per fornire le funzionalità di messaggistica unificata di Exchange alla distribuzione di Lync Server 2013. Vengono inoltre descritte le topologie supportate per l'integrazione della messaggistica unificata di Exchange locale.

<div>

## <a name="exchange-server-components"></a>Componenti di Exchange Server

Per fornire le funzionalità e i servizi di messaggistica unificata di Exchange descritti in [funzionalità di messaggistica unificata integrata e Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) per gli utenti di VoIP aziendale nell'organizzazione, è necessario distribuire un server cassette postali di Microsoft Exchange e un server Accesso client che ospita le cassette postali degli utenti e fornisce un singolo percorso di archiviazione per la posta elettronica e la segreteria telefonica. La messaggistica unificata di Exchange viene eseguita come servizio nei server cassette postali e accesso client di Exchange.

Per informazioni dettagliate sui componenti di messaggistica unificata di Exchange in Microsoft Exchange Server 2007 e Microsoft Exchange Server 2010, vedere [Deploying on-premises Exchange Messaggistica unificata per fornire Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) segreteria telefonica nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

È possibile distribuire Lync Server 2013 e la messaggistica unificata di Exchange nella stessa foresta o più foreste. Se la distribuzione si estende su più insiemi di strutture, è necessario eseguire i passaggi di integrazione di Exchange per ogni foresta di messaggistica unificata di Exchange. Inoltre, è necessario configurare ogni foresta di Microsoft Exchange affinché consideri attendibile la foresta Lync Server 2013 e la foresta Lync Server 2013 per considerare attendibile ogni foresta di messaggistica unificata di Exchange. Oltre a questo trust tra foreste, è necessario che le impostazioni di messaggistica unificata di Exchange per tutti gli utenti siano impostate sugli oggetti utente nella foresta di Lync Server 2013.

Lync Server 2013 supporta le topologie seguenti per l'integrazione della messaggistica unificata di Exchange:

  - Foresta singola

  - Singolo dominio, ovvero foresta singola con un solo dominio. Lync Server 2013, Microsoft Exchange e tutti gli utenti risiedono nello stesso dominio.

  - Dominio multiplo, ovvero un dominio radice con uno o più domini figlio. Lync Server 2013 e i server di Microsoft Exchange vengono distribuiti in domini diversi dal dominio in cui vengono creati gli utenti. I server di messaggistica unificata di Exchange possono essere distribuiti in domini diversi dal pool Lync Server 2013 che supportano.

  - Foresta multipla, ovvero foresta di risorse. Lync Server 2013 è distribuito in una singola foresta e quindi gli utenti vengono distribuiti tra più foreste. Gli attributi di messaggistica unificata di Exchange per gli utenti devono essere replicati nella foresta di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Exchange può essere distribuito in più foreste. Ogni organizzazione di Exchange può fornire la messaggistica unificata di Exchange ai propri utenti oppure è possibile distribuire la messaggistica unificata di Exchange nella stessa foresta di Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

