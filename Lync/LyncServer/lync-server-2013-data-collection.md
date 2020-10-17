---
title: 'Lync Server 2013: raccolta dati'
description: 'Lync Server 2013: raccolta dati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1808a68081ee453a56eabdaf264eb53ab5a1ef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553782"
---
# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="975f7-103">Raccolta dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975f7-103">Data collection in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="975f7-104">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="975f7-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="975f7-105">In Microsoft Lync Server 2013 Communications Software, è possibile eseguire Microsoft Lync Server 2013, strumento di pianificazione senza documentare gli indirizzi IP e i nomi di dominio completi (FQDN) esistenti e proposi, ma è molto più difficile farlo senza causare errori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="975f7-105">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="975f7-106">Ad esempio, se la coesistenza è necessaria per un determinato periodo di tempo, un errore comune consiste nel riutilizzare gli FQDN da una distribuzione perimetrale esistente per la distribuzione di Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="975f7-106">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="975f7-107">Prendendo nota degli indirizzi IP esistenti e proposti e degli FQDN in un foglio di calcolo, in una tabella oppure in un altro tipo di modulo grafico, si evitano problemi di configurazione durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="975f7-107">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="975f7-108">Se sono state utilizzate versioni precedenti dello strumento di pianificazione, è possibile che sia stato utilizzato lo strumento per creare la topologia e il documento della topologia esportato per l'utilizzo in Generatore di topologie per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="975f7-108">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="975f7-109">La possibilità di esportare la topologia è stata rimossa dallo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="975f7-109">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="975f7-110">L'utilizzo di una versione precedente dello strumento di pianificazione per creare un documento di topologia per Lync Server 2013 è fortemente sconsigliato e produrrà risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="975f7-110">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="975f7-111">Pertanto, l'approccio consigliato consiste nell'utilizzare il modello di raccolta dati seguente, che corrisponde alla topologia perimetrale, per raccogliere i vari FQDN e gli indirizzi IP che dovranno essere immessi nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="975f7-111">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="975f7-112">Documentando la configurazione corrente e quella proposta, è possibile inserire i valori nel contesto corretto per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="975f7-112">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="975f7-113">Si è inoltre costretti a valutare come configurare la coesistenza e funzionalità come URL semplici, condivisioni file e bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="975f7-113">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="975f7-114">Per distribuire correttamente Microsoft Lync Server 2013, è necessario comprendere l'interazione e l'affidamento sui singoli componenti.</span><span class="sxs-lookup"><span data-stu-id="975f7-114">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="975f7-115">Raccogliendo i dati dall'infrastruttura di rete e del server esistente e applicando le indicazioni relative alla pianificazione in queste sezioni, è possibile integrare i componenti del server perimetrale di Lync Server 2013 nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="975f7-115">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="975f7-116">Introdotta nella [scelta di una topologia in Lync Server 2013](lync-server-2013-choosing-a-topology.md), esistono tre architetture principali con due varianti, per un totale di cinque possibili scenari di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="975f7-116">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="975f7-117">Uno di questi scenari rappresenterà il punto di partenza per la raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="975f7-117">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="975f7-118">Gli indirizzi IP, i nomi dei server e i nomi di dominio sono esempi che coincidono con il certificato, il firewall e i diagrammi DNS corrispondenti che descrivono in dettaglio le informazioni richieste per una soluzione di pianificazione completa.</span><span class="sxs-lookup"><span data-stu-id="975f7-118">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="975f7-119">I diagrammi e la compilazione dei valori richiesti per certificato, DNS e firewall sono particolarmente importanti per le comunicazioni tra team, nei casi in cui la gestione dell'Autorità di certificazione, della configurazione del firewall e del sistema DNS è responsabilità di team diversi dal team che si occupa della pianificazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="975f7-119">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="975f7-120">I diagrammi offrono informazioni sui componenti necessari che è possibile utilizzare per la comunicazione dei requisiti nell'ottica della collaborazione tra team.</span><span class="sxs-lookup"><span data-stu-id="975f7-120">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="975f7-121">I diagrammi forniti sono intenzionalmente generali, ma consentono la raccolta di dati pertinenti che sarebbero necessari per la comunicazione dei requisiti in uno scenario di collaborazione tra team, nel quale la rete, i firewall, la creazione e la gestione dei certificati, la distribuzione dei server e la gestione dei server sono affidati a gruppi diversi.</span><span class="sxs-lookup"><span data-stu-id="975f7-121">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="975f7-122">La disponibilità dei dettagli necessari per la configurazione di rete, firewall, porte e protocolli, certificati e server risulta inestimabile quando è in corso la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="975f7-122">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="975f7-123">**Server perimetrale e pool perimetrale**</span><span class="sxs-lookup"><span data-stu-id="975f7-123">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="975f7-124">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="975f7-124">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="975f7-125">**Proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="975f7-125">**Reverse Proxy**</span></span>

<span data-ttu-id="975f7-126">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="975f7-126">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="975f7-127">**Director o pool di server Director**</span><span class="sxs-lookup"><span data-stu-id="975f7-127">**Director or Director pool**</span></span>

<span data-ttu-id="975f7-128">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="975f7-128">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

