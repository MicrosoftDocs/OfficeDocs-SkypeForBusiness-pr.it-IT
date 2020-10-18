---
title: "Lync Server 2013: componenti utilizzati dall'applicazione annuncio"
description: "Lync Server 2013: componenti utilizzati dall'applicazione annuncio."
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
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577692"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="8a87c-103">Componenti utilizzati dall'applicazione annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a87c-103">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a87c-104">_**Ultimo argomento modificato:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="8a87c-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="8a87c-105">In Lync Server 2013, l'applicazione annuncio è un componente dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="8a87c-105">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="8a87c-106">Quando si distribuisce VoIP aziendale, l'applicazione annuncio viene automaticamente installata e attivata insieme all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="8a87c-106">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="8a87c-107">In questa sezione vengono descritti i componenti che supportano l'applicazione annuncio.</span><span class="sxs-lookup"><span data-stu-id="8a87c-107">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="8a87c-108">Componenti dell'applicazione Annuncio</span><span class="sxs-lookup"><span data-stu-id="8a87c-108">Announcement Application Components</span></span>

<span data-ttu-id="8a87c-109">I componenti di Lync Server seguenti supportano l'applicazione annuncio:</span><span class="sxs-lookup"><span data-stu-id="8a87c-109">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="8a87c-110">**Servizio applicazione**     Il servizio applicazione fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificate.</span><span class="sxs-lookup"><span data-stu-id="8a87c-110">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="8a87c-111">Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8a87c-111">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="8a87c-112">**Applicazione**     Response Group L'applicazione Response Group è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="8a87c-112">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="8a87c-113">Quando un intervallo di numeri di telefono non assegnato è configurato in modo da instradare un annuncio, è necessario che l'applicazione Response Group INSTRADE le chiamate effettuate al numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="8a87c-113">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="8a87c-114">(L'applicazione Response Group non è obbligatoria se tutti gli intervalli sono configurati in modo da instradare la messaggistica unificata di Exchange).</span><span class="sxs-lookup"><span data-stu-id="8a87c-114">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="8a87c-115">**File audio**     I file audio vengono utilizzati per gli annunci.</span><span class="sxs-lookup"><span data-stu-id="8a87c-115">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="8a87c-116">**Archivio file**     L'applicazione annuncio utilizza l'archivio file per archiviare i file audio.</span><span class="sxs-lookup"><span data-stu-id="8a87c-116">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="8a87c-117">Pannello di controllo di **Lync Server**     È possibile utilizzare il pannello di controllo di Lync Server per configurare la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="8a87c-117">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="8a87c-118">**Lync Server Management Shell**     È possibile utilizzare i cmdlet di Lync Server Management Shell per configurare le impostazioni degli annunci e la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="8a87c-118">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

