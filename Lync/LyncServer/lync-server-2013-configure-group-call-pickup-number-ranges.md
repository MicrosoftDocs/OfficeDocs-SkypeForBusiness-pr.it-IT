---
title: 'Lync Server 2013: configurare gli intervalli di numeri di raccolta delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13bd822dda38dd3b6cb5d6b801460ad463375e62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="01546-102">Configurare gli intervalli di numeri di raccolta delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01546-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01546-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="01546-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="01546-104">Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="01546-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="01546-105">Quando si distribuisce il pickup di una chiamata di gruppo, è possibile configurare la tabella Orbit di Call Park con intervalli di numeri di telefono designati come numeri di gruppo di prelievo chiamate.</span><span class="sxs-lookup"><span data-stu-id="01546-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="01546-106">Questi numeri di gruppo sono i numeri che gli utenti chiamano per raccogliere chiamate che squillano per un altro utente.</span><span class="sxs-lookup"><span data-stu-id="01546-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="01546-107">Come i numeri dell'orbita di Call Park, i numeri dei gruppi di pickup delle chiamate devono essere estensioni virtuali che non hanno un utente o un telefono assegnato.</span><span class="sxs-lookup"><span data-stu-id="01546-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="01546-108">Ogni pool Front end in cui si distribuisce il pickup di una chiamata di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamate.</span><span class="sxs-lookup"><span data-stu-id="01546-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="01546-109">Gli intervalli di numeri di gruppo devono essere univoci a livello globale in tutta la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01546-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01546-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="01546-110">In This Section</span></span>

  - [<span data-ttu-id="01546-111">Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01546-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="01546-112">Eliminare un intervallo di numeri di prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01546-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

