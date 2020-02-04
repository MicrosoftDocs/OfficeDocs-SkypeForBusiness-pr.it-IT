---
title: 'Lync Server 2013: Componenti utilizzati dal parcheggio di chiamata'
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
ms.openlocfilehash: ae458d7ef3245e366e4f2bdd61f192401909213b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="7f30f-102">Componenti utilizzati dal parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f30f-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f30f-103">_**Argomento Ultima modifica:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="7f30f-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="7f30f-104">L'applicazione Call Park viene automaticamente installata quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7f30f-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7f30f-105">Si Abilita il parcheggio delle chiamate configurando il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="7f30f-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="7f30f-106">I componenti di Lync Server 2013 seguenti supportano l'applicazione Parcheggio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="7f30f-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="7f30f-107">**Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione di applicazioni di comunicazioni unificate, ad esempio l'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="7f30f-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="7f30f-108">Il servizio applicazione viene installato automaticamente in ogni server front-end in un pool Front-end e in ogni server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7f30f-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="7f30f-109">**Call Park application**   l'applicazione Call Park è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f30f-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="7f30f-110">Viene incluso automaticamente quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7f30f-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7f30f-111">Chiama parchi parcheggiati e recupera le chiamate e gestisce le orbite di Call Park.</span><span class="sxs-lookup"><span data-stu-id="7f30f-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="7f30f-112">**Musica in attesa-file**   se la musica è abilitata, il file musicale viene riprodotto durante il parcheggio di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f30f-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="7f30f-113">Viene incluso un file di musica predefinito quando viene installata l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f30f-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="7f30f-114">**Archivio file l'**   applicazione Call Park USA archivio file per contenere file audio personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7f30f-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="7f30f-115">**Pannello di controllo di Lync Server**   è possibile usare il pannello di controllo di Lync Server per configurare la tabella Orbit di Call Park e per abilitare il parcheggio delle chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7f30f-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="7f30f-116">**Lync Server Management Shell**   tutte le configurazioni delle applicazioni di Call Park possono essere eseguite usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7f30f-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

