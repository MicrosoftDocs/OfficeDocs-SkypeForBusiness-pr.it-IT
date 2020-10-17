---
title: 'Lync Server 2013: pianificazione per la disponibilità elevata e il ripristino di emergenza'
description: 'Lync Server 2013: pianificazione della disponibilità elevata e del ripristino di emergenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571842"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-31_

Come in Lync Server 2010, il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Lync Server 2013 si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore. Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.

Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza per i pool Front End introducendo dispersione geografiche dei server in due data center per fornire la continuazione del servizio se un intero pool o sito si sposta verso il basso.

Lync Server 2013 consente inoltre di migliorare la disponibilità elevata del server back-end, grazie al supporto del mirroring SQL sincrono per i database back-end.

In questa sezione vengono illustrate le principali funzionalità per disponibilità elevata e ripristino di emergenza e descritti i passaggi da effettuare per assicurare disponibilità elevata e ripristino di emergenza per gli altri ruoli server.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Ripristino di emergenza del pool Front end in Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Ripristino di emergenza del server perimetrale in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Pianificazione della resilienza di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Funzionalità di gestione delle chiamate per il ripristino di emergenza in Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Resilienza del sito metropolitano di Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

