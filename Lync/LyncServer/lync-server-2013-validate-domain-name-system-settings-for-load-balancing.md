---
title: 'Lync Server 2013: convalida delle impostazioni di sistema dei nomi di dominio per il bilanciamento del carico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="6d9bc-102">Convalidare le impostazioni di sistema dei nomi di dominio per il bilanciamento del carico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d9bc-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d9bc-103">_**Argomento Ultima modifica:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="6d9bc-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="6d9bc-104">Per supportare il nome di dominio completo usato dal bilanciamento del carico DNS, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio pool01.contoso.com, agli indirizzi IP di tutti i server del pool (ad es. 192.168.1.1, 192.168.1.2 e così via).</span><span class="sxs-lookup"><span data-stu-id="6d9bc-104">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="6d9bc-105">Dovresti includere solo gli indirizzi IP dei server attualmente distribuiti.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-105">You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="6d9bc-106">Inoltre, se si usa il bilanciamento del carico DNS per i pool di bordi, sono necessarie le seguenti voci DNS:</span><span class="sxs-lookup"><span data-stu-id="6d9bc-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="6d9bc-107">Per il servizio Access Edge di Lync Server è necessario disporre di una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="6d9bc-108">Ogni voce deve risolvere il nome di dominio completo di Lync Server Access Edge service, ad esempio sip.contoso.com, all'indirizzo IP del servizio Access Edge di Lync Server in uno degli Edge Server del pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="6d9bc-109">Per il servizio Web Conferencing Edge di Lync Server, è necessario avere una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="6d9bc-110">Ogni voce deve risolvere il nome di dominio completo di Lync Server Web Conferencing Edge Services, ad esempio webconf.contoso.com, all'indirizzo IP di Lync Server Web Conferencing Edge Services in uno degli Edge Server del pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="6d9bc-111">Per il servizio Edge audio/video di Lync Server è necessario disporre di una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="6d9bc-112">Ogni voce deve risolvere il nome di dominio completo del servizio Edge audio/video di Lync Server, ad esempio av.contoso.com, all'indirizzo IP del servizio Edge audio/video di Lync Server in uno degli Edge Server del pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="6d9bc-113">Se si vuole usare il bilanciamento del carico DNS nell'interfaccia interna del pool di Edge, è necessario aggiungere un record DNS, che risolve il nome di dominio completo interno del pool di Edge nell'indirizzo IP di ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="6d9bc-114">Per verificare che il DNS stia restituendo i valori corretti per il bilanciamento del carico DNS, usare lo strumento Nslookup.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="6d9bc-115">Per restituire tutti i valori di un record DNS con Nslookup, eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="6d9bc-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="6d9bc-116">Eseguire questo comando per ogni nome di dominio completo usato nella configurazione di bilanciamento del carico DNS per verificare che ogni set di record per il bilanciamento del carico DNS restituisca tutte le voci corrette.</span><span class="sxs-lookup"><span data-stu-id="6d9bc-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

