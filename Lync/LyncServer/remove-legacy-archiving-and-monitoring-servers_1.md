---
title: Rimuovere server di archiviazione e di monitoraggio legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4f149db04be75cec961478f4382b3e7a333e0a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="392a2-102">Rimuovere server di archiviazione e di monitoraggio legacy</span><span class="sxs-lookup"><span data-stu-id="392a2-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="392a2-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="392a2-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="392a2-104">Se la distribuzione di Office Communications Server 2007 R2 conteneva un server di archiviazione o un Monitoring Server, dopo la migrazione a Lync Server 2013, tali server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da tutti i pool di Office Communications Server 2007 R2 rimanenti.</span><span class="sxs-lookup"><span data-stu-id="392a2-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="392a2-105">È possibile rimuovere il server di archiviazione o il Monitoring Server in qualsiasi sequenza.</span><span class="sxs-lookup"><span data-stu-id="392a2-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="392a2-106">Il requisito fondamentale è che tutti gli utenti siano stati rimossi da tutti i pool di Office Communications Server 2007 R2 rimanenti.</span><span class="sxs-lookup"><span data-stu-id="392a2-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="392a2-107">È possibile spostare gli utenti da Office Communications Server 2007 R2 a Lync Server 2013 seguendo le procedure illustrate nella [fase 6: spostare gli utenti nel pool pilota](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="392a2-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="392a2-108">Dopo aver verificato che tutti gli utenti sono stati rimossi da tutti i pool rimanenti, seguire la procedura descritta in "rimozione di server e ruoli del server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887) .</span><span class="sxs-lookup"><span data-stu-id="392a2-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

