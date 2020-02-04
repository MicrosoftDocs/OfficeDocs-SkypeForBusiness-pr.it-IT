---
title: Scenario di migrazione standard - informazioni generali
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="de12d-102">Scenario di migrazione standard - informazioni generali</span><span class="sxs-lookup"><span data-stu-id="de12d-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de12d-103">_**Argomento Ultima modifica:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="de12d-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="de12d-104">Usare gli elementi seguenti come punto di partenza quando si esegue la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="de12d-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="de12d-105">Il percorso di migrazione standard di Lync Server 2013 è il seguente:</span><span class="sxs-lookup"><span data-stu-id="de12d-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="de12d-106">L'organizzazione ha distribuito in precedenza Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat e si vuole distribuire Lync Server 2013, Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="de12d-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="de12d-107">Distribuire Lync Server 2013 e quindi distribuire i pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="de12d-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="de12d-108">Preparare e pianificare la migrazione delle chat room persistenti e determinare il momento appropriato per arrestare il sistema per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="de12d-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="de12d-109">Eseguire i cmdlet di Windows PowerShell per la migrazione (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) per trasferire il contenuto nel server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="de12d-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="de12d-110">Verificare che la migrazione sia riuscita.</span><span class="sxs-lookup"><span data-stu-id="de12d-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="de12d-111">Rimuovere la Commissione dalla distribuzione legacy.</span><span class="sxs-lookup"><span data-stu-id="de12d-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="de12d-112">Configurare il server di chat persistente in modo che i client legacy possano connettersi a Lync Server 2013, server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="de12d-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="de12d-113">Questa operazione è necessaria perché richiede tempo per distribuire nuovi client e si vuole consentire agli utenti esistenti con client legacy di accedere alle chat room il più presto possibile.</span><span class="sxs-lookup"><span data-stu-id="de12d-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="de12d-114">Distribuire nuovi client, pur continuando a garantire che i dipendenti con la chat di gruppo legacy (client) possano arrivare alle loro chat room.</span><span class="sxs-lookup"><span data-stu-id="de12d-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

