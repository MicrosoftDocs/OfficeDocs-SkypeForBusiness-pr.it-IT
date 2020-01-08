---
title: 'Lync Server 2013: Requisiti tecnici per IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972b59ba2ea01f967d5cfb8a7767a4f322bcb2fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="3e79a-102">Requisiti tecnici per IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e79a-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e79a-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3e79a-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3e79a-104">Se si prevede di configurare Lync Server 2013 per IPv6, tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e79a-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="3e79a-105">Per usare gli indirizzi IPv6 con Lync Server, è necessario creare record DNS (Domain Name System) per i record che devono essere individuati e risolti in un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="3e79a-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="3e79a-106">DNS IPv6 usa record AAAA (Quad-A) host.</span><span class="sxs-lookup"><span data-stu-id="3e79a-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="3e79a-107">Se si usano sia IPv4 che IPv6 nella distribuzione, è consigliabile configurare e gestire sia l'host di un record per IPv4 che i record AAAA host per IPv6.</span><span class="sxs-lookup"><span data-stu-id="3e79a-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="3e79a-108">Anche quando si passa completamente la distribuzione a IPv6, è possibile che siano ancora necessari record host DNS IPv4 per gli utenti esterni che usano ancora IPv4.</span><span class="sxs-lookup"><span data-stu-id="3e79a-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="3e79a-109">È possibile distribuire record host DNS IPv6 prima di iniziare a usare IPv6.</span><span class="sxs-lookup"><span data-stu-id="3e79a-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="3e79a-110">Se il client o il server non usa IPv6, non verrà fatto riferimento al record.</span><span class="sxs-lookup"><span data-stu-id="3e79a-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="3e79a-111">Le tecnologie di transizione consentiranno di decidere quale record usare, in base alla configurazione e ai criteri di tecnologia di transizione.</span><span class="sxs-lookup"><span data-stu-id="3e79a-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="3e79a-112">Ogni indirizzo IPv6 ha un ambito.</span><span class="sxs-lookup"><span data-stu-id="3e79a-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="3e79a-113">I tre ambiti che è possibile usare per l'indirizzamento IPv6 sono indirizzi globali IPv6 (in modo simile agli indirizzi IPv4 pubblici), indirizzi locali univoci di IPv6 (in modo simile agli intervalli di indirizzi IPv4 privati) e indirizzi locali del collegamento IPv6 (in modo simile agli indirizzi IP privati automatici in Windows Server per IPv4).</span><span class="sxs-lookup"><span data-stu-id="3e79a-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="3e79a-114">Tutti i server all'interno di un pool devono avere indirizzi IPv6 con lo stesso ambito.</span><span class="sxs-lookup"><span data-stu-id="3e79a-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e79a-115">IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider Internet per assicurarti che gli indirizzi assegnati a livello di Windows Server e a livello di Lync Server 2013 funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="3e79a-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="3e79a-116">Vedere i collegamenti alla fine di questo argomento per altre risorse sull'indirizzamento e la pianificazione IPv6.</span><span class="sxs-lookup"><span data-stu-id="3e79a-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e79a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e79a-117">See Also</span></span>


[<span data-ttu-id="3e79a-118">Architettura di indirizzamento IP versione 6</span><span class="sxs-lookup"><span data-stu-id="3e79a-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="3e79a-119">Formato di indirizzo unicast globale IPv6</span><span class="sxs-lookup"><span data-stu-id="3e79a-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="3e79a-120">Indirizzi unicast IPv6 locali univoci</span><span class="sxs-lookup"><span data-stu-id="3e79a-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

