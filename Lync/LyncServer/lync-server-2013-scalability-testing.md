---
title: Test di scalabilità di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e23cd1bf0382a392cba951d90cd9dfa80c4880
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511013"
---
# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="b6291-102">Test della scalabilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6291-102">Scalability testing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6291-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b6291-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b6291-104">Lync Server 2013 fornisce l'infrastruttura server per tutte le comunicazioni in tempo reale di Lync Server, tra cui la messaggistica istantanea e la presenza, le conferenze e la VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b6291-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="b6291-105">Sono incluse tutte le funzionalità che utilizzano le risorse hardware di un pool di Lync Server 2013 e, pertanto, influiscono sulle prestazioni e sulla scalabilità.</span><span class="sxs-lookup"><span data-stu-id="b6291-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="b6291-106">Non tutte le organizzazioni si avvalgono di tutte le funzionalità nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="b6291-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="b6291-107">Alcune organizzazioni ad esempio possono utilizzare molto frequentemente i video nelle conferenze, mentre altre possono utilizzarli raramente o addirittura non utilizzarli affatto.</span><span class="sxs-lookup"><span data-stu-id="b6291-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="b6291-108">Alcune organizzazioni preferiscono la condivisione delle diapositive di PowerPoint alla condivisione delle applicazioni, mentre altre preferiscono il contrario.</span><span class="sxs-lookup"><span data-stu-id="b6291-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="b6291-109">Le organizzazioni che distribuiscono VoIP aziendale potrebbero o meno utilizzare l'applicazione Response Group in modo pesante.</span><span class="sxs-lookup"><span data-stu-id="b6291-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="b6291-110">La maggior parte delle organizzazioni distribuisce i server di monitoraggio, ma non molti di essi distribuiscono i server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b6291-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="b6291-111">Le organizzazioni inoltre non dispongono tutte delle stesse infrastrutture, anche in termini di capacità hardware, capacità di rete e numero e dimensione dei pool distribuiti.</span><span class="sxs-lookup"><span data-stu-id="b6291-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="b6291-112">La diversità di funzionalità e infrastrutture pone una sfida ai fini del testing della scalabilità, in quanto non si riescono a simulare tutte le combinazioni di funzionalità e infrastrutture possibili.</span><span class="sxs-lookup"><span data-stu-id="b6291-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="b6291-113">Per determinare il supporto della scalabilità per Lync Server, è possibile eseguire test utilizzando contemporaneamente tutte le funzionalità di Lync Server, in base a un modello di utilizzo medio (modello utente).</span><span class="sxs-lookup"><span data-stu-id="b6291-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="b6291-114">Per determinare un modello utente appropriato per i carichi di lavoro di Lync Server, vengono analizzati molti punti dati, inclusi i sondaggi dei clienti, i commenti e suggerimenti del programma Analisi utilizzo software Microsoft, i dati di uso di Lync Server provenienti dal reparto IT interno di Microsoft e i dati estratti dal servizio Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="b6291-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="b6291-115">In molti casi il modello utente tende a preferire i carichi più pesanti in modo da lasciare un margine adeguato per l'utilizzo all'interno di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6291-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="b6291-116">Nei test di scalabilità sono stati configurati i pool di Lync Server 2013 in base alle specifiche hardware e software consigliate, tra cui i componenti dell'infrastruttura, ad esempio servizi di dominio Active Directory, dispositivi di bilanciamento del carico hardware e firewall.</span><span class="sxs-lookup"><span data-stu-id="b6291-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="b6291-117">Gli ambienti di Lync Server sono configurati il più vicino possibile agli ambienti tipici del mondo reale.</span><span class="sxs-lookup"><span data-stu-id="b6291-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="b6291-118">È quindi possibile utilizzare lo strumento Lync Server 2013 stress and performance per simulare i carichi di Lync Server 2013 (in base al modello utente).</span><span class="sxs-lookup"><span data-stu-id="b6291-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="b6291-119">.</span><span class="sxs-lookup"><span data-stu-id="b6291-119">.</span></span>

<span data-ttu-id="b6291-p105">Vengono eseguite più iterazioni dei test di scalabilità, incluse più esecuzioni di prova della durata di tre settimane. I risultati di tutti i test vengono utilizzati per l'ottimizzazione delle prestazioni e la verifica del supporto per i numeri di scalabilità previsti nel modello utente.</span><span class="sxs-lookup"><span data-stu-id="b6291-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

