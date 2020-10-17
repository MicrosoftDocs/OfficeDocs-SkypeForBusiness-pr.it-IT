---
title: Processo di migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf45be5e5d30a1c8a69a634837bc63c2768b193
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515123"
---
# <a name="migration-process"></a><span data-ttu-id="95bea-102">Processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="95bea-102">Migration process</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95bea-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="95bea-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="95bea-104">La procedura di migrazione consigliata e supportata per Lync Server 2013 è la migrazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="95bea-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="95bea-105">In questo argomento vengono illustrati i motivi per cui utilizzare questo tipo di migrazione e fornite informazioni sul test di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="95bea-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="95bea-106">Migrazione affiancata</span><span class="sxs-lookup"><span data-stu-id="95bea-106">Side-By-Side Migration</span></span>

<span data-ttu-id="95bea-107">In quasi ogni migrazione è consigliabile utilizzare il percorso di migrazione side-by-side.</span><span class="sxs-lookup"><span data-stu-id="95bea-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="95bea-108">In una migrazione affiancata, è necessario distribuire un nuovo server con Lync Server 2013 accanto a un server corrispondente che esegue Lync Server 2010 e quindi trasferire le operazioni nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="95bea-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="95bea-109">Se è necessario eseguire il rollback a Lync Server 2010, è solo necessario spostare di nuovo le operazioni nei server originali.</span><span class="sxs-lookup"><span data-stu-id="95bea-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="95bea-110">Tenere presente che in questa situazione tutte le nuove riunioni pianificate con client aggiornati non funzioneranno e sarà necessario eseguire anche il downgrade dei client.</span><span class="sxs-lookup"><span data-stu-id="95bea-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="95bea-111">Testing della coesistenza</span><span class="sxs-lookup"><span data-stu-id="95bea-111">Coexistence Testing</span></span>

<span data-ttu-id="95bea-112">Dopo aver distribuito Lync Server 2013 in parallelo con Lync Server 2010, la distribuzione rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="95bea-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="95bea-113">In questo stato è importante testare e verificare che i servizi siano avviati, che sia possibile amministrare ogni sito e che i client siano in grado di comunicare con gli utenti correnti e legacy.</span><span class="sxs-lookup"><span data-stu-id="95bea-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="95bea-114">Prima di eseguire la migrazione di tutti gli utenti, è estremamente importante conoscere lo stato di ciascuna distribuzione e verificare che ogni distribuzione sia operativa e funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="95bea-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="95bea-115">In genere, la fase di test di coesistenza esiste durante il testing pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95bea-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="95bea-116">Gli utenti legacy vengono spostati in Lync Server 2013 per un determinato periodo di tempo per garantire che la compatibilità delle applicazioni e le caratteristiche e le funzionalità funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="95bea-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="95bea-117">Dopo il testing pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool legacy e le applicazioni di Lync Server 2010 vengono ritirati.</span><span class="sxs-lookup"><span data-stu-id="95bea-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

