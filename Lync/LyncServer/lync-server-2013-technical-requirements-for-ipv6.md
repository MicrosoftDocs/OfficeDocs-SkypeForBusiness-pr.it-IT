---
title: Lync Server 2013 requisiti tecnici per IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6513af4598f36aa510181e6971ccb6962cd44f91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="c5530-102">Requisiti tecnici per IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5530-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5530-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c5530-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c5530-104">Se si prevede di configurare Lync Server 2013 per IPv6, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c5530-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="c5530-105">Per utilizzare gli indirizzi IPv6 con Lync Server, è necessario creare record DNS (Domain Name System) per i record che devono essere individuati e risolti in un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="c5530-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="c5530-106">Il DNS IPv6 utilizza record AAAA (A quadrupla) dell'host.</span><span class="sxs-lookup"><span data-stu-id="c5530-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="c5530-107">Se si utilizzano entrambi gli indirizzamenti IPv4 e IPv6 nella distribuzione, è consigliabile configurare e gestire sia i record A dell'host per IPv4 che i record AAAA dell'host per IPv6.</span><span class="sxs-lookup"><span data-stu-id="c5530-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="c5530-108">Anche in caso di transizione completa della distribuzione a IPv6, è possibile che siano comunque necessari record dell'host DNS IPv4 per gli utenti esterni che continuano a utilizzare IPv4.</span><span class="sxs-lookup"><span data-stu-id="c5530-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="c5530-109">È possibile distribuire record DNS IPv6 prima di iniziare a utilizzare IPv6.</span><span class="sxs-lookup"><span data-stu-id="c5530-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="c5530-110">Se il client o il server non utilizza IPv6, il record non verrà utilizzato come riferimento.</span><span class="sxs-lookup"><span data-stu-id="c5530-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="c5530-111">Le tecnologie transitorie sceglieranno quale record utilizzare in base alla configurazione e ai criteri della tecnologia.</span><span class="sxs-lookup"><span data-stu-id="c5530-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="c5530-112">Ogni indirizzo IPv6 prevede un ambito.</span><span class="sxs-lookup"><span data-stu-id="c5530-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="c5530-113">I tre ambiti che è possibile utilizzare per l'indirizzamento IPv6 sono gli indirizzi globali IPv6 (simili agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (simili agli intervalli di indirizzi IPv4 privati) e gli indirizzi del collegamento IPv6 (simili agli indirizzi IP privati automatici in Windows Server per IPv4).</span><span class="sxs-lookup"><span data-stu-id="c5530-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="c5530-114">Tutti i server di un pool devono disporre di indirizzi IPv6 con lo stesso ambito.</span><span class="sxs-lookup"><span data-stu-id="c5530-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c5530-115">IPv6 è un argomento complesso che richiede una pianificazione accurata con il team di rete e il provider di servizi Internet per garantire che gli indirizzi assegnati a livello di Windows Server e al livello di Lync Server 2013 funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="c5530-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="c5530-116">Vedere i collegamenti alla fine dell'argomento per risorse aggiuntive sull'indirizzamento IPv6 e la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c5530-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5530-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5530-117">See Also</span></span>


[<span data-ttu-id="c5530-118">Architettura di indirizzamento IP versione 6</span><span class="sxs-lookup"><span data-stu-id="c5530-118">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="c5530-119">Formato di indirizzo unicast globale IPv6</span><span class="sxs-lookup"><span data-stu-id="c5530-119">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="c5530-120">Indirizzi unicast IPv6 locali univoci</span><span class="sxs-lookup"><span data-stu-id="c5530-120">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

