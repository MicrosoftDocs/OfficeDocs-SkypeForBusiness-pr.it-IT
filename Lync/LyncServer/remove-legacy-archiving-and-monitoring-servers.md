---
title: Rimuovere server di archiviazione e di monitoraggio legacy
description: Rimuovere i server di archiviazione e di monitoraggio legacy.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0155fb18e298d2538e3bad8dc4a5626bb1ce01d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545922"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="fb8eb-103">Rimuovere server di archiviazione e di monitoraggio legacy</span><span class="sxs-lookup"><span data-stu-id="fb8eb-103">Remove legacy Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb8eb-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="fb8eb-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="fb8eb-105">Se la distribuzione legacy conteneva un server di archiviazione o un Monitoring Server, dopo la migrazione a Lync Server 2013, tali server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da tutti i pool legacy rimanenti.</span><span class="sxs-lookup"><span data-stu-id="fb8eb-105">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="fb8eb-106">È possibile rimuovere il server di archiviazione o il Monitoring Server in qualsiasi sequenza.</span><span class="sxs-lookup"><span data-stu-id="fb8eb-106">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="fb8eb-107">Il requisito fondamentale è che tutti gli utenti siano stati rimossi dai pool legacy rimanenti.</span><span class="sxs-lookup"><span data-stu-id="fb8eb-107">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="fb8eb-108">È possibile spostare gli utenti da Lync Server 2010 a Lync Server 2013 attenendosi alle procedure descritte nella [fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="fb8eb-108">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="fb8eb-109">Dopo aver verificato che tutti gli utenti sono stati rimossi da tutti i pool rimanenti, seguire la procedura descritta in "disinstallazione di Microsoft Lync Server 2010 e rimozione dei ruoli del server", che è possibile scaricare all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) .</span><span class="sxs-lookup"><span data-stu-id="fb8eb-109">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

