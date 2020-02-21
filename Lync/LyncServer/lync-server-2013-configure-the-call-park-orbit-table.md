---
title: 'Lync Server 2013: configurare la tabella di orbit del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce2919e783b24148cd6526a1b4ecfbf082c11985
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="fff78-102">Configurare la tabella di orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff78-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fff78-103">_**Ultimo argomento modificato:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="fff78-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="fff78-104">Il parcheggio di chiamata utilizza le orbite per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="fff78-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="fff78-105">Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella di orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fff78-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="fff78-106">È necessario specificare gli intervalli di numeri di interno (orbite) che l'organizzazione prenoterà per le chiamate al parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="fff78-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="fff78-107">Quando si definiscono gli intervalli di codici orbit, l'obiettivo è quello di disporre di un numero sufficiente di codici orbit tale da evitare che uno stesso codice orbit venga riutilizzato troppo rapidamente, ma senza eccedere limitando il numero di interni disponibili per gli utenti o altri servizi.</span><span class="sxs-lookup"><span data-stu-id="fff78-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="fff78-108">È possibile creare più intervalli di orbit del parcheggio di chiamata per ogni pool di Lync Server in cui è distribuita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fff78-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="fff78-109">Ogni intervallo di orbit del parcheggio di chiamata deve disporre di un nome univoco globale e di un insieme univoco di estensioni.</span><span class="sxs-lookup"><span data-stu-id="fff78-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fff78-p102">Un intervallo di codici orbit include in genere al massimo 100 codici orbit. Ogni intervallo può essere più grande, purché sia più piccolo del massimo di 10.000 codici orbit per intervallo e ogni pool includa meno di 50.000 codici orbit. Se un intervallo è troppo piccolo, i codici orbit vengono riutilizzati più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="fff78-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="fff78-113">Utilizzare blocchi di estensioni virtuali, ovvero a cui non sono assegnati utenti o telefoni, per gli intervalli di codici orbit.</span><span class="sxs-lookup"><span data-stu-id="fff78-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fff78-114">L'assegnazione dei numeri DID (Direct Inward Dialing) ai numeri orbitali nella tabella orbit del parcheggio di chiamata non è supportata.</span><span class="sxs-lookup"><span data-stu-id="fff78-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fff78-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="fff78-115">In This Section</span></span>

[<span data-ttu-id="fff78-116">Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff78-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

