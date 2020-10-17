---
title: 'Lync Server 2013: amministrazione di sistema'
description: 'Lync Server 2013: amministrazione di sistema.'
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
ms.openlocfilehash: b56271d8d90f1d83072af0577692be1ea0b5bc7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562682"
---
# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="8066e-103">Amministrazione di sistema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8066e-103">System administration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8066e-104">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8066e-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8066e-105">L'amministrazione del sistema include le attività amministrative quotidiane, sia pianificate sia su richiesta, che sono necessarie per mantenere un funzionamento del sistema IT senza problemi.</span><span class="sxs-lookup"><span data-stu-id="8066e-105">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="8066e-106">Le attività di amministrazione del sistema vengono in genere analizzate tramite procedure scritte.</span><span class="sxs-lookup"><span data-stu-id="8066e-106">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="8066e-107">Queste procedure consentono di garantire che gli stessi strumenti e metodi standard siano utilizzati da tutto il personale di supporto.</span><span class="sxs-lookup"><span data-stu-id="8066e-107">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="8066e-108">In un ambiente Lync le attività tipiche di amministrazione del sistema includono il backup e l'archiviazione di pool, il monitoraggio dei log, la creazione e la gestione degli utenti e l'aggiornamento del software antivirus.</span><span class="sxs-lookup"><span data-stu-id="8066e-108">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="8066e-109">Risoluzione dei problemi del sistema</span><span class="sxs-lookup"><span data-stu-id="8066e-109">System troubleshooting</span></span>

<span data-ttu-id="8066e-110">Un'organizzazione deve essere preparata per gestire i problemi imprevisti e deve disporre di una procedura per la gestione dei problemi dal momento in cui vengono segnalati fino alla risoluzione.</span><span class="sxs-lookup"><span data-stu-id="8066e-110">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="8066e-111">Informazioni sul modo in cui gli addetti al supporto diagnostici hanno diagnosticato un problema devono essere registrati e usati in futuro per evitare inutili ripetendo il lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="8066e-111">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="8066e-112">Processo di risoluzione dei problemi del sistema</span><span class="sxs-lookup"><span data-stu-id="8066e-112">System troubleshooting process</span></span>

