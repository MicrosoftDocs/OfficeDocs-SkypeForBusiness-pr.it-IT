---
title: 'Lync Server 2013: Panoramica del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="1aa62-102">Panoramica del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa62-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aa62-103">_**Argomento Ultima modifica:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="1aa62-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="1aa62-104">In Microsoft Lync Server 2013 viene usato il monitoraggio per raccogliere le informazioni sull'utilizzo e i dati di qualità dell'esperienza (QoE) sulle sessioni di comunicazione coinvolte dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="1aa62-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="1aa62-105">Una sessione è un termine generico che copre la connessione di un utente a:</span><span class="sxs-lookup"><span data-stu-id="1aa62-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="1aa62-106">Conferenza</span><span class="sxs-lookup"><span data-stu-id="1aa62-106">Conference</span></span>

  - <span data-ttu-id="1aa62-107">Modalità di conferenza (ad esempio condivisione audio/video o applicazioni)</span><span class="sxs-lookup"><span data-stu-id="1aa62-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="1aa62-108">Un altro utente tramite una conversazione peer-to-peer, ad esempio la messaggistica istantanea o una chiamata audio</span><span class="sxs-lookup"><span data-stu-id="1aa62-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1aa62-109">Lync Server 2013 tiene traccia delle informazioni relative a ogni sessione: chi ha chiamato chi; quali endpoint sono stati usati nella sessione; durata della sessione Qual è stata la qualità percepita della sessione; E così via.</span><span class="sxs-lookup"><span data-stu-id="1aa62-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="1aa62-110">Tuttavia, Lync Server non registra e archivia la chiamata effettiva stessa.</span><span class="sxs-lookup"><span data-stu-id="1aa62-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="1aa62-111">Che include anche le sessioni di messaggistica istantanea: Sebbene Lync Server registri informazioni sulle sessioni di messaggistica istantanea, non mantiene un record di ogni messaggio istantaneo inviato durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="1aa62-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="1aa62-112">Le informazioni dettagliate sulle chiamate raccolte da Lync Server possono essere usate per qualsiasi numero di usi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="1aa62-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="1aa62-113">**Return on Investment (ROI)**.</span><span class="sxs-lookup"><span data-stu-id="1aa62-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="1aa62-114">Gli amministratori possono confrontare i dati di utilizzo raccolti da Monitoring Server in base a dati simili raccolti per il sistema di telefonia precedente per mostrare il risparmio dei costi e giustificare la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aa62-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="1aa62-115">**Gestione inventario dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1aa62-115">**Device Inventory Management**.</span></span> <span data-ttu-id="1aa62-116">Le informazioni sulla gestione degli asset consentono agli amministratori di identificare i vecchi dispositivi ancora in uso che devono essere sostituiti, nonché di identificare i dispositivi costosi che non sembrano essere sempre usati.</span><span class="sxs-lookup"><span data-stu-id="1aa62-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="1aa62-117">Help desk.</span><span class="sxs-lookup"><span data-stu-id="1aa62-117">Help Desk.</span></span> <span data-ttu-id="1aa62-118">La risoluzione dei problemi dei dati consente agli ingegneri del supporto di determinare il motivo per cui la chiamata di un utente non è riuscita e di farlo senza dover raccogliere log lato server o client.</span><span class="sxs-lookup"><span data-stu-id="1aa62-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="1aa62-119">Queste informazioni possono essere facilmente accessibili e comprese dal personale di supporto che non ha una profonda conoscenza tecnica di Microsoft Lync 2013 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa62-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="1aa62-120">**Risoluzione dei problemi di sistema**.</span><span class="sxs-lookup"><span data-stu-id="1aa62-120">**System Troubleshooting**.</span></span> <span data-ttu-id="1aa62-121">Consente agli amministratori di rilevare problemi importanti che potrebbero impedire agli utenti finali di eseguire attività di base, ad esempio partecipare a una conferenza, stabilire una chiamata o inviare un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="1aa62-121">Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="1aa62-122">Oltre a queste informazioni di base sulle chiamate, il server di monitoraggio offre anche un meccanismo che consente agli endpoint SIP (ad esempio Lync 2013) di fornire informazioni di risoluzione dei problemi a cui il server non avrebbe altrimenti accesso:</span><span class="sxs-lookup"><span data-stu-id="1aa62-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="1aa62-123">**Metriche multimediali che incidono sulla qualità**.</span><span class="sxs-lookup"><span data-stu-id="1aa62-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="1aa62-124">Queste metriche trattano la trasmissione effettiva della chiamata stessa; in altre cose, essi includono una sorta di log di viaggio durante i viaggi di chiamata attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="1aa62-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="1aa62-125">Queste metriche (che includono elementi come perdita di pacchetti, jitter e tempi di andata e ritorno) offrono informazioni su ciò che è accaduto alla chiamata dal momento in cui ha lasciato l'endpoint fino al momento in cui è arrivato all'endpoint dell'altra persona.</span><span class="sxs-lookup"><span data-stu-id="1aa62-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="1aa62-126">**Problemi segnalati all'utente finale**.</span><span class="sxs-lookup"><span data-stu-id="1aa62-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="1aa62-127">Queste metriche includono notifiche di qualità scadente che Lync 2013 presenta agli utenti finali nei casi in cui siano troppo lontani da un microfono, che parli troppo dolcemente, che abbiano una connessione di rete scadente o che abbiano una qualità scadente perché un altro programma nel computer è utilizzo delle risorse disponibili.</span><span class="sxs-lookup"><span data-stu-id="1aa62-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="1aa62-128">**Informazioni sull'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="1aa62-128">**Environment Information**.</span></span> <span data-ttu-id="1aa62-129">Queste metriche denominano fattori di qualità come il tipo di microfono e gli altoparlanti usati, se l'utente è connesso tramite una connessione VPN e se l'utente si trova in una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="1aa62-129">These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="1aa62-130">Alla fine di ogni chiamata, gli endpoint conformi a SIP trasmettono automaticamente queste informazioni al server front-end che facilita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1aa62-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="1aa62-131">Non è necessario eseguire alcuna operazione per ottenere gli endpoint per trasmettere tali informazioni; Questo comportamento è incorporato nel protocollo SIP.</span><span class="sxs-lookup"><span data-stu-id="1aa62-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="1aa62-132">Tuttavia, se si vogliono raccogliere e archiviare tali informazioni, è necessario installare e abilitare il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1aa62-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="1aa62-133">Se si installa e si Abilita il monitoraggio, le informazioni sulle chiamate vengono raccolte dagli agenti in uso nel server front-end e inoltrate a una coppia di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1aa62-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="1aa62-134">Si noti che il processo di installazione e configurazione del monitoraggio è stato semplificato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa62-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="1aa62-135">Nelle versioni precedenti del software il monitoraggio richiedeva un ruolo di server di monitoraggio distinto, che in genere significava un computer separato da accantonare per l'uso come server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1aa62-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="1aa62-136">In Lync Server 2013, tuttavia, il ruolo del server di monitoraggio è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="1aa62-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="1aa62-137">Il servizio di monitoraggio, sotto forma di "agenti di raccolta dati unificati", è invece stato collocato in tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="1aa62-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="1aa62-138">Questo ha almeno due vantaggi principali.</span><span class="sxs-lookup"><span data-stu-id="1aa62-138">This has at least two major benefits.</span></span> <span data-ttu-id="1aa62-139">Collocazione del servizio di monitoraggio:</span><span class="sxs-lookup"><span data-stu-id="1aa62-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="1aa62-140">Riduce il numero di ruoli del server necessari per l'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa62-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="1aa62-141">Il decremento del ruolo del server di monitoraggio consente inoltre di ridurre i costi eliminando la necessità di gestire server dedicati per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1aa62-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="1aa62-142">Riduce la complessità della configurazione e dell'amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa62-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="1aa62-143">Collocando i servizi di monitoraggio in ogni server front-end non è più necessario installare, configurare e gestire il ruolo del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1aa62-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="1aa62-144">Per altre informazioni, vedere l'argomento [distribuzione di monitoraggio in Lync server 2013](lync-server-2013-deploying-monitoring.md) nella Guida alla distribuzione di lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa62-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

