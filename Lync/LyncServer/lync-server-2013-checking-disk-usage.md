---
title: "Lync Server 2013: controllo dell'utilizzo del disco"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791f4a0f9db56c38c837fa77b443d5aa6de74bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Controllo dell'utilizzo del disco in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-30_

I dischi rigidi sono un componente importante della distribuzione di Lync Server 2013. Senza un sufficiente volume di disco libero, il sistema operativo e i database di Lync Server 2013 non possono funzionare correttamente. È necessario monitorare giornalmente le statistiche di database back-end di Lync Server 2013 per assicurarsi che i server non finiscano nello spazio su disco e si preparino ad aggiungere risorse di archiviazione in base alle esigenze.

Oltre a controllare lo spazio sui dischi che ospitano il sistema operativo, i file di programma, il database e i registri delle transazioni (Lync Server 2013 back-end), è necessario monitorare anche l'uso del file System che include lo spazio su disco per le condivisioni di file che contengono le seguenti importanti dati

  - Contenuto della riunione

  - Metadati del contenuto della riunione

  - Registri conformità delle riunioni

  - File di dati dell'applicazione (usati internamente dal componente server applicazioni)

  - Raggruppare le cartelle servizio Web Chat Server e conformità (per archiviare i file caricati nel servizio web chat di gruppo)

  - File XML di conformità della chat di gruppo (che contengono record di conformità di Group Chat)

  - Aggiornare i file (per il servizio di aggiornamento dei dispositivi)

  - File della Rubrica

Lync Server 2013 richiede spazio su disco rigido per archiviare i propri database e i registri delle transazioni oltre ai file in condivisioni file elencate in precedenza.

È consigliabile monitorare regolarmente lo spazio su disco per verificare che la distribuzione di Lync Server 2013 non venga influenzata negativamente a causa di risorse di archiviazione insufficienti.

Confrontare e gestire le informazioni statistiche sullo spazio disponibile su disco in ogni volume di Lync Server 2013 e la crescita prevista dei database e i file di log delle transazioni. Questo aiuta a pianificare la capacità e ad aggiungere spazio di archiviazione quando sono necessarie le risorse di archiviazione.

Per gestire la risoluzione dei problemi e il ripristino di emergenza, è consigliabile che lo spazio disponibile per il volume libero sia uguale o maggiore di 110% delle dimensioni del database.

Per controllare lo spazio disponibile su disco, è possibile usare i metodi seguenti:

1.  **System Center Operations**   Manager System Center Operations Manager può essere usato per avvisare gli amministratori quando lo spazio del volume è vincolato.

2.  **L'esecuzione di uno**   spazio su disco di monitor di script esegue uno script che invia un messaggio se lo spazio disponibile sul disco rigido scende al di sotto del 20%. È possibile trovare uno script di esempio in Microsoft Script Center in TechNet, esaminare:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Esplora risorse**   USA Esplora risorse per verificare la quantità di spazio su disco nei volumi che archiviano i registri e i database di Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

