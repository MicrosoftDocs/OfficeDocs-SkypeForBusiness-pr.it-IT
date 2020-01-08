---
title: "Lync Server 2013: Pianificazione dell'abbinamento dei pool Front End"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0445a6d952ba7311b8f6b5435c16d9e91de587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="02865-102">Pianificazione dell'abbinamento dei pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02865-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02865-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="02865-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="02865-104">Per le migliori capacità di ripristino di emergenza in Lync Server 2013, distribuire coppie di pool Front-end in due siti dislocati geograficamente.</span><span class="sxs-lookup"><span data-stu-id="02865-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="02865-105">Ogni sito contiene un pool Front-end che viene associato a un pool Front-End corrispondente nell'altro sito.</span><span class="sxs-lookup"><span data-stu-id="02865-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="02865-106">Entrambi i siti sono attivi e il servizio di backup di Lync Server offre la replica dei dati in tempo reale per sincronizzare i pool.</span><span class="sxs-lookup"><span data-stu-id="02865-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="02865-107">Il servizio di backup è una nuova funzionalità di Lync Server 2013, progettata per supportare la soluzione di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="02865-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="02865-108">Viene installata in un pool Front-end quando si associa il pool a un altro pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="02865-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="02865-109">Se il pool in un sito non riesce, è possibile eseguire il failover degli utenti da tale pool al pool nell'altro sito, che fornisce quindi Servizi a tutti gli utenti in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="02865-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="02865-110">Per scopi di pianificazione della capacità, ogni pool deve essere progettato per gestire i carichi di lavoro di tutti gli utenti in entrambi i pool in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="02865-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02865-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="02865-111">In This Section</span></span>

  - [<span data-ttu-id="02865-112">Opzioni di associazione e procedure consigliate per la combinazione di pool supportate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02865-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="02865-113">Eseguire il backup delle relazioni di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02865-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="02865-114">Tempo di ripristino per il failover e il failback dei pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02865-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="02865-115">Failover dell'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02865-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="02865-116">Sicurezza dei dati per l'abbinamento dei pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02865-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

