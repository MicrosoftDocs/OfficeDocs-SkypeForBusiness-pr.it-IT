---
title: Processo di migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="fcc43-102">Processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="fcc43-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc43-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="fcc43-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="fcc43-104">La procedura di migrazione consigliata e supportata per Lync Server 2013 è la procedura di migrazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="fcc43-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="fcc43-105">In questo argomento vengono illustrati i motivi per cui utilizzare questo tipo di migrazione e vengono inoltre fornite informazioni sulla coesistenza.</span><span class="sxs-lookup"><span data-stu-id="fcc43-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="fcc43-106">Migrazione side-by-side</span><span class="sxs-lookup"><span data-stu-id="fcc43-106">Side-by-Side Migration</span></span>

<span data-ttu-id="fcc43-107">In quasi ogni migrazione è consigliabile utilizzare il percorso di migrazione side-by-side.</span><span class="sxs-lookup"><span data-stu-id="fcc43-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="fcc43-108">In una migrazione affiancata, è necessario distribuire un nuovo server con Lync Server 2013 accanto a un server corrispondente che esegue Office Communications Server 2007 R2 e quindi trasferire le operazioni nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="fcc43-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="fcc43-109">Se è necessario eseguire il rollback a Office Communications Server 2007 R2, è solo necessario spostare di nuovo le operazioni nei server originali.</span><span class="sxs-lookup"><span data-stu-id="fcc43-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="fcc43-110">Tenere presente che in questa situazione tutte le nuove riunioni pianificate con client aggiornati non funzioneranno e sarà necessario eseguire anche il downgrade dei client.</span><span class="sxs-lookup"><span data-stu-id="fcc43-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="fcc43-111">Testing della coesistenza</span><span class="sxs-lookup"><span data-stu-id="fcc43-111">Coexistence Testing</span></span>

<span data-ttu-id="fcc43-112">Dopo aver distribuito Lync Server 2013 in parallelo con Office Communications Server 2007 R2, la topologia rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="fcc43-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="fcc43-113">In questo stato è importante testare e verificare che i servizi siano avviati, che sia possibile amministrare ogni sito e che i client siano in grado di comunicare con gli utenti correnti e legacy.</span><span class="sxs-lookup"><span data-stu-id="fcc43-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="fcc43-114">Prima di eseguire la migrazione di tutti gli utenti, è molto importante identificare lo stato di ogni distribuzione e assicurarsi che ogni distribuzione sia corretta e funzionante.</span><span class="sxs-lookup"><span data-stu-id="fcc43-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="fcc43-115">In genere, la fase di test di coesistenza esiste durante il testing pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcc43-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="fcc43-116">Gli utenti legacy vengono spostati in Lync Server 2013 per un determinato periodo di tempo per garantire che la compatibilità delle applicazioni e le caratteristiche e le funzionalità funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="fcc43-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="fcc43-117">Dopo il testing pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool legacy e le applicazioni di Office Communications Server 2007 R2 vengono ritirati.</span><span class="sxs-lookup"><span data-stu-id="fcc43-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

