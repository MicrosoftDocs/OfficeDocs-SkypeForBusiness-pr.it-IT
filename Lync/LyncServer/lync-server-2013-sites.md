---
title: Siti di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="b299f-102">Siti di Lync Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b299f-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b299f-103">_**Argomento Ultima modifica:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="b299f-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="b299f-104">In Lync Server è possibile definire i *siti* della rete che contengono componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b299f-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="b299f-105">Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="b299f-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="b299f-106">Si noti che i siti di Lync Server sono un concetto separato da siti di servizi di dominio Active Directory e siti di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b299f-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="b299f-107">I siti di Lync Server non devono corrispondere ai siti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b299f-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="b299f-108">Tipi di sito</span><span class="sxs-lookup"><span data-stu-id="b299f-108">Site Types</span></span>

<span data-ttu-id="b299f-109">Ogni sito è un *sito centrale*, che contiene almeno un pool di front end o un server Standard Edition o un sito di *succursale*.</span><span class="sxs-lookup"><span data-stu-id="b299f-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="b299f-110">Ogni sito di succursale è associato a un sito centrale e gli utenti del sito della filiale ottengono la maggior parte delle funzionalità di Lync Server dai server del sito centrale associato.</span><span class="sxs-lookup"><span data-stu-id="b299f-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="b299f-111">Ogni sito di succursale contiene una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b299f-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="b299f-112">Un *Survivable Branch Appliance (SBA)*, un server blade di livello industriale con un registrar di Lync Server e un Mediation Server in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b299f-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="b299f-113">Il Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="b299f-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="b299f-114">Survivable Branch Appliance è progettato per i siti di succursale con utenti compresi tra 25 e 1000.</span><span class="sxs-lookup"><span data-stu-id="b299f-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="b299f-115">Un *Survivable Branch Server (SBS)*, un server che utilizza Windows Server che soddisfa i requisiti hardware specificati e che include il software di registrazione di Lync Server e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b299f-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="b299f-116">Deve essere collegato a un gateway PSTN o a un trunk SIP a un provider di servizi telefonici.</span><span class="sxs-lookup"><span data-stu-id="b299f-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="b299f-117">Il Survivable Branch Server è progettato per i siti di succursale tra gli utenti di 1000 e 5000.</span><span class="sxs-lookup"><span data-stu-id="b299f-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="b299f-118">Un gateway PSTN e, facoltativamente, un *Mediation Server*.</span><span class="sxs-lookup"><span data-stu-id="b299f-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="b299f-119">Per informazioni dettagliate su questo e altri ruoli del server, vedere [ruoli del server in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b299f-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="b299f-120">Una filiale con un collegamento WAN (Wide Area Network) resiliente a un sito centrale può usare la terza opzione, ovvero un gateway PSTN e, facoltativamente, un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b299f-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="b299f-121">I siti di succursale con collegamenti meno resilienti devono usare un Survivable Branch Appliance o un Survivable Branch Server, che garantiscono la resilienza in tempi di errori di rete wide-area.</span><span class="sxs-lookup"><span data-stu-id="b299f-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="b299f-122">Ad esempio, in un sito con un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere le chiamate vocali aziendali se la WAN che connette il sito della filiale al sito centrale è in calo.</span><span class="sxs-lookup"><span data-stu-id="b299f-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="b299f-123">Per informazioni dettagliate su Survivable Branch Appliance, Survivable Branch Server e resilienza, vedere [pianificazione della resilienza di Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b299f-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="b299f-124">Topologie del sito</span><span class="sxs-lookup"><span data-stu-id="b299f-124">Site Topologies</span></span>

<span data-ttu-id="b299f-125">La distribuzione deve includere almeno un sito centrale e può includere zero in molti siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="b299f-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="b299f-126">Ogni sito di succursale è affiliato a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="b299f-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="b299f-127">Il sito centrale fornisce i servizi di Lync Server al sito della filiale che non sono ospitati localmente nel sito della filiale, ad esempio presenza e conferenza.</span><span class="sxs-lookup"><span data-stu-id="b299f-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="b299f-128">Se si hanno più siti, è possibile abbinare i pool Front-end in siti diversi per abilitare le abilità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b299f-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="b299f-129">Per informazioni dettagliate, vedere Supporto per la [disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="b299f-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b299f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b299f-130">See Also</span></span>


[<span data-ttu-id="b299f-131">Ruoli del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b299f-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="b299f-132">Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b299f-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="b299f-133">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b299f-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

