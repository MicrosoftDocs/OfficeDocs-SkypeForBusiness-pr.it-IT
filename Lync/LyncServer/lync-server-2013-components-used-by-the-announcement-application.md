---
title: "Lync Server 2013: Componenti utilizzati dall'applicazione Annuncio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="a82c1-102">Componenti utilizzati dall'applicazione Annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a82c1-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a82c1-103">_**Argomento Ultima modifica:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="a82c1-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="a82c1-104">In Lync Server 2013 l'applicazione di annuncio è un componente dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="a82c1-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="a82c1-105">Quando si distribuisce VoIP aziendale, l'applicazione di annuncio viene automaticamente installata e attivata insieme all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="a82c1-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="a82c1-106">In questa sezione vengono descritti i componenti che supportano l'applicazione di annuncio.</span><span class="sxs-lookup"><span data-stu-id="a82c1-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="a82c1-107">Componenti dell'applicazione di annuncio</span><span class="sxs-lookup"><span data-stu-id="a82c1-107">Announcement Application Components</span></span>

<span data-ttu-id="a82c1-108">I componenti di Lync Server seguenti supportano l'applicazione di annuncio:</span><span class="sxs-lookup"><span data-stu-id="a82c1-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="a82c1-109">**Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="a82c1-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="a82c1-110">Il servizio applicazione viene installato automaticamente in ogni server front-end in un pool Front-end e in ogni server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a82c1-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="a82c1-111">**Response Group Application**   l'applicazione Response Group è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a82c1-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="a82c1-112">Quando un intervallo di numeri di telefono non assegnato è configurato per l'instradamento a un annuncio, è necessaria l'applicazione Response Group per instradare le chiamate effettuate al numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="a82c1-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="a82c1-113">L'applicazione Response Group non è necessaria se tutti gli intervalli sono configurati per l'instradamento alla messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a82c1-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="a82c1-114">\*\*\*\*   Per gli annunci vengono usati file audio per i file audio.</span><span class="sxs-lookup"><span data-stu-id="a82c1-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="a82c1-115">**Archivio file l'**   applicazione di annuncio USA archivio file per archiviare i file audio.</span><span class="sxs-lookup"><span data-stu-id="a82c1-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="a82c1-116">**Pannello di controllo di Lync Server**   è possibile usare il pannello di controllo di Lync Server per configurare la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a82c1-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="a82c1-117">**Lync Server Management Shell**   è possibile usare i cmdlet di Lync Server Management Shell per configurare le impostazioni degli annunci e la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a82c1-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

