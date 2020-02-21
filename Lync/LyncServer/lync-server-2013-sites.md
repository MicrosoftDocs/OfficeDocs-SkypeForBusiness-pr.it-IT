---
title: Siti di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="08036-102">Siti di Lync Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08036-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08036-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="08036-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="08036-104">In Lync Server, è possibile definire i *siti* della rete che contengono componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08036-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="08036-105">Un sito è un insieme di computer connessi attraverso una rete a bassa latenza e alta velocità, come una singola rete LAN o due reti connesse tramite una rete a fibra ottica ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="08036-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="08036-106">Si noti che i siti di Lync Server sono un concetto separato dai siti di servizi di dominio Active Directory e dai siti di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="08036-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="08036-107">I siti di Lync Server non devono corrispondere ai siti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08036-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="08036-108">Tipi di sito</span><span class="sxs-lookup"><span data-stu-id="08036-108">Site Types</span></span>

<span data-ttu-id="08036-109">Ogni sito è un *sito centrale*, che contiene almeno un pool Front end o un server Standard Edition o un *sito di succursale*.</span><span class="sxs-lookup"><span data-stu-id="08036-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="08036-110">Ogni sito di succursale è associato a un solo sito centrale e gli utenti del sito di succursale ottengono la maggior parte delle funzionalità di Lync Server dai server nel sito centrale associato.</span><span class="sxs-lookup"><span data-stu-id="08036-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="08036-111">Ogni sito di succursale contiene uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="08036-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="08036-112">Un *Survivable Branch Appliance (SBA)*, che è un server blade standard del settore con un registrar di Lync Server e un Mediation Server in esecuzione su Windows Server.</span><span class="sxs-lookup"><span data-stu-id="08036-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="08036-113">Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="08036-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="08036-114">Il Survivable Branch Appliance è stato creato per i siti di succursale con gli utenti compresi tra 25 e 1000.</span><span class="sxs-lookup"><span data-stu-id="08036-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="08036-115">Un *Survivable Branch Server (SBS)*, che è un server che esegue Windows Server che soddisfa i requisiti hardware specificati, e che dispone di un software di registrazione di Lync Server e Mediation Server installato su di esso.</span><span class="sxs-lookup"><span data-stu-id="08036-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="08036-116">Deve connettersi a un gateway PSTN o a un trunk SIP verso un provider di servizi telefonici.</span><span class="sxs-lookup"><span data-stu-id="08036-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="08036-117">Il Survivable Branch Server è progettato per siti di succursale aventi da 1000 a 5000 utenti.</span><span class="sxs-lookup"><span data-stu-id="08036-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="08036-118">Un gateway PSTN e, facoltativamente, un *Mediation Server*.</span><span class="sxs-lookup"><span data-stu-id="08036-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="08036-119">Per informazioni dettagliate su questo e altri ruoli del server, vedere [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="08036-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="08036-120">In un sito di succursale con un collegamento WAN (Wide Area Network) resiliente a un sito centrale è possibile utilizzare la terza opzione, ovvero un gateway PSTN e facoltativamente un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="08036-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="08036-121">I siti di succursale con collegamenti con resilienza inferiore devono utilizzare un Survivable Branch Appliance o un Survivable Branch Server, che forniscono resilienza in periodi di problemi di rete a aree estese.</span><span class="sxs-lookup"><span data-stu-id="08036-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="08036-122">Ad esempio, in un sito con un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere chiamate vocali di VoIP aziendale se la rete WAN che collega il sito di succursale al sito centrale è inattivo.</span><span class="sxs-lookup"><span data-stu-id="08036-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="08036-123">Per informazioni dettagliate sul Survivable Branch Appliance, sul Survivable Branch Server e sulla resilienza, vedere [Planning for Enterprise Voice resilienzy in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="08036-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="08036-124">Topologie di siti</span><span class="sxs-lookup"><span data-stu-id="08036-124">Site Topologies</span></span>

<span data-ttu-id="08036-125">La distribuzione deve includere almeno un sito centrale e può includere da zero a numerosi siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="08036-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="08036-126">Ogni sito di succursale è affiliato a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="08036-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="08036-127">Nel sito centrale sono disponibili i servizi di Lync Server per il sito di succursale che non sono ospitati localmente nel sito di succursale, ad esempio la presenza e le conferenze.</span><span class="sxs-lookup"><span data-stu-id="08036-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="08036-128">Se sono disponibili più siti, sarà possibile accoppiare i pool Front End su siti diversi per abilitare le funzionalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="08036-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="08036-129">Per informazioni dettagliate, vedere Supporto per la [disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="08036-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08036-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08036-130">See Also</span></span>


[<span data-ttu-id="08036-131">Ruoli del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08036-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="08036-132">Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08036-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="08036-133">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08036-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

