---
title: "Lync Server 2013: Failover dell'archivio di gestione centrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="78750-102">Failover dell'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78750-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78750-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="78750-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="78750-104">L'archivio di gestione centrale contiene i dati di configurazione relativi a server e servizi nella distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="78750-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="78750-105">Offre un solido spazio di archiviazione schematizzato dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="78750-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="78750-106">Convalida inoltre i dati per garantire la coerenza della configurazione.</span><span class="sxs-lookup"><span data-stu-id="78750-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="78750-107">Ogni distribuzione di Lync include un unico Central Management store, ospitato dal server back-end di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="78750-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="78750-108">Quando si stabilisce l'associazione di un pool che include il pool che ospita l'archivio di gestione centrale, nel pool di backup è configurato un database di backup di Central Management store e i servizi di Central Management store sono installati in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="78750-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="78750-109">In qualsiasi momento, uno dei due database di Central Management store è lo schema attivo, mentre l'altro è in standby.</span><span class="sxs-lookup"><span data-stu-id="78750-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="78750-110">Il contenuto viene replicato dal servizio di backup da master attivo in standby.</span><span class="sxs-lookup"><span data-stu-id="78750-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="78750-111">Durante un failover del pool che include i pool che ospitano Central Management store, l'amministratore deve avere esito negativo su Central Management Store prima di non superare il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="78750-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="78750-112">Una volta riparato il disastro, non è necessario eseguire il failover dell'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="78750-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="78750-113">Dopo il ripristino, l'archivio di gestione centrale nel pool di backup originale può rimanere come master attivo.</span><span class="sxs-lookup"><span data-stu-id="78750-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="78750-114">Gli obiettivi di progettazione per il failover di Central Management store sono di 5 minuti per l'obiettivo del tempo di recupero (RTO) e di 5 minuti per l'obiettivo del punto di ripristino (RPO).</span><span class="sxs-lookup"><span data-stu-id="78750-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

