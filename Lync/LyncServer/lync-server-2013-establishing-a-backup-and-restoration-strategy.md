---
title: 'Lync Server 2013: creazione di una strategia di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee1a13667e28ad374f538d61f6cfd941d31fade
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Creazione di una strategia di backup e ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-26_

Prima di poter sviluppare un piano di backup e ripristino per Lync Server, è necessario sviluppare una strategia adatta agli obiettivi dell'organizzazione. Per sviluppare una strategia di backup e ripristino efficace, è necessario:

  - Stabilire le priorità aziendali.

  - Identificare i requisiti di backup e ripristino.

<div>

## <a name="establishing-business-priorities"></a>Definizione delle priorità aziendali

Valutare le priorità aziendali dell'organizzazione. In genere, le priorità aziendali principali che influiscono sulla strategia di backup e ripristino sono le seguenti:

  - Requisiti di continuità aziendale

  - Completezza dei dati

  - Criticità dei dati

  - Requisiti di portabilità

  - Vincoli di costo

Le esigenze aziendali come queste consentono di determinare i contratti di servizio sviluppati con i clienti. I contratti a livello di servizio influenzano notevolmente la strategia di backup e ripristino.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identificazione dei requisiti di backup e ripristino

Le priorità aziendali e i contratti a livello di servizio agiscono per determinare i requisiti delle organizzazioni per il backup e il ripristino di Lync Server. Identificare e documentare i requisiti seguenti:

  - **Frequenza dei backup**   per informazioni dettagliate sulle procedure consigliate per la frequenza di backup, vedere procedure consigliate [per il backup e il ripristino per Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Gli strumenti**   di backup e ripristino includono gli utenti che usano gli strumenti e i computer in uso. Per informazioni dettagliate sugli strumenti descritti in questo argomento e sulle autorizzazioni necessarie, vedere [requisiti di backup e ripristino in Lync Server 2013: strumenti e autorizzazioni](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Il percorso**   di backup identifica se i backup vengono mantenuti localmente o in remoto, tenendo conto della sicurezza e dell'accessibilità. Specificare il contenuto multimediale da usare per i backup.

  - **I requisiti**   hardware e software identificano e documentano i requisiti hardware e software specifici, incluso l'hardware per l'archiviazione e il ripristino del backup di componenti specifici e qualsiasi software e connettività di rete necessari per supportare il backup e il ripristino. Man mano che sviluppi i requisiti hardware e software, tieni presente i vari scenari di ripristino seguiti.

  - **Scenari di ripristino**   Ecco i processi di ripristino per gli scenari seguenti:
    
      - Un pool di Lync Server non riesce. Questo scenario richiede la ricostruzione di ogni server nel pool.
    
      - Un server Standard Edition non riesce. Questo scenario richiede la ricostruzione del server in un computer nuovo o pulito e il ripristino di database.
    
      - Perdita di Central Management store. Questo scenario richiede almeno il ripristino e la pubblicazione dell'Central Management store.
    
      - Perdita di un server back-end quando l'Central Management store è ancora in funzione normalmente. Questo scenario richiede la ricostruzione del server in un computer nuovo o pulito e il ripristino di database.
    
      - Un server che fa parte di un pool di Lync Server non riesce. Questo scenario richiede la ricostruzione del server in un computer nuovo o pulito.
    
      - Un archivio di file non riesce. Questo scenario richiede il ripristino del file server o del cluster di file.
    
      - Un database di archiviazione, monitoraggio o chat persistente non riesce. Questo scenario richiede la ricreazione dei database e, se i dati sono fondamentali per l'organizzazione, per il ripristino dei dati. L'archiviazione, il monitoraggio e i dati della chat persistente non sono necessari per eseguire il backup e l'uso di Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

