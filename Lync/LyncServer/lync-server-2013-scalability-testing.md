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
ms.openlocfilehash: d702b0a197e6e81fbc6833ca58968a10d8dd3fff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="79235-102">Test di scalabilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79235-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79235-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="79235-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="79235-104">Lync Server 2013 offre l'infrastruttura server per tutte le comunicazioni in tempo reale di Lync Server, tra cui messaggistica istantanea e presenza, conferenza e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="79235-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="79235-105">Sono incluse tutte le caratteristiche che usano le risorse hardware di un pool di Lync Server 2013 e quindi incidono sulle prestazioni e sulle proporzioni.</span><span class="sxs-lookup"><span data-stu-id="79235-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="79235-106">Tutte le organizzazioni non usano tutte le funzionalità in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="79235-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="79235-107">Ad esempio, alcune organizzazioni potrebbero usare il video in conferenze molto duramente, mentre altri potrebbero avere poco o nessun utilizzo video.</span><span class="sxs-lookup"><span data-stu-id="79235-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="79235-108">Alcune organizzazioni preferiscono la condivisione di diapositive di PowerPoint nella condivisione delle applicazioni, mentre altre preferiscono il contrario.</span><span class="sxs-lookup"><span data-stu-id="79235-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="79235-109">Le organizzazioni che distribuiscono Enterprise Voice potrebbero non usare molto l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="79235-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="79235-110">La maggior parte delle organizzazioni distribuisce server di monitoraggio, ma non molti distribuiscono i server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="79235-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="79235-111">Inoltre, le organizzazioni non hanno tutte le stesse infrastrutture, incluse le capacità hardware, le capacità di rete e il numero di pool e le dimensioni dei pool distribuiti.</span><span class="sxs-lookup"><span data-stu-id="79235-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="79235-112">La diversità delle caratteristiche e delle infrastrutture rappresenta una sfida per i test di scalabilità: non è possibile simulare tutte le possibili combinazioni di funzionalità e infrastrutture.</span><span class="sxs-lookup"><span data-stu-id="79235-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="79235-113">Per determinare il supporto della scalabilità per Lync Server, conduciamo test usando tutte le funzionalità di Lync Server contemporaneamente, in base a un modello di utilizzo medio (modello utente).</span><span class="sxs-lookup"><span data-stu-id="79235-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="79235-114">Per determinare un modello utente appropriato per i carichi di lavoro di Lync Server, analizziamo molti punti dati, inclusi i sondaggi dei clienti, il feedback del programma Microsoft Customer Experience Improvement, i dati di utilizzo di Lync Server dal reparto IT interno di Microsoft, e i dati estratti dal nostro servizio Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="79235-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="79235-115">In molti casi, il modello utente ha una distorsione nei confronti di carichi più pesanti per ottenere un margine comodo per l'utilizzo all'interno di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79235-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="79235-116">Nei test di scalabilità abbiamo configurato i pool di Lync Server 2013 in base alle specifiche hardware e software consigliate, inclusi i componenti dell'infrastruttura, ad esempio i servizi di dominio Active Directory, i dispositivi di bilanciamento del carico hardware e i firewall.</span><span class="sxs-lookup"><span data-stu-id="79235-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="79235-117">Configuriamo gli ambienti di Lync Server il più vicino possibile agli ambienti reali del mondo reale.</span><span class="sxs-lookup"><span data-stu-id="79235-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="79235-118">Viene quindi usato lo strumento di esecuzione dello stress e delle prestazioni di Lync Server 2013 per simulare i carichi di Lync Server 2013 (in base al modello di utente).</span><span class="sxs-lookup"><span data-stu-id="79235-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="79235-119">.</span><span class="sxs-lookup"><span data-stu-id="79235-119">.</span></span>

<span data-ttu-id="79235-120">Eseguiamo più iterazioni di test di scalabilità (tra cui più esecuzioni di test di tre settimane).</span><span class="sxs-lookup"><span data-stu-id="79235-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="79235-121">Usiamo i risultati di tutti i test per facilitare l'ottimizzazione delle prestazioni e per verificare il supporto per i numeri di scalabilità nel modello di utente.</span><span class="sxs-lookup"><span data-stu-id="79235-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

