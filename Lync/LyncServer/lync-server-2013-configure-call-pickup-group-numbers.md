---
title: 'Lync Server 2013: configurare i numeri del gruppo di prelievo delle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e380e5b857a59405d42e382d18d7470395a5f580
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="61ea7-102">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61ea7-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61ea7-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="61ea7-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="61ea7-104">Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="61ea7-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="61ea7-105">Quando si distribuisce il prelievo delle chiamate di gruppo, è possibile configurare la tabella orbit del parcheggio di chiamata con intervalli di numeri di telefono designati come numeri del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="61ea7-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="61ea7-106">Questi numeri di gruppo sono i numeri che gli utenti chiamano per raccogliere le chiamate che squillano per un altro utente.</span><span class="sxs-lookup"><span data-stu-id="61ea7-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="61ea7-107">Analogamente ai numeri dell'orbita del parcheggio di chiamata, i numeri del gruppo di prelievo delle chiamate devono essere estensioni virtuali a cui non è assegnato alcun utente o telefono.</span><span class="sxs-lookup"><span data-stu-id="61ea7-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="61ea7-108">Ogni pool Front end in cui si distribuisce il prelievo delle chiamate di gruppo può avere uno o più intervalli di numeri del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="61ea7-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="61ea7-109">Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61ea7-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61ea7-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="61ea7-110">In This Section</span></span>

[<span data-ttu-id="61ea7-111">Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61ea7-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

