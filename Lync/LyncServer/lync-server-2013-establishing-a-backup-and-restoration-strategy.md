---
title: 'Lync Server 2013: creazione di una strategia di backup e ripristino'
description: 'Lync Server 2013: creazione di una strategia di backup e ripristino.'
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
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555042"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Definizione di una strategia di backup e ripristino per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-26_

Prima di poter sviluppare un piano di backup e ripristino per Lync Server, è necessario sviluppare una strategia compatibile con gli obiettivi dell'organizzazione. Per sviluppare una strategia di backup e ripristino efficace, è necessario eseguire le operazioni seguenti:

  - Stabilire le priorità aziendali.

  - Identificare i requisiti di backup e ripristino.

<div>

## <a name="establishing-business-priorities"></a>Stabilire le priorità aziendali

Valutare le priorità aziendali dell'organizzazione. In genere, le principali priorità aziendali che incidono sulla strategia di backup e ripristino sono le seguenti:

  - Requisiti di continuità aziendale

  - Completezza dei dati

  - Criticità dei dati

  - Requisiti di portabilità

  - Vincoli dei costi

Le esigenze aziendali, ad esempio, consentono di determinare i contratti di servizio che si sviluppano con i clienti. I contratti di servizio influenzano enormemente la strategia di backup e ripristino.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Individuare i requisiti di backup e ripristino

Le priorità aziendali e i contratti di servizio agiscono per determinare i requisiti delle organizzazioni per il backup e il ripristino di Lync Server. Individuare e documentare i requisiti per i seguenti fattori:

  - **Frequenza dei backup**     Per informazioni dettagliate sulle procedure consigliate per la frequenza di backup, vedere procedure consigliate [per il backup e il ripristino di Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - Strumenti di backup **e ripristino**     Includere gli utenti che devono utilizzare gli strumenti e i computer. Per informazioni dettagliate sugli strumenti descritti in questo argomento e sulle autorizzazioni necessarie, vedere [backup and Restoration requirements in Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Percorso**     di backup Identificare se i backup vengono mantenuti localmente o in remoto, tenendo in considerazione la sicurezza e l'accessibilità. Specificare i supporti da utilizzare per i backup.

  - Requisiti hardware e **software**     Identificare e documentare i requisiti hardware e software specifici, inclusi l'hardware per l'archiviazione e il ripristino del backup di componenti specifici e qualsiasi software e connettività di rete necessari per supportare il backup e il ripristino. Nello sviluppo dei requisiti hardware e software, valutare i diversi scenari di ripristino illustrati di seguito.

  - **Scenari**     di ripristino Di seguito sono riportati i processi di ripristino per gli scenari seguenti:
    
      - Esito negativo di un pool di Lync Server. Questo scenario richiede la ricostruzione di ogni server nel pool.
    
      - Un server Standard Edition ha esito negativo. Questo scenario richiede la ricostruzione del server in un computer nuovo o sottoposto a pulizia e il ripristino dei database.
    
      - Perdita dell'archivio di gestione centrale. Questo scenario richiede almeno il ripristino e la pubblicazione dell'archivio di gestione centrale.
    
      - Perdita di un server back-end quando l'archivio di gestione centrale è ancora in funzione normalmente. Questo scenario richiede la ricostruzione del server in un computer nuovo o sottoposto a pulizia e il ripristino dei database.
    
      - Un server membro di un pool di Lync Server ha esito negativo. Questo scenario richiede la ricostruzione del server in un computer nuovo o sottoposto a pulizia e il ripristino dei database.
    
      - Un archivio file ha esito negativo. Questo scenario richiede il ripristino del file server o del file cluster.
    
      - Esito negativo di un database di archiviazione, monitoraggio o Persistent Chat. Questo scenario richiede di ricreare i database e di ripristinare i dati, se questi sono critici per l'organizzazione. I dati di archiviazione, monitoraggio e Persistent Chat non sono necessari per ottenere il backup e l'esecuzione di Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

