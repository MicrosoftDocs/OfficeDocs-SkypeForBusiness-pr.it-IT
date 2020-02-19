---
title: "Lync Server 2013: elenco di controllo di distribuzione per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5010608f05f99d1d1830874a80b6f9f44fd25b38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f5e58-102">Elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5e58-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5e58-103">_**Ultimo argomento modificato:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="f5e58-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="f5e58-104">Prima di distribuire la rete perimetrale e implementare il supporto per gli utenti esterni, è necessario che siano già stati distribuiti i server interni di Microsoft Lync Server 2013, tra cui un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f5e58-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="f5e58-105">Se si prevede di distribuire i Director facoltativi nella rete interna, è consigliabile distribuirli anche prima di distribuire i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="f5e58-106">Per informazioni dettagliate sul processo di distribuzione del Director, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="f5e58-107">Microsoft Lync Server 2013 include strumenti che facilitano la pianificazione e la distribuzione di entrambi i server interni e server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="f5e58-108">Al completamento della topologia, pubblicare la definizione di topologia risultante nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="f5e58-109">A tale scopo, è necessario essere membri dei gruppi **Domain Admins** e **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="f5e58-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="f5e58-110">**Strumento di pianificazione**   Office Communications Server 2007 R2 includeva uno strumento di pianificazione e uno strumento di pianificazione Edge che è possibile utilizzare per semplificare la progettazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="f5e58-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="f5e58-111">In Lync Server 2010, questi due strumenti sono stati combinati in un unico strumento di pianificazione con caratteristiche e funzionalità aggiuntive, ad esempio la raccolta dei conteggi degli utenti pianificati, i requisiti vocali, i tipi di accesso degli utenti esterni e le opzioni di Federazione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="f5e58-112">Inoltre, è possibile pianificare i parametri di rete di un'infrastruttura, inclusi gli indirizzi IP, i tipi di servizio di bilanciamento del carico e altre considerazioni in merito alle reti perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="f5e58-113">**Generatore di**   topologie in Generatore di topologie Lync Server 2013 consente di definire la topologia e i componenti.</span><span class="sxs-lookup"><span data-stu-id="f5e58-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="f5e58-114">Generatore di topologie è essenziale per la distribuzione di server che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5e58-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="f5e58-115">Il generatore di topologie pubblica i risultati in un archivio di gestione centrale utilizzato per configurare tutti i server che eseguono Lync Server 2013 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="f5e58-116">Non è possibile installare Lync Server 2013 nei server senza l'utilizzo di generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="f5e58-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="f5e58-117">Se è stata progettata la topologia perimetrale durante il processo di pianificazione, incluso l'esecuzione di generatore di topologie per definire la topologia perimetrale, è possibile utilizzare tali risultati per avviare la distribuzione del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f5e58-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="f5e58-118">Se la topologia perimetrale non è stata completata o si desidera modificare le informazioni precedentemente specificate, è necessario completare l'esecuzione di generatore di topologie prima di procedere con altri passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="f5e58-119">Per informazioni dettagliate su come creare la topologia, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f5e58-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="f5e58-120">Per informazioni dettagliate sullo strumento di pianificazione e sul generatore di topologie, vedere [beginning the Planning Process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="f5e58-121">Nella tabella riportata di seguito viene fornita una panoramica del processo di distribuzione dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="f5e58-122">Per esaminare le decisioni di pianificazione che devono essere apportate prima di distribuire l'accesso degli utenti esterni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f5e58-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f5e58-123">Le informazioni riportate nella tabella seguente fanno riferimento a una nuova distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="f5e58-124">Se sono stati distribuiti server perimetrali in un ambiente Lync Server 2010, Office Communications Server 2007 R2 o Office Communications Server 2007, vedere la pagina relativa alla <A href="migration.md">migrazione</A> per informazioni dettagliate sulla migrazione a lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5e58-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="f5e58-125">La migrazione non è supportata da una versione precedente a Office Communications Server 2007 R2, tra cui Office Communications Server 2007, Live Communications Server 2005 e Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f5e58-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="f5e58-126">Per migliorare la sicurezza e le prestazioni dei server perimetrali e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuiscono la rete perimetrale e i server perimetrali:</span><span class="sxs-lookup"><span data-stu-id="f5e58-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="f5e58-127">Distribuire i server perimetrali solo dopo aver testato e verificato l'operazione di Lync Server 2013 all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="f5e58-p108">Si consiglia di distribuire i server perimetrali in un gruppo di lavoro anziché in un dominio. In questo modo si semplifica l'installazione e si mantengono i Servizi di dominio Active Directory (AD DS) al di fuori della rete perimetrale. La presenza dei servizi AD DS nella rete perimetrale può infatti costituire un rischio di sicurezza significativo.</span><span class="sxs-lookup"><span data-stu-id="f5e58-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="f5e58-p109">L'unione di un server perimetrale a un dominio situato interamente nella rete perimetrale è supportata ma non consigliata. Un server perimetrale come parte del dominio interno viola i limiti di attendibilità della rete, in cui Internet presenta attendibilità minima, la rete perimetrale attendibilità superiore e la rete interna attendibilità massima. Un server perimetrale come membro del dominio fa automaticamente parte della rete più attendibile, ma risiede in una rete meno attendibile (il perimetro).</span><span class="sxs-lookup"><span data-stu-id="f5e58-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="f5e58-134">Processo di distribuzione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="f5e58-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5e58-135">Fase</span><span class="sxs-lookup"><span data-stu-id="f5e58-135">Phase</span></span></th>
<th><span data-ttu-id="f5e58-136">Passaggi</span><span class="sxs-lookup"><span data-stu-id="f5e58-136">Steps</span></span></th>
<th><span data-ttu-id="f5e58-137">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f5e58-137">Permissions</span></span></th>
<th><span data-ttu-id="f5e58-138">Documentazione</span><span class="sxs-lookup"><span data-stu-id="f5e58-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5e58-139">Creare la topologia perimetrale appropriata e determinare i componenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="f5e58-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f5e58-140">Eseguire Generatore di topologie per configurare le impostazioni del server perimetrale e creare e pubblicare la topologia e quindi utilizzare Lync Server Management Shell per esportare il file di configurazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="f5e58-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f5e58-141">Gruppo <strong>Domain Admins</strong> e gruppo <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong></span><span class="sxs-lookup"><span data-stu-id="f5e58-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f5e58-142">È possibile definire una topologia utilizzando un account membro del gruppo degli utenti locali, ma per la pubblicazione di una topologia è necessario un account membro dei gruppi <STRONG>Domain Admins</STRONG> e <STRONG>RTCUniversalServerAdmins</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f5e58-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="f5e58-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia Edge e Director in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e58-144">Preparare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f5e58-145">Verificare che vengano soddisfatti i prerequisiti del sistema.</span><span class="sxs-lookup"><span data-stu-id="f5e58-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-146">Configurare gli indirizzi IP (IPv4 e IPv6, se utilizzati) per le interfacce di rete interne e pubbliche in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f5e58-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-147">Configurare record DNS interni ed esterni (host A e AAAA per IPv4 e IPv6), inclusa la configurazione del suffisso DNS nel computer da distribuire come server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f5e58-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-p110">(Facoltativo) Creare e installare certificati pubblici. Il tempo necessario per ottenere i certificati dipende dall'Autorità di certificazione (CA) che emette il certificato. Se non si esegue questo passaggio in questa fase, sarà necessario eseguirlo durante l'installazione dei server perimetrali. I servizi dei server perimetrali non possono essere avviati se non si ottengono e installano i certificati.</span><span class="sxs-lookup"><span data-stu-id="f5e58-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-p111">Fornire il supporto per la connettività per messaggistica istantanea pubblica se la distribuzione deve supportare le comunicazioni con utenti di Windows Live, AOL o Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="f5e58-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f5e58-154">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="f5e58-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f5e58-155">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f5e58-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f5e58-156">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="f5e58-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="f5e58-157">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f5e58-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f5e58-158">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="f5e58-158">has been announced.</span></span> <span data-ttu-id="f5e58-159">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5e58-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f5e58-160">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f5e58-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f5e58-161">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="f5e58-161">Messenger.</span></span> <span data-ttu-id="f5e58-162">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="f5e58-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f5e58-163">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="f5e58-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f5e58-164">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="f5e58-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f5e58-165">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="f5e58-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="f5e58-166">Provisioning del supporto per il supporto di XMPP e federativo per Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se la distribuzione utilizzerà questi</span><span class="sxs-lookup"><span data-stu-id="f5e58-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="f5e58-167">Configurare i firewall.</span><span class="sxs-lookup"><span data-stu-id="f5e58-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f5e58-168">In base all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f5e58-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="f5e58-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparazione per l'installazione dei server nella rete perimetrale per Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e58-170">Configurare il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f5e58-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f5e58-171">Configurare il proxy inverso (ad esempio, per Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) nella rete perimetrale, ottenere i certificati pubblici necessari e configurare la regole di pubblicazione Web nel server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f5e58-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="f5e58-172">Preparare il proxy inverso per i servizi dei dispositivi mobili se si intende utilizzare tali dispositivi e distribuire i servizi nel pool Front End o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f5e58-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f5e58-173">Gruppo <strong>Administrators</strong> o amministratore del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f5e58-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="f5e58-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurazione dei server proxy inversi per Lync server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e58-175">Configurare un server Director (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="f5e58-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f5e58-176">(Facoltativo) Installare e configurare uno o più Director nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="f5e58-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f5e58-177">Gruppo <strong>Administrators</strong></span><span class="sxs-lookup"><span data-stu-id="f5e58-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="f5e58-178"><a href="lync-server-2013-setting-up-the-director.md">Configurazione del Director in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e58-179">Configurare i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f5e58-180">Installare i prerequisiti software.</span><span class="sxs-lookup"><span data-stu-id="f5e58-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-181">Trasportare in ogni server perimetrale il file di configurazione della topologia esportato.</span><span class="sxs-lookup"><span data-stu-id="f5e58-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-182">Installare il software Lync Server 2013 in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f5e58-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-183">Configurare i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-184">Richiedere e installare i certificati per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f5e58-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-185">Avviare i servizi dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f5e58-186">Gruppo <strong>Administrators</strong></span><span class="sxs-lookup"><span data-stu-id="f5e58-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="f5e58-187"><a href="lync-server-2013-setting-up-edge-servers.md">Configurazione dei server perimetrali in Lync server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e58-188">Configurare la distribuzione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="f5e58-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f5e58-189">Utilizzare il pannello di controllo di Lync Server per configurare il supporto per ognuna delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="f5e58-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="f5e58-190">Media relay</span><span class="sxs-lookup"><span data-stu-id="f5e58-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="f5e58-191">Route di federazione</span><span class="sxs-lookup"><span data-stu-id="f5e58-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="f5e58-192">Accesso degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="f5e58-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="f5e58-193">Federazione con Lync Server, Office Communications Server e Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="f5e58-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="f5e58-194">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="f5e58-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="f5e58-195">Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="f5e58-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="f5e58-196">Utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="f5e58-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="f5e58-197">Configurare gli account utente per l'accesso degli utenti remoti, la federazione, la connettività per messaggistica istantanea pubblica e il supporto degli utenti anonimi (in base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="f5e58-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f5e58-198">Gruppo <strong>RTCUniversalServerAdmins</strong> o account utente assegnato al ruolo <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="f5e58-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="f5e58-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e58-200">Verificare la configurazione dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f5e58-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f5e58-201">Verificare la connettività dei server e la replica dei dati di configurazione dai server interni.</span><span class="sxs-lookup"><span data-stu-id="f5e58-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-202">Verificare che gli utenti esterni possano connettersi, inclusi gli utenti remoti, gli utenti di domini federati, gli utenti di messaggistica istantanea pubblica e gli utenti anonimi, a seconda dei requisiti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5e58-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="f5e58-203">Verificare la configurazione e la comunicazione tramite l'analizzatore connettività remota di Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="f5e58-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="f5e58-204">Risolvere i problemi di comunicazione e configurazione</span><span class="sxs-lookup"><span data-stu-id="f5e58-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f5e58-205">Per la verifica della replica, il gruppo <strong>RTCUniversalServerAdmins</strong> o l'account utente assegnato al ruolo <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="f5e58-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="f5e58-206">Per la verifica della connettività degli utenti, un utente per ogni tipo di accesso degli utenti esterni supportato</span><span class="sxs-lookup"><span data-stu-id="f5e58-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="f5e58-207">Utenti remoti</span><span class="sxs-lookup"><span data-stu-id="f5e58-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="f5e58-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione di Edge in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f5e58-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

