---
title: 'Lync Server 2013: amministrazione di sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f128196f1d541e8a7f8ffd3b48bac8f34de85b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="b5044-102">Amministrazione di sistema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5044-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5044-103">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="b5044-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="b5044-104">L'amministrazione del sistema include le attività amministrative quotidiane, sia pianificate sia su richiesta, che sono necessarie per mantenere un funzionamento del sistema IT senza problemi.</span><span class="sxs-lookup"><span data-stu-id="b5044-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="b5044-105">Le attività di amministrazione del sistema vengono in genere analizzate tramite procedure scritte.</span><span class="sxs-lookup"><span data-stu-id="b5044-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="b5044-106">Queste procedure consentono di garantire che gli stessi strumenti e metodi standard siano utilizzati da tutto il personale di supporto.</span><span class="sxs-lookup"><span data-stu-id="b5044-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="b5044-107">In un ambiente Lync le attività tipiche di amministrazione del sistema includono il backup e l'archiviazione di pool, il monitoraggio dei log, la creazione e la gestione degli utenti e l'aggiornamento del software antivirus.</span><span class="sxs-lookup"><span data-stu-id="b5044-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="b5044-108">Risoluzione dei problemi del sistema</span><span class="sxs-lookup"><span data-stu-id="b5044-108">System troubleshooting</span></span>

<span data-ttu-id="b5044-109">Un'organizzazione deve essere preparata per gestire i problemi imprevisti e deve disporre di una procedura per la gestione dei problemi dal momento in cui vengono segnalati fino alla risoluzione.</span><span class="sxs-lookup"><span data-stu-id="b5044-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="b5044-110">Informazioni sul modo in cui gli addetti al supporto diagnostici hanno diagnosticato un problema devono essere registrati e usati in futuro per evitare inutili ripetendo il lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="b5044-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="b5044-111">Processo di risoluzione dei problemi del sistema</span><span class="sxs-lookup"><span data-stu-id="b5044-111">System troubleshooting process</span></span>

