---
title: 'Lync Server 2013: componenti utilizzati dal parcheggio di chiamata'
description: 'Lync Server 2013: componenti utilizzati dal parcheggio di chiamata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576772"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="e4130-103">Componenti utilizzati dal parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4130-103">Components used by Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4130-104">_**Ultimo argomento modificato:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="e4130-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="e4130-105">L'applicazione Parcheggio di chiamata viene automaticamente installata quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e4130-105">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e4130-106">Si Abilita il parcheggio di chiamata configurando il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="e4130-106">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="e4130-107">I componenti di Lync Server 2013 seguenti supportano l'applicazione Parcheggio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="e4130-107">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="e4130-108">**Servizio applicazione**     Il servizio applicazione fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e4130-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="e4130-109">Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4130-109">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="e4130-110">Applicazione Parcheggio di **chiamata**     L'applicazione Parcheggio di chiamata è una delle applicazioni di comunicazione unificate ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4130-110">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="e4130-111">Viene inclusa automaticamente quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e4130-111">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e4130-112">Parchi parcheggio di chiamata e recupera le chiamate e gestisce le orbite del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e4130-112">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="e4130-113">**Music-on Hold-file**     Se la musica è abilitata, il file musicale viene riprodotto mentre una chiamata è parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="e4130-113">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="e4130-114">Quando è installata l'applicazione Parcheggio di chiamata, viene incluso un file di musica predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4130-114">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="e4130-115">**Archivio file**     L'applicazione Parcheggio di chiamata utilizza l'archivio file per contenere file audio personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e4130-115">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="e4130-116">Pannello di controllo di **Lync Server**     È possibile utilizzare il pannello di controllo di Lync Server per configurare la tabella di orbit del parcheggio di chiamata e per abilitare il parcheggio di chiamata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e4130-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="e4130-117">**Lync Server Management Shell**     Tutte le configurazioni dell'applicazione Parcheggio di chiamata possono essere eseguite utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e4130-117">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

