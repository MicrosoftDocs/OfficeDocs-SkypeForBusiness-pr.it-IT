---
title: Processo di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="eecb2-102">Processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="eecb2-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eecb2-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="eecb2-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="eecb2-104">La procedura di migrazione consigliata e supportata per Lync Server 2013 è la procedura di migrazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="eecb2-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="eecb2-105">Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sulla coesistenza.</span><span class="sxs-lookup"><span data-stu-id="eecb2-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="eecb2-106">Migrazione affiancata</span><span class="sxs-lookup"><span data-stu-id="eecb2-106">Side-by-Side Migration</span></span>

<span data-ttu-id="eecb2-107">In quasi tutte le migrazioni devi usare il percorso di migrazione affiancato.</span><span class="sxs-lookup"><span data-stu-id="eecb2-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="eecb2-108">In una migrazione affiancata si distribuisce un nuovo server con Lync Server 2013 accanto a un server corrispondente che sta eseguendo Office Communications Server 2007 R2 e quindi si trasferiscono le operazioni nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="eecb2-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="eecb2-109">Se è necessario eseguire il rollback a Office Communications Server 2007 R2, è necessario spostare di nuovo solo le operazioni nei server originali.</span><span class="sxs-lookup"><span data-stu-id="eecb2-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="eecb2-110">Tieni presente che in questa situazione le nuove riunioni pianificate con i client aggiornati non funzioneranno e anche i client dovranno essere declassati.</span><span class="sxs-lookup"><span data-stu-id="eecb2-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="eecb2-111">Test di coesistenza</span><span class="sxs-lookup"><span data-stu-id="eecb2-111">Coexistence Testing</span></span>

<span data-ttu-id="eecb2-112">Dopo aver distribuito Lync Server 2013 in parallelo a Office Communications Server 2007 R2, la topologia rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="eecb2-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="eecb2-113">In questo stato è importante testare e verificare che i servizi vengano avviati, ogni sito può essere amministrato e i client possono comunicare con utenti correnti e legacy.</span><span class="sxs-lookup"><span data-stu-id="eecb2-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="eecb2-114">Prima della migrazione di tutti gli utenti, è molto importante comprendere lo stato di ogni distribuzione e verificare che ogni distribuzione sia funzionale e funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="eecb2-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="eecb2-115">In genere, la fase di test di coesistenza esiste durante il test pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eecb2-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="eecb2-116">Gli utenti legacy vengono spostati in Lync Server 2013 per un periodo di tempo per verificare che la compatibilità e le caratteristiche e le funzionalità delle applicazioni funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="eecb2-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="eecb2-117">Dopo il test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool e le applicazioni legacy di Office Communications Server 2007 R2 vengono ritirati.</span><span class="sxs-lookup"><span data-stu-id="eecb2-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

