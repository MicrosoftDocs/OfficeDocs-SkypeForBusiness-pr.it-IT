---
title: Modifiche alla topologia di Lync Server 2013
description: Viene modificata la topologia di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549102"
---
# <a name="topology-changes-in-lync-server-2013"></a>Modifiche alla topologia in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

I requisiti e le considerazioni sulla topologia per Lync Server 2013 sono diversi da quelli relativi alle versioni precedenti, come descritto in questa sezione.

<div>

## <a name="new-front-end-pools-architecture"></a>Nuova architettura di pool Front End

In Lync Server 2013, l'architettura di pool Enterprise Edition front end è stata modificata in un'architettura di sistemi distribuiti.

Con questa nuova architettura, il database back-end non è più l'archivio dati in tempo reale in un pool. Le informazioni relative a un determinato utente vengono conservate su tre Front End Server nel pool. Per ogni utente, un front end server funge da master per le informazioni dell'utente e altri due server front end fungono da repliche. Se un front end server viene abbassato, un altro front end server che funge da replica viene automaticamente promosso come master.

Questo accade dietro le quinte e gli amministratori non hanno bisogno di sapere quali front end server sono i master per cui gli utenti. Questa distribuzione dell'archiviazione dei dati consente di migliorare le prestazioni e la scalabilità all'interno del pool ed Elimina il singolo punto di errore di un singolo server back-end.

Il server back-end funge da archivio di backup per i dati degli utenti e delle conferenze ed è anche lo spazio di archiviazione principale per altri database, ad esempio il database di Response Group.

Questi miglioramenti indicano anche che sono presenti modifiche al modo in cui si pianificano e gestiscono i pool. È consigliabile che tutti i pool Enterprise Edition front end includano almeno tre Front End Server, per fornire il numero completo di repliche per cui è progettata l'architettura del pool Front end. Inoltre, è necessario seguire determinate procedure quando si aggiungono server a un pool Front End, si rimuovono i server da esso o si aggiornano i server. Per ulteriori informazioni, vedere [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Modifiche alla topologia del ruolo del server

Alcuni ruoli del server precedentemente eseguiti su server distinti sono ora consolidati nel ruolo front end server, consentendo di risparmiare sui costi hardware

  - In Lync Server 2013, A/V Conferencing Server è sempre collocato con Front End Server.

  - I front-end sia per il monitoraggio che per l'archiviazione sono ora collocati in un server front endpoint. Monitoring and Archiving each richiedono ancora un database Back-End separato, che può essere collocato nello stesso server del database back-end del pool Front end oppure può essere ospitato in server Back-End separati.

  - Il server Chat persistente è ora un ruolo del server. In Microsoft Lync Server 2010, Group Chat Server era un'applicazione attendibile di terze parti per Microsoft Lync Server 2010. In Lync Server 2013, la funzionalità del server Chat persistente viene implementata utilizzando tre nuovi ruoli del server:
    
      - **PersistentChatService:** Principali servizi del server Chat persistente implementati come ruolo front-end
    
      - **PersistentChatStore:** Ruolo del server back-end
    
      - **PersistentChatComplianceStore:** Ruolo del server back-end per la conformità della chat persistente

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

