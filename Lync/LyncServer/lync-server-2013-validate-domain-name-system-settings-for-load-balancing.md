---
title: 'Lync Server 2013: convalidare le impostazioni di sistema del nome di dominio per il bilanciamento del carico'
description: 'Lync Server 2013: convalidare le impostazioni di sistema del nome di dominio per il bilanciamento del carico.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547232"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="8b7dd-103">Convalidare le impostazioni di sistema del nome di dominio per il bilanciamento del carico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b7dd-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b7dd-104">_**Ultimo argomento modificato:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="8b7dd-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="8b7dd-p101">Per supportare il nome di dominio completo utilizzato dal bilanciamento del carico DNS, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio pool01.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via). Includere solo gli indirizzi IP dei server attualmente distribuiti.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="8b7dd-107">Inoltre, se si utilizza il bilanciamento del carico DNS per i pool di server perimetrali, sono necessarie le seguenti voci DNS:</span><span class="sxs-lookup"><span data-stu-id="8b7dd-107">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="8b7dd-108">Per il servizio Lync Server Access Edge, è necessario disporre di una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-108">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="8b7dd-109">Ogni voce deve risolvere il nome di dominio completo del servizio Lync Server Access Edge (ad esempio, sip.contoso.com) all'indirizzo IP del servizio Lync Server Access Edge in uno dei server perimetrali del pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-109">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8b7dd-110">Per il servizio Web Conferencing Edge di Lync Server, è necessario disporre di una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-110">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="8b7dd-111">Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge di Lync Server (ad esempio, webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge di Lync Server in uno dei server perimetrali del pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-111">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8b7dd-112">Per Lync Server audio/video Edge service, è necessario disporre di una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-112">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="8b7dd-113">Ogni voce deve risolvere il nome di dominio completo di Lync Server audio/video Edge del servizio (ad esempio, av.contoso.com) per l'indirizzo IP del servizio Lync Server audio/video Edge su uno dei server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-113">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8b7dd-114">Se si desidera utilizzare il bilanciamento del carico DNS nell'interfaccia interna del pool di server perimetrali, è necessario aggiungere un record DNS, che consente di risolvere il nome di dominio completo interno del pool perimetrale nell'indirizzo IP di ognuno di essi del pool.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-114">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="8b7dd-115">Per verificare che DNS restituisca i valori corretti per il bilanciamento del carico DNS, è necessario utilizzare lo strumento Nslookup.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-115">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="8b7dd-116">Per restituire tutti i valori di un record DNS con Nslookup, è necessario eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="8b7dd-116">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="8b7dd-117">Eseguire questo comando per ogni nome di dominio completo utilizzato nella configurazione del bilanciamento del carico DNS per verificare che ogni set di record per il bilanciamento del carico DNS abbia restituito tutte le voci corrette.</span><span class="sxs-lookup"><span data-stu-id="8b7dd-117">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

