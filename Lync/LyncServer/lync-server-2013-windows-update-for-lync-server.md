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
ms.openlocfilehash: f7df13a7875aa033bc0d38d9d736eecd12bbf5b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="6f6da-102">Windows Update per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f6da-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f6da-103">_**Ultimo argomento modificato:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="6f6da-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="6f6da-104">Verificare di frequente la disponibilità di aggiornamenti e aggiornamenti della sicurezza e applicarli tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="6f6da-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="6f6da-105">In questo modo si evitano le vulnerabilità di altri componenti del sistema che potrebbero consentire agli aggressori di accedere ai server che eseguono Microsoft Lync Server 2013 con i diritti di amministratore e quindi di compromettere Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f6da-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="6f6da-106">Gli aggiornamenti per Microsoft SQL Server 2008 Express (64 bit Edition) vengono eseguiti su ogni server Lync Server 2013 Standard Edition (per il database back-end) e su tutti gli altri ruoli del server Lync Server 2013 (per l'archivio di configurazione locale), a meno che non sia stato eseguito l'aggiornamento di questi database di SQL Server 2008 R2 Express.</span><span class="sxs-lookup"><span data-stu-id="6f6da-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="6f6da-107">Considerare questi database nelle attività di manutenzione degli aggiornamenti della sicurezza di routine, così come SQL Server nel database back-end di un pool Front End, il database di monitoraggio e il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="6f6da-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="6f6da-108">Procedura consigliata</span><span class="sxs-lookup"><span data-stu-id="6f6da-108">Best Practice</span></span>

  - <span data-ttu-id="6f6da-109">Mantenere aggiornato il computer con Windows Update.</span><span class="sxs-lookup"><span data-stu-id="6f6da-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

