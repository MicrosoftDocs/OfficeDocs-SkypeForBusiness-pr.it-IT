---
title: "Lync Server 2013: Configurare l'accesso automatico dei client per l'utilizzo del server Director"
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
ms.openlocfilehash: b9a6d9090796b2c6c2271025ed4d17a134943c11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="61579-102">Configurare l'accesso automatico dei client per l'utilizzo del server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61579-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61579-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="61579-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="61579-104">Quando si distribuisce un Lync Server 2013, un amministratore o un pool di amministratori, è consigliabile usare l'accesso automatico client come procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="61579-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="61579-105">Per informazioni dettagliate su come configurare i server DNS per l'accesso automatico al client, vedere [requisiti DNS per l'accesso automatico client in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="61579-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="61579-106">Se è già stata distribuita l'accesso automatico al client, vedere le sezioni seguenti per configurarla in un Director o in un amministratore.</span><span class="sxs-lookup"><span data-stu-id="61579-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="61579-107">Istanza Single Director</span><span class="sxs-lookup"><span data-stu-id="61579-107">Single Director Instance</span></span>

<span data-ttu-id="61579-108">Se è già stata distribuita l'accesso automatico al client e punta a un server front-end o a un pool Front-End, è necessario modificare il record SRV DNS in maniera che punti al Director.</span><span class="sxs-lookup"><span data-stu-id="61579-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="61579-109">Pool di Director</span><span class="sxs-lookup"><span data-stu-id="61579-109">Director Pool</span></span>

<span data-ttu-id="61579-110">Se è già stata distribuita l'accesso automatico al client e punta a un server front-end o a un pool Front-End, è necessario modificare il record SRV DNS in maniera che punti al pool di Director.</span><span class="sxs-lookup"><span data-stu-id="61579-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

