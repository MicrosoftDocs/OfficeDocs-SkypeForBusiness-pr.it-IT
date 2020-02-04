---
title: 'Lync Server 2013: Pianificazione per la disponibilità elevata e il ripristino di emergenza'
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
ms.openlocfilehash: 79abf8b98252f3b05b899a9840e7a9c9a2e8096c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-31_

Come in Lync Server 2010, il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Lync Server 2013 è basato sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server. Questo vale per i server front-end, Edge Server, Mediation Server e direttori.

Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza per i pool Front-End introducendo dispersement geografiche dei server in due centri dati per consentire la prosecuzione del servizio in caso di abbandono di un intero pool o sito.

Lync Server 2013 migliora inoltre l'elevata disponibilità di back end server, supportando il mirroring sincrono di SQL per i database di back-end.

In questa sezione vengono illustrate le principali caratteristiche di elevata disponibilità e ripristino di emergenza e vengono inoltre illustrati i passaggi che è possibile eseguire per l'elevata disponibilità e il ripristino di emergenza anche per gli altri ruoli del server.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Ripristino di emergenza del pool Front End in Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Ripristino di emergenza dei server perimetrali in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Pianificazione della resilienza di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Funzionalità di gestione delle chiamate per il ripristino di emergenza in Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Resilienza di siti metropolitani di Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

