---
title: 'Lync Server 2013: Configurare la tabella di codici orbit del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="27002-102">Configurare la tabella di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27002-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27002-103">_**Argomento Ultima modifica:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="27002-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="27002-104">Call Park USA orbite per le chiamate di parcheggio.</span><span class="sxs-lookup"><span data-stu-id="27002-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="27002-105">Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="27002-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="27002-106">Devi specificare gli intervalli di numeri di interno (orbite) che l'organizzazione riserva alle chiamate di parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="27002-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="27002-107">Quando definisci intervalli orbitali, l'obiettivo è quello di avere orbite sufficienti in modo che una qualsiasi orbita non venga riutilizzata troppo rapidamente, ma non così tante orbite che limiti il numero di estensioni disponibili per gli utenti o altri servizi.</span><span class="sxs-lookup"><span data-stu-id="27002-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="27002-108">È possibile creare più intervalli di orbita del parcheggio di chiamata per ogni pool di Lync Server in cui è distribuita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27002-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="27002-109">Ogni intervallo di Orbit di Call Park deve avere un nome univoco globale e un set di estensioni univoco.</span><span class="sxs-lookup"><span data-stu-id="27002-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="27002-110">Un intervallo orbit include in genere 100 o meno orbite.</span><span class="sxs-lookup"><span data-stu-id="27002-110">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="27002-111">Ogni intervallo può essere molto più grande, purché sia più piccolo del massimo di 10.000 orbite per intervallo e si hanno meno di 50.000 orbite per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="27002-111">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="27002-112">Se un intervallo è troppo piccolo, le orbite vengono riutilizzate più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="27002-112">If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="27002-113">Usare blocchi di estensioni virtuali (estensioni che non hanno un utente o un telefono assegnato) per gli intervalli di Orbit.</span><span class="sxs-lookup"><span data-stu-id="27002-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27002-114">L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata.</span><span class="sxs-lookup"><span data-stu-id="27002-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27002-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="27002-115">In This Section</span></span>

[<span data-ttu-id="27002-116">Creare o modificare un intervallo orbit di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27002-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