<span data-ttu-id="b5044-112">Nel diagramma seguente viene illustrato il processo di risoluzione dei problemi del sistema e le interazioni con altri ruoli operativi.</span><span class="sxs-lookup"><span data-stu-id="b5044-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="b5044-113">**Diagramma di flusso di risoluzione dei problemi del sistema**</span><span class="sxs-lookup"><span data-stu-id="b5044-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="b5044-114">![Diagramma di flusso di risoluzione dei problemi del sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagramma di flusso di risoluzione dei problemi del sistema")</span><span class="sxs-lookup"><span data-stu-id="b5044-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="b5044-115">**Classificazione e assegnazione di priorità**   questa attività viene in genere eseguita dal Service Desk.</span><span class="sxs-lookup"><span data-stu-id="b5044-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="b5044-116">Ad esempio, un problema può essere raggruppato come problema software o hardware.</span><span class="sxs-lookup"><span data-stu-id="b5044-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="b5044-117">Il problema viene quindi instradato al team di supporto appropriato per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="b5044-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="b5044-118">Le regole per determinare la priorità di un problema, insieme al tempo di risposta e al tempo di risoluzione, vengono in genere definite nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b5044-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="b5044-119">**Esaminare e diagnosticare**   il team di supporto appropriato per la diagnosi del problema e propone le modifiche per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="b5044-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="b5044-120">Se la soluzione è semplice e non richiede il controllo delle modifiche, la soluzione può essere applicata immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b5044-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="b5044-121">Se la soluzione non è semplice, è necessario che venga generata una richiesta di modifica e che il lavoro proposto venga gestito dal processo di gestione delle modifiche, spesso in base a una procedura "Fast-Track".</span><span class="sxs-lookup"><span data-stu-id="b5044-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="b5044-122">Tutte le modifiche apportate devono essere registrate utilizzando il processo di gestione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="b5044-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="b5044-123">**Chiudi e registra**   dopo aver testato la risoluzione, il problema dovrebbe essere chiuso.</span><span class="sxs-lookup"><span data-stu-id="b5044-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="b5044-124">Se è possibile trarre lezioni dal problema, è necessario creare una voce nella Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="b5044-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="b5044-125">**Revisione e analisi**   delle tendenze le recensioni periodiche dei problemi recenti devono essere eseguite per identificare i trend del problema.</span><span class="sxs-lookup"><span data-stu-id="b5044-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="b5044-126">Ad esempio, se gli utenti riscontrano problemi frequenti con gli accessi lenti ai propri siti Lync, potrebbe essere la causa di problemi relativi alla larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="b5044-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="b5044-127">I tempi di risoluzione dei problemi e l'effetto di eventuali interruzioni sulla disponibilità del sistema devono essere esaminati e confrontati con il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b5044-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="b5044-128">La persona che mantiene con il cliente in merito ai problemi del servizio, ad esempio un responsabile account, deve essere informata su eventuali problemi significativi.</span><span class="sxs-lookup"><span data-stu-id="b5044-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="b5044-129">Strumenti di gestione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b5044-129">Issue management tools</span></span>

<span data-ttu-id="b5044-130">Gli strumenti di Service Desk consentono al personale di registrare, classificare e assegnare una priorità ai nuovi problemi.</span><span class="sxs-lookup"><span data-stu-id="b5044-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="b5044-131">Gli strumenti forniranno quindi i processi del flusso di lavoro per gestire la richiesta di servizio di problema tramite indagini e diagnosi, spesso da più di un team di supporto.</span><span class="sxs-lookup"><span data-stu-id="b5044-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="b5044-132">Gli strumenti, che forniscono spesso report sui tempi di risoluzione e le tendenze storiche, possono includere anche un database della Knowledge base, che può essere utilizzato per eseguire ricerche nei problemi precedenti.</span><span class="sxs-lookup"><span data-stu-id="b5044-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="b5044-133">La Microsoft Knowledge base è un utile record di problemi di supporto che sono stati rilevati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5044-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="b5044-134">Per ulteriori informazioni, vedere il sito Web del supporto<https://go.microsoft.com/fwlink/?linkid=14898>tecnico Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="b5044-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="b5044-135">Il software di terze parti in genere richiede la personalizzazione in base alle esigenze dell'organizzazione, ad esempio l'organizzazione di Team, i requisiti per la creazione di report e le misure richieste dal contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b5044-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="b5044-136">Amministrazione centralizzata e decentralizzata</span><span class="sxs-lookup"><span data-stu-id="b5044-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="b5044-137">I ruoli e le responsabilità per l'esecuzione delle attività di amministrazione del sistema dipendono dal fatto che l'organizzazione segua un modello centralizzato, un modello decentralizzato o una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="b5044-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="b5044-138">**Modello centralizzato**   in un modello centralizzato, uno o più gruppi amministrativi mantengono il controllo completo dell'intero ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5044-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="b5044-139">Questo modello amministrativo è simile a un centro dati in cui tutte le attività di amministrazione vengono eseguite da un singolo gruppo di tecnologie informative.</span><span class="sxs-lookup"><span data-stu-id="b5044-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="b5044-140">I ruoli e le responsabilità interni al team devono essere definiti in base a esperienze e competenze.</span><span class="sxs-lookup"><span data-stu-id="b5044-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="b5044-141">\*\*\*\*   Le organizzazioni decentralizzate del modello decentralizzato sono situate in diverse posizioni geografiche e dispongono di server e team di amministratori di Lync Server in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="b5044-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="b5044-142">Ad esempio, è possibile che vi sia personale di amministrazione locale e uno o più server che eseguono Lync Server 2013 per ogni paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="b5044-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="b5044-143">In alternativa, può essere presente un pool di server che eseguono Lync Server 2013 e un team amministrativo per il Nord America e uno per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="b5044-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="b5044-144">A volte, potrebbe essere necessario che gli amministratori siano responsabili solo per la propria area geografica e limitare le autorizzazioni per amministrare le risorse in altre aree.</span><span class="sxs-lookup"><span data-stu-id="b5044-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="b5044-145">Lync Server consente inoltre di delegare specifiche attività amministrative a specifiche persone o gruppi tramite il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b5044-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="b5044-146">RBAC consente agli amministratori di delegare diritti utente e autorizzazioni specifici ad altri amministratori per eseguire un sottoinsieme delle attività amministrative possibili.</span><span class="sxs-lookup"><span data-stu-id="b5044-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="b5044-147">Tramite RBAC, la capacità dell'utente di eseguire attività amministrative specifiche dipende dai ruoli RBAC assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="b5044-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="b5044-148">RBAC fornisce un elenco di cmdlet che l'utente può eseguire in base ai ruoli RBAC di cui l'utente è membro.</span><span class="sxs-lookup"><span data-stu-id="b5044-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

