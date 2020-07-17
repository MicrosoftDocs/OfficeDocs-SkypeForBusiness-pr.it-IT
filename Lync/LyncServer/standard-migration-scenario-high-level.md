---
title: Scenario di migrazione standard-alto livello
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0acdf50ac515810b2813a98e9dc1f289e327eba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="6bf72-102">Scenario di migrazione standard-alto livello</span><span class="sxs-lookup"><span data-stu-id="6bf72-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf72-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="6bf72-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="6bf72-104">Utilizzare gli elementi seguenti come punto di partenza per la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6bf72-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="6bf72-105">Il percorso di migrazione standard di Lync Server 2013 è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6bf72-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="6bf72-106">L'organizzazione ha distribuito in precedenza Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat e si desidera distribuire Lync Server 2013, il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6bf72-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="6bf72-107">Distribuire Lync Server 2013 e quindi distribuire i pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6bf72-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="6bf72-108">Preparare e pianificare la migrazione delle chat room permanenti e determinare il tempo appropriato per arrestare il sistema per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="6bf72-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="6bf72-109">Eseguire i cmdlet di Windows PowerShell per la migrazione (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) per spostare il contenuto nel server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6bf72-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="6bf72-110">Verificare la corretta esecuzione della migrazione.</span><span class="sxs-lookup"><span data-stu-id="6bf72-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="6bf72-111">Rimuovere la distribuzione legacy,</span><span class="sxs-lookup"><span data-stu-id="6bf72-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="6bf72-112">Configurare il server Chat persistente in modo che i client legacy possano connettersi a Lync Server 2013, server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6bf72-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="6bf72-113">Ciò è necessario perché la distribuzione dei nuovi client richiede tempo e si desidera consentire agli utenti esistenti con client legacy di poter accedere alle loro chat room il prima possibile.</span><span class="sxs-lookup"><span data-stu-id="6bf72-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="6bf72-114">Distribuire nuovi client, continuando a garantire che i lavoratori con i client di gruppo legacy possano accedere alle chat room.</span><span class="sxs-lookup"><span data-stu-id="6bf72-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

