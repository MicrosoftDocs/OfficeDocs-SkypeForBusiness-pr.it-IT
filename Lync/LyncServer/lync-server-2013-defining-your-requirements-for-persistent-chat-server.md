---
title: 'Lync Server 2013: definizione dei requisiti per il server Chat persistente'
description: 'Lync Server 2013: definizione dei requisiti per il server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af3fab1d91b78a5993f723b8fc6b375e4ab7cee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545352"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definizione dei requisiti dell'organizzazione per il server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-15_

Prima di distribuire il server Chat persistente per l'organizzazione, è essenziale prendere in considerazione le seguenti domande chiave per ottimizzare la distribuzione:

  - Chi (profilo utente) deve essere abilitato per il server Chat persistente? Il server Chat persistente è abilitato da un criterio che può essere impostato a livello globale, sito, pool o utente.

  - Quanti utenti (scala) devono essere abilitati per il server Chat persistente? Il server Chat persistente supporta gli utenti con provisioning 150.000 (abilitati dai criteri) e un massimo di 80.000 utenti simultanei che utilizzano il server Chat persistente. Un singolo server Chat persistente può supportare gli utenti connessi a 20.000 e un singolo pool di server Chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.

  - Si sta eseguendo la migrazione da una versione precedente di Group Chat Server o si sta distribuendo il server Chat persistente per la prima volta?

  - Ci sono requisiti di conformità da rispettare? Il server Chat persistente supporta la conformità. Il servizio di conformità viene eseguito nella collocazione sul server front end server Persistent Chat, invece del requisito di un computer separato nelle distribuzioni precedenti di Group Chat Server. La conformità è facoltativa e, se scelta, richiede un database di conformità che deve essere configurato per l'archiviazione di dati ed eventi di conformità. È possibile che si desideri configurare anche un adattatore per estrarre i dati dal database di conformità e convertirli in un altro formato, ad esempio file XML o archivi di Exchange ospitati.

  - In che modo si vogliono controllare ambiti, limiti etici e accesso? È possibile definire **Categorie** per definire i limiti e scegliere gli utenti a cui è consentito trovarsi nelle chat create in ognuna di queste categorie.

  - In che modo si vuole controllare chi può creare chat? È possibile configurare **Creatori**, appropriati a seconda della categoria, che possono creare chat. I creatori possono impostare altri membri come **Responsabili di chat room** per la gestione ordinaria delle chat (aggiunta o rimozione di membri), in base all'ambito dei **Membri consentiti/Membri non consentiti** configurati dalla categoria.

  - In che modo si vogliono creare le chat? Il server Chat persistente offre una funzionalità basata sul Web per la creazione e la gestione della sala. Questa operazione può essere avviata dal client Lync 2013. È possibile scegliere di definire una soluzione personalizzata, utilizzando il Software Development Kit (SDK) di Persistent Chat Server, che implementa i flussi di lavoro e i requisiti aziendali e configura il server Chat persistente per indirizzare gli utenti alla soluzione personalizzata.

  - Di che tipo di componenti aggiuntivi si vuole effettuare il provisioning? I **componenti** aggiuntivi consentono di migliorare l'esperienza in sala utilizzando il riquadro Extensibility nel client Lync 2013 per fornire un contesto pertinente per la sala. È possibile scegliere i componenti aggiuntivi generici che si ritengono più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via. I responsabili di chat room, se vogliono, possono scegliere uno dei componenti aggiuntivi registrati e associarlo alla propria chat.

  - Quali sono i requisiti di disponibilità elevata e di ripristino di emergenza? Il server Chat persistente supporta il mirroring di SQL Server e il clustering di SQL Server per la disponibilità elevata e supporta fino a 8 Server (4 attivi e 4 in standby) in un pool esteso con il log shipping di SQL Server per il ripristino di emergenza.

  - Ci sono requisiti normativi da rispettare? Se l'azienda si trova in un paese/area geografica in cui i dati devono essere conservati all'interno del paese, potrebbe essere necessario distribuire più pool di server di chat persistente, ognuno locale a una specifica geografia. Una sala, una categoria o un componente aggiuntivo non si estende su pool, bensì appartiene a un solo pool di server Chat persistente. È possibile gestire il set di categorie, i componenti aggiuntivi e le sale per ogni pool di server Chat persistente. Gli utenti possono essere configurati in modo che possano accedere alle chat room di uno o più pool utilizzando l'ambito di appartenenza di categoria AllowedMembers o della sala, a seconda di come si progettano le categorie.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si dispone di più pool di server di chat persistente, non è possibile aumentare la scalabilità (sono ancora disponibili solo 80.000 utenti connessi contemporaneamente in tutti i pool di server Chat persistente). Il motivo principale del supporto di più pool di server di chat persistente è il supporto di problemi normativi.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

