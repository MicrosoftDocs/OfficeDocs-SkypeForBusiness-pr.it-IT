---
title: "Lync Server 2013: configurazione di piattaforme di sistema per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="fc29f-102">Configurazione di piattaforme di sistema per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc29f-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc29f-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="fc29f-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="fc29f-104">Prima di avviare la distribuzione dell'archiviazione, è necessario installare il sistema operativo necessario e qualsiasi altro software prerequisito su hardware che soddisfi i requisiti di sistema:</span><span class="sxs-lookup"><span data-stu-id="fc29f-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="fc29f-105">\*\*\*\*   Le distribuzioni di Lync Server 2013 Platform Lync Server 2013 non dispongono di server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fc29f-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="fc29f-106">Gli agenti di raccolta dati unificati vengono invece eseguiti nei server front-end e nei server Standard Edition per acquisire dati per l'archiviazione, quindi non è necessaria una piattaforma di sistema separata per ospitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fc29f-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="fc29f-107">**Piattaforma di archiviazione dati**   in Lync Server 2013 è possibile archiviare i dati utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc29f-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="fc29f-108">**Integrazione di Microsoft Exchange**   se si vuole archiviare i dati di archiviazione di Lync Server 2013 tramite la distribuzione di Exchange 2013, anziché o in aggiunta alla configurazione di un database separato per l'archiviazione dei dati di archiviazione, è necessario che la distribuzione di Exchange esegua Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="fc29f-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="fc29f-109">Per informazioni dettagliate sulla configurazione di piattaforme di sistema per Exchange 2013, vedere la documentazione del prodotto Exchange.</span><span class="sxs-lookup"><span data-stu-id="fc29f-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="fc29f-110">**SQL Server**   se si vuole usare un database SQL Server separato per l'archiviazione dei dati di archiviazione, anziché o oltre a usare l'integrazione di Microsoft Exchange, è necessario configurare la piattaforma di sistema per il database prima della distribuzione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fc29f-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="fc29f-111">I requisiti specifici della piattaforma di sistema variano a seconda che si usi Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 per il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fc29f-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="fc29f-112">Per informazioni dettagliate sulla configurazione di piattaforme di sistema per questi database, vedere la documentazione del prodotto Microsoft SQL Server 2008 R2 e Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fc29f-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="fc29f-113">**Piattaforma file server**   Lync Server 2013 archivia i file di archiviazione di Lync Server nella stessa posizione specificata per l'archiviazione dei file quando si configurano i server front-end o i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fc29f-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="fc29f-114">Non è possibile specificare una posizione separata per l'archiviazione dei file, quindi non è necessaria una piattaforma di sistema separata per archiviare l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="fc29f-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="fc29f-115">Se si usa l'integrazione di Microsoft Exchange, Exchange 2013 i file per le comunicazioni di Lync archiviati sono archiviati nei server di Exchange 2013 per gli utenti residenti in questi server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fc29f-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

