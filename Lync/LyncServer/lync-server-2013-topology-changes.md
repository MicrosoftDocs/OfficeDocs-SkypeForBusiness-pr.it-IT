---
title: 'Lync Server 2013: Modifiche della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Modifiche della topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

I requisiti di topologia e le considerazioni per Lync Server 2013 sono diversi da quelli per le versioni precedenti, come descritto in questa sezione.

<div>

## <a name="new-front-end-pools-architecture"></a>Nuova architettura di pool di front-end

In Lync Server 2013 l'architettura dei pool Front-end Enterprise Edition è stata cambiata in un'architettura di sistemi distribuiti.

Con questa nuova architettura, il database di back-end non è più l'archivio dati in tempo reale in un pool. Le informazioni su un determinato utente vengono mantenute in tre server front-end nel pool. Per ogni utente, un server front-end funge da master per le informazioni dell'utente e altri due server front-end fungono da repliche. Se un server front-end si abbassa, un altro server front-end che fungeva da replica viene automaticamente promosso come master.

Questo avviene dietro le quinte e gli amministratori non devono sapere quali server front-end sono i master per gli utenti. Questa distribuzione di archiviazione dei dati migliora le prestazioni e la scalabilità all'interno del pool ed Elimina il singolo punto di errore di un singolo server back-end.

Il server back-end funge da spazio di archiviazione di backup per i dati dell'utente e della conferenza ed è anche lo spazio di archiviazione principale per altri database, ad esempio il database Response Group.

Questi miglioramenti indicano anche che ci sono modifiche in come pianificare e gestire i pool. È consigliabile che tutti i pool di front end di Enterprise Edition includano almeno tre server front-end per specificare il numero completo di repliche per cui è progettata l'architettura del pool Front-end. È inoltre necessario seguire alcune procedure quando si aggiungono server a un pool Front-End, si rimuovono i server o si aggiornano i server. Per altre informazioni, vedere [topologie e componenti per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Modifiche alla topologia del ruolo del server

Alcuni ruoli del server che in precedenza sono stati eseguiti su server distinti vengono ora consolidati nel ruolo del server front-end, consentendo di risparmiare sui costi hardware

  - In Lync Server 2013, A/V Conferencing Server è sempre collocato con Front End Server.

  - I Front ends sia per il monitoraggio che per l'archiviazione ora sono sempre collocati con Front End Server. Il monitoraggio e l'archiviazione di ognuno di essi richiede comunque un database back-end distinto, che può essere collocato nello stesso server del database back-end del pool Front end o può essere ospitato in server back-end distinti.

  - Il server di chat persistente è ora un ruolo del server. In Microsoft Lync Server 2010, Group Chat Server è un'applicazione attendibile di terze parti per Microsoft Lync Server 2010. In Lync Server 2013 la funzionalità del server di chat persistente viene implementata con tre nuovi ruoli del server:
    
      - **PersistentChatService:** Principali servizi di chat server Persistenti implementati come ruolo front-end
    
      - **PersistentChatStore:** Ruolo del server back-end
    
      - **PersistentChatComplianceStore:** Ruolo del server back-end per la conformità della chat persistente

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

