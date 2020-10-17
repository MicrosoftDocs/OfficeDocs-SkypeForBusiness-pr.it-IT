---
title: "Lync Server 2013: configurare Sign-In di client automatici per l'utilizzo del Director"
description: "Lync Server 2013: configurare i Sign-In automatici dei client per l'utilizzo del Director."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9c45a1a677d3a30704d8dca1771ef865cef29ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546652"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="218a4-103">Configurare Sign-In automatici dei client per l'utilizzo del server Director in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="218a4-103">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="218a4-104">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="218a4-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="218a4-105">Quando si distribuisce un Lync Server 2013, un Director o un pool di Director, è consigliabile utilizzare il Sign-In automatico client come procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="218a4-105">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="218a4-106">Per informazioni dettagliate su come configurare i server DNS per l'accesso automatico dei client, vedere [DNS requirements for Automatic client Sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="218a4-106">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="218a4-107">Se l'accesso automatico dei client è già stato distribuito, vedere le sezioni seguenti per configurarlo nel server o nei server Director.</span><span class="sxs-lookup"><span data-stu-id="218a4-107">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="218a4-108">Istanza di server Director singolo</span><span class="sxs-lookup"><span data-stu-id="218a4-108">Single Director Instance</span></span>

<span data-ttu-id="218a4-109">Se sono già stati distribuiti client automatici Sign-In che puntano a un front end server o a un pool Front End, è necessario modificare il record DNS SRV per puntare al Director.</span><span class="sxs-lookup"><span data-stu-id="218a4-109">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="218a4-110">Pool di server Director</span><span class="sxs-lookup"><span data-stu-id="218a4-110">Director Pool</span></span>

<span data-ttu-id="218a4-111">Se sono già stati distribuiti client automatici Sign-In che puntano a un front end server o a un pool Front End, è necessario modificare il record DNS SRV in modo che puntino al pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="218a4-111">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