<span data-ttu-id="8066e-113">Nel diagramma seguente viene illustrato il processo di risoluzione dei problemi del sistema e le interazioni con altri ruoli operativi.</span><span class="sxs-lookup"><span data-stu-id="8066e-113">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="8066e-114">**Diagramma di flusso di risoluzione dei problemi del sistema**</span><span class="sxs-lookup"><span data-stu-id="8066e-114">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="8066e-115">![Diagramma di flusso di risoluzione dei problemi del sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagramma di flusso di risoluzione dei problemi del sistema")</span><span class="sxs-lookup"><span data-stu-id="8066e-115">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="8066e-116">**Classificazione e assegnazione di priorità**     Questa attività viene in genere eseguita dal Service Desk.</span><span class="sxs-lookup"><span data-stu-id="8066e-116">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="8066e-117">Ad esempio, un problema può essere raggruppato come problema software o hardware.</span><span class="sxs-lookup"><span data-stu-id="8066e-117">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="8066e-118">Il problema viene quindi instradato al team di supporto appropriato per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="8066e-118">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="8066e-119">Le regole per determinare la priorità di un problema, insieme al tempo di risposta e al tempo di risoluzione, vengono in genere definite nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8066e-119">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="8066e-120">**Esaminare e diagnosticare**     Il team di supporto appropriato diagnostica il problema e propone le modifiche per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="8066e-120">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="8066e-121">Se la soluzione è semplice e non richiede il controllo delle modifiche, la soluzione può essere applicata immediatamente.</span><span class="sxs-lookup"><span data-stu-id="8066e-121">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="8066e-122">Se la soluzione non è semplice, è necessario che venga generata una richiesta di modifica e che il lavoro proposto venga gestito dal processo di gestione delle modifiche, spesso in base a una procedura "Fast-Track".</span><span class="sxs-lookup"><span data-stu-id="8066e-122">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="8066e-123">Tutte le modifiche apportate devono essere registrate utilizzando il processo di gestione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="8066e-123">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="8066e-124">**Chiudi e registra**     Dopo aver testato la risoluzione, il problema dovrebbe essere chiuso.</span><span class="sxs-lookup"><span data-stu-id="8066e-124">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="8066e-125">Se è possibile trarre lezioni dal problema, è necessario creare una voce nella Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="8066e-125">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="8066e-126">**Revisione e analisi**     delle tendenze Le recensioni periodiche dei problemi recenti devono essere eseguite per identificare le tendenze del problema.</span><span class="sxs-lookup"><span data-stu-id="8066e-126">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="8066e-127">Ad esempio, se gli utenti riscontrano problemi frequenti con gli accessi lenti ai propri siti Lync, potrebbe essere la causa di problemi relativi alla larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="8066e-127">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="8066e-128">I tempi di risoluzione dei problemi e l'effetto di eventuali interruzioni sulla disponibilità del sistema devono essere esaminati e confrontati con il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8066e-128">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="8066e-129">La persona che mantiene con il cliente in merito ai problemi del servizio, ad esempio un responsabile account, deve essere informata su eventuali problemi significativi.</span><span class="sxs-lookup"><span data-stu-id="8066e-129">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="8066e-130">Strumenti di gestione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8066e-130">Issue management tools</span></span>

<span data-ttu-id="8066e-131">Gli strumenti di Service Desk consentono al personale di registrare, classificare e assegnare una priorità ai nuovi problemi.</span><span class="sxs-lookup"><span data-stu-id="8066e-131">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="8066e-132">Gli strumenti forniranno quindi i processi del flusso di lavoro per gestire la richiesta di servizio di problema tramite indagini e diagnosi, spesso da più di un team di supporto.</span><span class="sxs-lookup"><span data-stu-id="8066e-132">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="8066e-133">Gli strumenti, che forniscono spesso report sui tempi di risoluzione e le tendenze storiche, possono includere anche un database della Knowledge base, che può essere utilizzato per eseguire ricerche nei problemi precedenti.</span><span class="sxs-lookup"><span data-stu-id="8066e-133">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="8066e-134">La Microsoft Knowledge base è un utile record di problemi di supporto che sono stati rilevati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8066e-134">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="8066e-135">Per ulteriori informazioni, vedere il sito Web del supporto tecnico Microsoft ( <https://go.microsoft.com/fwlink/?linkid=14898> ).</span><span class="sxs-lookup"><span data-stu-id="8066e-135">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="8066e-136">Il software di terze parti in genere richiede la personalizzazione in base alle esigenze dell'organizzazione, ad esempio l'organizzazione di Team, i requisiti per la creazione di report e le misure richieste dal contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8066e-136">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="8066e-137">Amministrazione centralizzata e decentralizzata</span><span class="sxs-lookup"><span data-stu-id="8066e-137">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="8066e-138">I ruoli e le responsabilità per l'esecuzione delle attività di amministrazione del sistema dipendono dal fatto che l'organizzazione segua un modello centralizzato, un modello decentralizzato o una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="8066e-138">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="8066e-139">**Modello**     centralizzato In un modello centralizzato, uno o più gruppi amministrativi mantengono il controllo completo dell'intero ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8066e-139">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="8066e-140">Questo modello amministrativo è simile a un centro dati in cui tutte le attività di amministrazione vengono eseguite da un singolo gruppo di tecnologie informative.</span><span class="sxs-lookup"><span data-stu-id="8066e-140">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="8066e-141">I ruoli e le responsabilità interni al team devono essere definiti in base a esperienze e competenze.</span><span class="sxs-lookup"><span data-stu-id="8066e-141">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="8066e-142">Modello decentralizzato **Decentralized Model**     Le organizzazioni decentralizzate sono situate in diverse posizioni geografiche e dispongono di server e team di amministratori di Lync Server in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="8066e-142">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="8066e-143">Ad esempio, è possibile che vi sia personale di amministrazione locale e uno o più server che eseguono Lync Server 2013 per ogni paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="8066e-143">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="8066e-144">In alternativa, può essere presente un pool di server che eseguono Lync Server 2013 e un team amministrativo per il Nord America e uno per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="8066e-144">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="8066e-145">A volte, potrebbe essere necessario che gli amministratori siano responsabili solo per la propria area geografica e limitare le autorizzazioni per amministrare le risorse in altre aree.</span><span class="sxs-lookup"><span data-stu-id="8066e-145">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="8066e-146">Lync Server consente inoltre di delegare specifiche attività amministrative a specifiche persone o gruppi tramite il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8066e-146">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="8066e-147">RBAC consente agli amministratori di delegare diritti utente e autorizzazioni specifici ad altri amministratori per eseguire un sottoinsieme delle attività amministrative possibili.</span><span class="sxs-lookup"><span data-stu-id="8066e-147">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="8066e-148">Tramite RBAC, la capacità dell'utente di eseguire attività amministrative specifiche dipende dai ruoli RBAC assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="8066e-148">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="8066e-149">RBAC fornisce un elenco di cmdlet che l'utente può eseguire in base ai ruoli RBAC di cui l'utente è membro.</span><span class="sxs-lookup"><span data-stu-id="8066e-149">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

