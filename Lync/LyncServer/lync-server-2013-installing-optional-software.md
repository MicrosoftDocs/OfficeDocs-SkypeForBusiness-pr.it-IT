---
title: 'Lync Server 2013: installazione di software facoltativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080f27b1e01f86d23fd5fd7bf6fdb9e9a05c0742
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="d0454-102">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0454-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0454-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d0454-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d0454-104">Microsoft Lync Server 2013, strumento di pianificazione è progettato per l'esportazione in Microsoft Excel e Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="d0454-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="d0454-105">Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d0454-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="d0454-106">Software facoltativo</span><span class="sxs-lookup"><span data-stu-id="d0454-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="d0454-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="d0454-107">Microsoft Excel</span></span>

<span data-ttu-id="d0454-108">L'esportazione del progetto in Microsoft Excel consente di creare un report in cui vengono visualizzate sette schede nel foglio di calcolo:</span><span class="sxs-lookup"><span data-stu-id="d0454-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="d0454-109">Riepilogo: consente di visualizzare informazioni sulla configurazione del sito, inclusi il numero di utenti, le impostazioni di capacità e le informazioni sui profili del server.</span><span class="sxs-lookup"><span data-stu-id="d0454-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="d0454-110">Profilo hardware – Visualizza un rapporto delle configurazioni hardware consigliate per i server specificati nella topologia, inclusi disco, CPU, memoria, e interfaccia di rete.</span><span class="sxs-lookup"><span data-stu-id="d0454-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="d0454-111">Sono incluse anche la quantità e le specifiche consigliate per i componenti del server.</span><span class="sxs-lookup"><span data-stu-id="d0454-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="d0454-112">Ogni server è inoltre definito dal sito per fornire una rappresentazione completa dei requisiti del server in base al sito.</span><span class="sxs-lookup"><span data-stu-id="d0454-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="d0454-113">Requisiti per le porte: consente di visualizzare un report di tutte le porte abilitate e l'associazione al bilanciamento del carico del sistema DNS (Domain Name System) e ai sistemi di bilanciamento del carico hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="d0454-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="d0454-114">È consigliabile utilizzare questo report per pianificare le configurazioni di firewall e di LB e di HLB di DNS.</span><span class="sxs-lookup"><span data-stu-id="d0454-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="d0454-115">Report riepilogativo – Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d0454-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="d0454-116">Report certificati – Visualizza il nome del soggetto e i nomi alternativi del soggetto necessari per i certificati necessari per ottenere i server perimetrali in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0454-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="d0454-117">Report firewall – Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce sia esterne che interne.</span><span class="sxs-lookup"><span data-stu-id="d0454-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="d0454-118">Report DNS: consente di visualizzare gli indirizzi FQDN (Fully Qualified Domain Name) e IP/VIP necessari per ogni voce DNS creata.</span><span class="sxs-lookup"><span data-stu-id="d0454-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="d0454-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="d0454-119">Microsoft Visio</span></span>

<span data-ttu-id="d0454-p104">L'esportazione del progetto in Microsoft Visio consente di creare un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e riorganizzato in base alle specifiche esigenze per la documentazione. Il diagramma di Visio tipico includerà:</span><span class="sxs-lookup"><span data-stu-id="d0454-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0454-123">Se il progetto è sufficientemente grande da richiedere più di tre Front End Server, verrà creata una pagina aggiuntiva per il pool Front End, i Front End Server, il computer che esegue SQL Server, gli indirizzi IP e i nomi FQDN.</span><span class="sxs-lookup"><span data-stu-id="d0454-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="d0454-124">Topologia globale – diagramma dei siti di Lync Server 2013 configurati.</span><span class="sxs-lookup"><span data-stu-id="d0454-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="d0454-125">Scheda nome sito – Visualizza la topologia di configurazione del sito con server perimetrale, firewall, rete PSTN (Public Switched Telephone Network) con gateway e la distribuzione interna del server.</span><span class="sxs-lookup"><span data-stu-id="d0454-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="d0454-126">La distribuzione interna è costituita da server e pool configurati, inclusi i pool Front End, i server basati su SQL Server, i servizi di dominio Active Directory, i direttori, i server di messaggistica unificata di Exchange, i server cassette postali di Exchange, i server Office Web Apps Mediation Server e server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d0454-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="d0454-127">Diagramma di rete perimetrale – diagramma che illustra la configurazione del server perimetrale con gli indirizzi IP e gli FQDN associati.</span><span class="sxs-lookup"><span data-stu-id="d0454-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="d0454-128">Sono inoltre inclusi il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d0454-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="d0454-129">Vengono inoltre visualizzati i direttori e il front end server o il pool Front End, con DNS LB o HLB associato e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="d0454-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0454-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0454-130">See Also</span></span>


[<span data-ttu-id="d0454-131">Installazione dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0454-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

