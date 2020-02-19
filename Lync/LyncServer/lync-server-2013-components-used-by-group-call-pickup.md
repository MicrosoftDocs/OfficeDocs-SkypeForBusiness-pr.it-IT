---
title: 'Lync Server 2013: componenti utilizzati dal prelievo delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05f41b7420f15c2815ababa0f85d8aca43898dd2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="9d10c-102">Componenti utilizzati dal ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d10c-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d10c-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9d10c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9d10c-104">Il prelievo delle chiamate di gruppo viene distribuito automaticamente quando si distribuisce VoIP aziendale e l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9d10c-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="9d10c-105">È possibile abilitare il ritiro delle chiamate di gruppo configurando la tabella orbit del parcheggio di chiamata con intervalli di numeri distinti designati come numeri del gruppo di prelievo di chiamata e quindi assegnando gli utenti ai gruppi di prelievo di chiamata e abilitando gli utenti al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9d10c-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="9d10c-106">I seguenti componenti di Lync Server supportano il ritiro delle chiamate di gruppo:</span><span class="sxs-lookup"><span data-stu-id="9d10c-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="9d10c-107">**Application Service**   Application Service fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9d10c-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="9d10c-108">Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9d10c-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="9d10c-109">**Applicazione Parcheggio di chiamata**   l'applicazione Parcheggio di chiamata è una delle applicazioni di comunicazione unificata ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d10c-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="9d10c-110">Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9d10c-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="9d10c-111">**Lync Server Management Shell**   si utilizza Lync Server Management Shell per gestire i gruppi di prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9d10c-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="9d10c-112">**Strumento di SEFAUtil Resource Kit**   utilizzare l'utilità di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare gli utenti a un gruppo di prelievo di chiamata e per abilitare o disabilitare il servizio di prelievo delle chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9d10c-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

