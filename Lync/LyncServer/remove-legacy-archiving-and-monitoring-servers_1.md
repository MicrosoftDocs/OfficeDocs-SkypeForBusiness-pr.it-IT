---
title: Rimuovere server di archiviazione e di monitoraggio legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcca1687a91f3ec3bd35fceab9ae6cdf58292292
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="b10a1-102">Rimuovere server di archiviazione e di monitoraggio legacy</span><span class="sxs-lookup"><span data-stu-id="b10a1-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b10a1-103">_**Argomento Ultima modifica:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b10a1-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b10a1-104">Se la distribuzione di Office Communications Server 2007 R2 conteneva un server di archiviazione o un server di monitoraggio, dopo la migrazione a Lync Server 2013, questi server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da qualsiasi rimanente Pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b10a1-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="b10a1-105">È possibile rimuovere il server di archiviazione o il server di monitoraggio in qualsiasi sequenza.</span><span class="sxs-lookup"><span data-stu-id="b10a1-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="b10a1-106">Il requisito fondamentale è che tutti gli utenti siano stati rimossi da tutti i pool di Office Communications Server 2007 R2 rimanenti.</span><span class="sxs-lookup"><span data-stu-id="b10a1-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="b10a1-107">È possibile trasferire utenti da Office Communications Server 2007 R2 a Lync Server 2013 seguendo le procedure descritte nella [fase 6: trasferire gli utenti nel pool pilota](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b10a1-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="b10a1-108">Dopo aver confermato che tutti gli utenti sono stati rimossi da tutti i pool rimanenti, seguire la procedura descritta in "rimozione di server e [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)ruoli del server".</span><span class="sxs-lookup"><span data-stu-id="b10a1-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

