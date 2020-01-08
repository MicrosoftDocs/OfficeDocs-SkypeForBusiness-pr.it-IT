---
title: 'Lync Server 2013: Raccolta dati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="46a54-102">Raccolta dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46a54-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46a54-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="46a54-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="46a54-104">Nel software di comunicazione di Microsoft Lync Server 2013 è possibile eseguire Microsoft Lync Server 2013, strumento di pianificazione senza documentare gli indirizzi IP esistenti e quelli previsti e i nomi di dominio completi (FQDN) del server perimetrale, ma è molto più difficile da eseguire senza causare errori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="46a54-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="46a54-105">Ad esempio, se è necessaria una coesistenza per un periodo di tempo, un errore comune consiste nel riutilizzare gli FQDN da una distribuzione di Edge esistente per la distribuzione di Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46a54-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="46a54-106">Se gli indirizzi IP e i nomi di dominio completi esistenti e proposti sono stati scritti in un foglio di calcolo, una tabella o un'altra maschera visiva, è possibile evitare problemi di configurazione durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="46a54-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="46a54-107">Se sono state usate versioni precedenti dello strumento di pianificazione, è possibile che sia stato usato lo strumento per creare la topologia e il documento della topologia esportato per l'uso in Generatore di topologia per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="46a54-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="46a54-108">La possibilità di esportare la topologia è stata rimossa dallo strumento pianificazione.</span><span class="sxs-lookup"><span data-stu-id="46a54-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="46a54-109">L'uso di una versione precedente dello strumento di pianificazione per creare un documento di topologia per Lync Server 2013 è fortemente sconsigliato e produrrà risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="46a54-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="46a54-110">Di conseguenza, l'approccio consigliato consiste nell'usare il modello di raccolta dati seguente, che corrisponde alla topologia di Edge, per raccogliere i vari indirizzi IP e FQDN che è necessario immettere nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="46a54-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="46a54-111">Documentando la configurazione corrente e proposta, è possibile inserire i valori nel contesto appropriato per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="46a54-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="46a54-112">È quindi necessario pensare a come configurare la coesistenza e le funzionalità, ad esempio URL semplici, condivisioni di file e bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="46a54-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="46a54-113">Per distribuire correttamente Microsoft Lync Server 2013, è necessario comprendere l'interazione e l'affidabilità dei singoli componenti.</span><span class="sxs-lookup"><span data-stu-id="46a54-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="46a54-114">Raccogliendo i dati dall'infrastruttura di rete e del server esistente e applicando le indicazioni per la pianificazione in queste sezioni, è possibile integrare i componenti del server Edge di Lync Server 2013 nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="46a54-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="46a54-115">Introdotta nella [scelta di una topologia in Lync Server 2013](lync-server-2013-choosing-a-topology.md), esistono tre architetture principali con due varianti, per un totale di cinque possibili scenari di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="46a54-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="46a54-116">Uno di questi scenari sarà il punto di partenza per la raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="46a54-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="46a54-117">Gli indirizzi IP, i nomi dei server e i nomi di dominio sono esempi che coincidono con i diagrammi di certificato, firewall e DNS corrispondenti che illustrano in dettaglio le informazioni necessarie per una soluzione di pianificazione completa.</span><span class="sxs-lookup"><span data-stu-id="46a54-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="46a54-118">I diagrammi e il riempimento del certificato richiesto, i valori DNS e firewall sono particolarmente importanti nelle comunicazioni cross-team in cui la gestione dell'autorità di certificazione, la configurazione del firewall e il DNS vengono gestiti da team diversi dal team che pianificare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="46a54-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="46a54-119">I diagrammi contengono informazioni sui componenti necessari che possono essere usati per comunicare questi requisiti per la collaborazione tra team.</span><span class="sxs-lookup"><span data-stu-id="46a54-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="46a54-120">I diagrammi forniti sono intenzionalmente generici, ma consentono la raccolta di tutti i dati pertinenti che sarebbero necessari per la comunicazione dei requisiti in uno scenario cross team in cui networking, firewall, creazione e gestione di certificati, server la distribuzione e la gestione del server vengono gestite da gruppi diversi.</span><span class="sxs-lookup"><span data-stu-id="46a54-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="46a54-121">I dettagli necessari per la configurazione di reti, firewall, porte e protocolli, certificati e server sono inestimabili quando è in corso la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46a54-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="46a54-122">**Edge Server e pool Edge**</span><span class="sxs-lookup"><span data-stu-id="46a54-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="46a54-123">![7624717a-CE99-4AE8-A929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-CE99-4AE8-A929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="46a54-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="46a54-124">**Proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="46a54-124">**Reverse Proxy**</span></span>

<span data-ttu-id="46a54-125">![cf63fc50-2D11-4334-AFC8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2D11-4334-AFC8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="46a54-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="46a54-126">**Pool di Director o Director**</span><span class="sxs-lookup"><span data-stu-id="46a54-126">**Director or Director pool**</span></span>

<span data-ttu-id="46a54-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="46a54-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

