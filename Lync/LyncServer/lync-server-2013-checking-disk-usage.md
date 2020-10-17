---
title: "Lync Server 2013: controllo dell'utilizzo del disco"
description: "Lync Server 2013: controllo dell'utilizzo del disco."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7eddde772d156f0a416dab381efe1ab33ee202f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571002"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a>Controllo dell'utilizzo del disco in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-30_

I dischi rigidi sono un componente importante della distribuzione di Lync Server 2013. Senza un sufficiente volume di disco libero, non è possibile che il sistema operativo e i database di Lync Server 2013 funzionino correttamente. È necessario monitorare giornalmente le statistiche di database back-end di Lync Server 2013 per garantire che i server non si esauriscono nello spazio su disco e per prepararsi ad aggiungere risorse di archiviazione in base alle esigenze.

Oltre a controllare lo spazio sui dischi che ospitano il sistema operativo, i file di programma, i database e i registri delle transazioni (Lync Server 2013 back-end), è necessario monitorare anche l'utilizzo del file System che include lo spazio su disco per le condivisioni di file che contengono i dati importanti seguenti:

  - Contenuto della riunione

  - Soddisfare i metadati del contenuto

  - Registri di conformità per le riunioni

  - File di dati dell'applicazione (utilizzati internamente dal componente del server applicazioni)

  - Group Chat Server Web Service and Compliance Folders (per archiviare i file caricati nel servizio Web Group Chat)

  - File XML di conformità di Group Chat (che contengono record di conformità di Group Chat)

  - Aggiornare i file (per il servizio aggiornamento dispositivi)

  - File della Rubrica

Lync Server 2013 richiede spazio su disco rigido per l'archiviazione dei database e dei registri delle transazioni, oltre ai file in condivisioni di file elencate in precedenza.

È necessario monitorare periodicamente lo spazio su disco per garantire che la distribuzione di Lync Server 2013 non venga influenzata negativamente a causa di risorse di archiviazione insufficienti.

Confrontare e gestire informazioni statistiche sullo spazio disponibile su disco su ogni volume di Lync Server 2013 e la crescita prevista dei database e i file di registro delle transazioni. Questo aiuta a pianificare la capacità e ad aggiungere spazio di archiviazione quando sono necessarie le risorse di archiviazione.

Per risolvere la risoluzione dei problemi e le situazioni di ripristino di emergenza, è consigliabile che lo spazio disponibile su volume libero sia uguale o superiore al 110% delle dimensioni del database.

Per controllare lo spazio libero sul disco, è possibile utilizzare i seguenti metodi:

1.  **System Center Operations Manager**     System Center Operations Manager può essere utilizzato per avvisare gli amministratori quando è vincolato lo spazio del volume.

2.  **Esecuzione di uno script**     Monitorare lo spazio su disco eseguendo uno script che invia un messaggio se lo spazio disponibile sul disco rigido scende al di sotto del 20%. È possibile trovare uno script di esempio su Microsoft Script Center su TechNet, esaminare quanto segue: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Esplora risorse**     di Windows Utilizzare Esplora risorse per controllare lo spazio su disco dei volumi che archiviano i log e i database di Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

