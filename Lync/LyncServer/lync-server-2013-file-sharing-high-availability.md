---
title: 'Lync Server 2013: disponibilità elevata della condivisione di file'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Disponibilità elevata della condivisione di file in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-03-30_

Per garantire la disponibilità elevata per la condivisione di file di Lync Server all'interno di un singolo centro dati, è possibile usare il file System distribuito (DFS). DFS supporta il failover da un file server a un altro nello stesso centro dati. Per una distribuzione su larga scala, è consigliabile usare i file server dedicati abbinati tramite DFS.

A seconda delle dimensioni della rete e della quantità di flessibilità desiderata, è possibile usare una coppia di server per ospitare tutte le condivisioni di file in un sito oppure usare una coppia per ogni pool di front-end.

DFS è un meccanismo di replica dei file di massimo sforzo, senza l'impegno per i tempi di recupero pubblicato (RTO) o RPO (Recovery Point Objective). Il failover tra i server DFS deve essere completato in modo rapido, ma il ritardo della replica dei dati può impedire agli utenti di continuare a lavorare in corso quando il failover si verifica.

Se si usa DFS e archivio dati per la condivisione di file è fondamentale, è consigliabile eseguire il backup delle condivisioni, ad esempio ogni 4 o 8 ore. Quando si abbassa una condivisione file e la replica non è aggiornata, è possibile usare il backup per ripristinare il contenuto del server non riuscito con l'altro server associato al server che ora non è disponibile.

</div>

<span> </span>

</div>

</div>

</div>

