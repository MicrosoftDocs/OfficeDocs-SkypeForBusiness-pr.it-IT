---
title: 'Lync Server 2013: disponibilità elevata della condivisione di file'
description: 'Lync Server 2013: disponibilità elevata della condivisione di file.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b0a77d2d03460c640c66b8e8ce2a551edf2d73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543362"
---
# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Disponibilità elevata della condivisione di file in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-03-30_

Per garantire la disponibilità elevata per la condivisione dei file di Lync Server in un unico Data Center, è possibile utilizzare il file System distribuito (DFS). DFS supporta il failover da un file server a un altro all'interno dello stesso data center. Per una distribuzione su larga scala, è consigliabile utilizzare file server dedicati accoppiati mediante DFS.

A seconda delle dimensioni della rete e del grado di resilienza desiderato, è possibile utilizzare una coppia di server per ospitare tutte le condivisioni file in un sito oppure utilizzare una coppia per ogni pool Front End.

DFS è un meccanismo che esegue la replica nel miglior modo possibile in base alle condizioni esistenti, senza alcun impegno pubblicato relativamente al raggiungimento degli obiettivi in termini di tempo di ripristino (RTO, Recovery Time Objective) o di punto di ripristino (RPO, Recovery Point Objective). Il failover tra i server DFS dovrebbe avvenire rapidamente, ma il ritardo della replica dei dati può impedire agli utenti di proseguire con il lavoro che stavano svolgendo quando si verifica il failover.

Se si utilizza DFS e l'archivio dati nella condivisione file è importante, è consigliabile eseguire frequentemente il backup delle condivisioni file, ad esempio ogni 4-8 ore. Quando una condivisione file non è più attiva e la replica non è aggiornata, è possibile utilizzare il backup per ripristinare il contenuto del server con problemi nell'altro server accoppiato al server attualmente non disponibile.

</div>

<span> </span>

</div>

</div>

</div>

