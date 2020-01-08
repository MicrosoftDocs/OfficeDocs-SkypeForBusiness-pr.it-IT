---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per il server Chat persistente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definizione dei requisiti dell'organizzazione per il server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-15_

Prima di distribuire il server di chat persistente per l'organizzazione, è essenziale prendere in considerazione le domande chiave seguenti per ottimizzare la distribuzione:

  - Chi (profilo utente) deve essere abilitato per il server di chat persistente? Il server di chat persistente è abilitato da un criterio che può essere impostato a livello globale, del sito, del pool o dell'utente.

  - Il numero di utenti (scala) deve essere abilitato per il server di chat persistente? Il server di chat persistente supporta gli utenti con provisioning di 150.000 (abilitati per criterio) e un massimo di 80.000 utenti simultanei che usano il server di chat persistente. Un singolo server di chat persistente può supportare gli utenti connessi di 20.000 e un singolo pool di server di chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.

  - Si esegue la migrazione da una versione precedente di Group Chat Server o si sta distribuendo il server di chat persistente per la prima volta?

  - Esistono requisiti di conformità? Il server di chat persistente supporta la conformità. Il servizio di conformità viene eseguito in una collocazione nel server front end del server di chat persistente, in contrapposizione al requisito di un computer separato nelle distribuzioni precedenti di Group Chat Server. La conformità è facoltativa e, se scelta, richiede un database di conformità che deve essere configurato per archiviare i dati e gli eventi di conformità. Potrebbe essere necessario configurare un adapter anche per prendere i dati dal database di conformità e convertirli in un altro formato, ad esempio i file XML o gli archivi ospitati in Exchange.

  - Come si vogliono controllare gli ambiti, i confini etici e l'accesso? Puoi definire **categorie** per separare questi limiti e scegliere chi può essere nelle sale create in ognuna di queste categorie.

  - Come si vuole controllare chi può creare sale? Puoi configurare gli **autori**, appropriati alle categorie, che possono creare sale. Gli autori possono assegnare ad altri membri i **responsabili delle chat room** per la gestione continua delle sale (aggiunta o rimozione di membri aggiuntivi), in base all'ambito per **AllowedMembers/DeniedMembers** configurato dalla categoria.

  - Come si vogliono creare le sale? Persistent Chat Server offre una funzionalità basata sul Web per la creazione e la gestione della sala. Questa operazione può essere avviata dal client Lync 2013. Puoi scegliere di definire una soluzione personalizzata (usando il Software Development Kit (SDK) Persistent Chat Server) che implementa i tuoi requisiti e flussi di lavoro e configura il server di chat persistente per indirizzare gli utenti alla tua soluzione personalizzata.

  - Quali tipi di componenti aggiuntivi si desidera eseguire il provisioning? I **componenti** aggiuntivi migliorano l'esperienza in camera sfruttando il riquadro estensibilità nel client Lync 2013 per offrire un contesto rilevante per la sala. È possibile scegliere quali componenti aggiuntivi generali potrebbero essere più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via. I responsabili della chat room possono scegliere uno dei componenti aggiuntivi registrati e associarli alle rispettive sale, se necessario.

  - Quali sono i requisiti per l'elevata disponibilità e il ripristino di emergenza? Il server di chat persistente supporta il mirroring di SQL Server e il clustering di SQL Server per l'elevata disponibilità e supporta fino a 8 Server (4 attiva e 4 in standby) in un pool allungato con SQL Server log shipping per il ripristino di emergenza.

  - Esistono requisiti normativi? Se l'azienda si trova in un paese/area geografica in cui devono essere conservati i dati all'interno del paese, potrebbe essere necessario distribuire più pool di server di chat permanenti, ognuno locale in uno specifico percorso geografico. Una sala, una categoria o un componente aggiuntivo non si estende ai pool, ma appartiene solo a un pool di server di chat persistente. È possibile gestire il set di categorie, componenti aggiuntivi e sale per ogni pool di server di chat persistente. Gli utenti possono essere configurati per avere accesso alle sale in uno o più pool usando l'ambito di categoria AllowedMembers o l'ambito di appartenenza della sala, a seconda di come si progettano le categorie.
    
    <div>
    

    > [!IMPORTANT]  
    > La presenza di più pool di server di chat persistenti non offre più scala (è comunque possibile avere solo 80.000 utenti connessi contemporaneamente in tutti i pool di server di chat persistenti). Il motivo principale per il supporto di più pool di server di chat persistenti consiste nel supportare i problemi normativi.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

