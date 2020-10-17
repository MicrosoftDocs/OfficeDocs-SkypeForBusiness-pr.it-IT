---
title: Preparazione per l'installazione dei server nella rete perimetrale
description: Preparazione per l'installazione dei server nella rete perimetrale.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5689d7990cc1ddf91ad6487d8abed08f40cd3db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549922"
---
# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="1ee94-103">Preparazione per l'installazione dei server nella rete perimetrale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-103">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee94-104">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1ee94-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1ee94-105">Prima di installare i componenti Edge Server, è necessario verificare che i computer che si sta configurando soddisfino i requisiti di sistema ed eseguire altri passaggi prerequisiti necessari per la distribuzione dei componenti Edge Server.</span><span class="sxs-lookup"><span data-stu-id="1ee94-105">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="1ee94-106">Prima di iniziare, esaminare le informazioni dettagliate negli argomenti seguenti della documentazione relativa alla pianificazione per l'architettura di riferimento che si desidera distribuire:</span><span class="sxs-lookup"><span data-stu-id="1ee94-106">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="1ee94-107">Singolo server perimetrale consolidato con indirizzi IP privati e NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="1ee94-108">Perimetro consolidato singolo con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="1ee94-109">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="1ee94-110">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="1ee94-111">Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ee94-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="1ee94-112">In This Section</span></span>

  - [<span data-ttu-id="1ee94-113">Configurare DNS per il supporto Edge in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-113">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="1ee94-114">Configurare i dispositivi di bilanciamento del carico hardware per le topologie perimetrali in scala in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-114">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="1ee94-115">Configurare firewall e porte per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-115">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="1ee94-116">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-116">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="1ee94-117">Richiedere i certificati per i componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee94-117">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

