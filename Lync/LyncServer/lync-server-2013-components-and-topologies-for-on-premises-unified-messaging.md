---
title: 'Lync Server 2013: Componenti e topologie per la messaggistica unificata locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdaf33a230f2663e9fc8b541aafb47c362d0ac97
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Componenti e topologie per la messaggistica unificata locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-25_

In questo argomento vengono descritti i componenti di Microsoft Exchange Server 2013 necessari per la distribuzione delle funzionalità di messaggistica UNIFICAta di Exchange a distribuzioni di Lync Server 2013. Vengono inoltre descritte le topologie supportate per l'integrazione della messaggistica unificata di Exchange locale.

<div>

## <a name="exchange-server-components"></a>Componenti di Exchange Server

Per fornire le caratteristiche e i servizi di messaggistica unificata di Exchange descritti in [funzionalità di messaggistica unificata integrata e Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) per gli utenti di VoIP aziendale dell'organizzazione, è necessario distribuire un server cassette postali di Microsoft Exchange e un server Accesso client, che ospita cassette postali degli utenti e offre una posizione di archiviazione unica per la posta elettronica e la segreteria telefonica. La messaggistica unificata di Exchange viene eseguita come servizio nella cassetta postale di Exchange e nei server Accesso client.

Per informazioni dettagliate sui componenti di messaggistica unificata di Exchange in Microsoft Exchange Server 2007 e Microsoft Exchange Server 2010, vedere [distribuzione della messaggistica unificata locale di Exchange per specificare la segreteria telefonica di Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

È possibile distribuire Lync Server 2013 e messaggistica UNIFICAta di Exchange nella stessa foresta o in più foreste. Se la distribuzione si estende su più foreste, è necessario eseguire la procedura di integrazione di Exchange per ogni foresta di messaggistica unificata di Exchange. È inoltre necessario configurare ogni foresta di Microsoft Exchange per considerare attendibile la foresta Lync Server 2013 e la foresta Lync Server 2013 per considerare attendibile ogni foresta di messaggistica unificata di Exchange. Oltre a questo trust tra insiemi di strutture, le impostazioni di messaggistica unificata di Exchange per tutti gli utenti devono essere impostate sugli oggetti utente nella foresta di Lync Server 2013.

Lync Server 2013 supporta le topologie seguenti per l'integrazione della messaggistica unificata di Exchange:

  - Singola foresta

  - Singolo dominio, ovvero una singola foresta con un singolo dominio. Lync Server 2013, Microsoft Exchange e tutti gli utenti si trovano nello stesso dominio.

  - Più domini, ovvero un dominio radice con uno o più domini figlio. Lync Server 2013 e i server di Microsoft Exchange vengono distribuiti in domini diversi dal dominio in cui si creano utenti. I server di messaggistica unificata di Exchange possono essere distribuiti in domini diversi dal pool di Lync Server 2013 supportati.

  - Più insiemi di strutture, ovvero foresta delle risorse. Lync Server 2013 è distribuito in una singola foresta e quindi gli utenti vengono distribuiti in più foreste. Gli attributi di messaggistica unificata di Exchange degli utenti devono essere replicati nella foresta di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Exchange può essere distribuito in più foreste. Ogni organizzazione di Exchange può specificare la messaggistica unificata di Exchange per gli utenti oppure la messaggistica unificata di Exchange può essere distribuita nella stessa foresta di Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

