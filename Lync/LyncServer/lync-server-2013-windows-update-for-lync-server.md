---
title: 'Lync Server 2013: Windows Update per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57949b051468241e18d8a121e9d79bc1fdb378f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="21d65-102">Windows Update per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d65-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d65-103">_**Argomento Ultima modifica:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="21d65-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="21d65-104">Spesso controlla e applica aggiornamenti e aggiornamenti della sicurezza con Windows Update Services.</span><span class="sxs-lookup"><span data-stu-id="21d65-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="21d65-105">Questa operazione consente di evitare vulnerabilità in altri componenti di sistema che potrebbero consentire agli aggressori di accedere ai server che utilizzano Microsoft Lync Server 2013 con i diritti di amministratore e quindi compromettono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21d65-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="21d65-106">Gli aggiornamenti per Microsoft SQL Server 2008 Express (64 bit Edition) vengono eseguiti in ogni server di Lync Server 2013 Standard Edition (per il database back-end) e in tutti gli altri ruoli del server di Lync Server 2013 (per l'archivio di configurazione locale), a meno che non siano stati aggiornati database di SQL Server 2008 R2 Express.</span><span class="sxs-lookup"><span data-stu-id="21d65-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="21d65-107">È consigliabile considerare questi database come parte della manutenzione di routine per l'aggiornamento della sicurezza, come dovrebbe essere SQL Server nel database back-end di un pool Front-End, il database di monitoraggio e il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="21d65-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="21d65-108">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="21d65-108">Best Practice</span></span>

  - <span data-ttu-id="21d65-109">Mantieni corrente con Windows Update.</span><span class="sxs-lookup"><span data-stu-id="21d65-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

