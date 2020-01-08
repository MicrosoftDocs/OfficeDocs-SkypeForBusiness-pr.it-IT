---
title: Processo di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="95901-102">Processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="95901-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95901-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="95901-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="95901-104">La procedura di migrazione consigliata e supportata per Lync Server 2013 è la migrazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="95901-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="95901-105">Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sui test di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="95901-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="95901-106">Migrazione affiancata</span><span class="sxs-lookup"><span data-stu-id="95901-106">Side-By-Side Migration</span></span>

<span data-ttu-id="95901-107">In quasi tutte le migrazioni devi usare il percorso di migrazione affiancato.</span><span class="sxs-lookup"><span data-stu-id="95901-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="95901-108">In una migrazione affiancata si distribuisce un nuovo server con Lync Server 2013 accanto a un server corrispondente che sta eseguendo Lync Server 2010 e quindi trasferisce le operazioni nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="95901-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="95901-109">Se è necessario eseguire il rollback a Lync Server 2010, è sufficiente spostare di nuovo le operazioni nei server originali.</span><span class="sxs-lookup"><span data-stu-id="95901-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="95901-110">Tieni presente che in questa situazione le nuove riunioni pianificate con i client aggiornati non funzioneranno e anche i client dovranno essere declassati.</span><span class="sxs-lookup"><span data-stu-id="95901-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="95901-111">Test di coesistenza</span><span class="sxs-lookup"><span data-stu-id="95901-111">Coexistence Testing</span></span>

<span data-ttu-id="95901-112">Dopo aver distribuito Lync Server 2013 in parallelo a Lync Server 2010, la distribuzione rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="95901-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="95901-113">In questo stato è importante testare e verificare che i servizi vengano avviati, ogni sito può essere amministrato e i client possono comunicare con utenti correnti e legacy.</span><span class="sxs-lookup"><span data-stu-id="95901-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="95901-114">Prima della migrazione di tutti gli utenti, è molto importante comprendere lo stato di ogni distribuzione e verificare che ogni distribuzione sia funzionale e funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="95901-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="95901-115">In genere, la fase di test di coesistenza esiste durante il test pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95901-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="95901-116">Gli utenti legacy vengono spostati in Lync Server 2013 per un periodo di tempo per verificare che la compatibilità e le caratteristiche e le funzionalità delle applicazioni funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="95901-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="95901-117">Dopo il test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool e le applicazioni legacy di Lync Server 2010 vengono ritirati.</span><span class="sxs-lookup"><span data-stu-id="95901-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

