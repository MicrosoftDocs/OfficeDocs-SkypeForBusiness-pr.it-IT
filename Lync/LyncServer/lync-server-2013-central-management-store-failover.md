---
title: Failover dell'archivio di gestione centrale di Lync Server 2013
description: Failover dell'archivio di gestione centrale di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2960a55d6bdc49e00bf22997bc53946d4770fde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544372"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="76a3f-103">Failover dell'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a3f-103">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76a3f-104">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="76a3f-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="76a3f-105">L'archivio di gestione centrale contiene i dati di configurazione relativi a server e servizi nella distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="76a3f-105">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="76a3f-106">Fornisce un'archiviazione schematizzato e robusta dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="76a3f-106">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="76a3f-107">Convalida inoltre i dati per garantire la coerenza della configurazione.</span><span class="sxs-lookup"><span data-stu-id="76a3f-107">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="76a3f-108">Ogni distribuzione di Lync include un archivio di gestione centrale, ospitato dal server back-end di un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="76a3f-108">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="76a3f-109">Quando si stabilisce una coppia di pool che include il pool che ospita l'archivio di gestione centrale, nel pool di backup è configurato un database dell'archivio di gestione centrale di backup e i servizi dell'archivio di gestione centrale sono installati in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="76a3f-109">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="76a3f-110">In qualsiasi momento, uno dei due database dell'archivio di gestione centrale è il master attivo e l'altro è una modalità standby.</span><span class="sxs-lookup"><span data-stu-id="76a3f-110">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="76a3f-111">Il contenuto viene replicato dal servizio di backup dal master attivo in quello in standby.</span><span class="sxs-lookup"><span data-stu-id="76a3f-111">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="76a3f-112">Durante un failover del pool che include i pool che ospitano l'archivio di gestione centrale, l'amministratore deve eseguire il failover dell'archivio di gestione centrale prima di eseguire il failback del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="76a3f-112">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="76a3f-113">Dopo aver ripristinato il disastro, non è necessario eseguire il failover dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="76a3f-113">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="76a3f-114">Dopo il ripristino, l'archivio di gestione centrale nel pool di backup originale può rimanere come master attivo.</span><span class="sxs-lookup"><span data-stu-id="76a3f-114">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="76a3f-115">Gli obiettivi di progettazione per il failover dell'archivio di gestione centrale sono di 5 minuti per l'obiettivo del tempo di ripristino (RTO) e di 5 minuti per l'obiettivo del punto di ripristino (RPO).</span><span class="sxs-lookup"><span data-stu-id="76a3f-115">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

