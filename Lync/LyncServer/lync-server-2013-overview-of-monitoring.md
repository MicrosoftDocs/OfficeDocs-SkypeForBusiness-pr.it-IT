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
ms.openlocfilehash: 47d53d740af9cb0407b0309d858d4a1a85b3b976
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="7ef60-102">Panoramica del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ef60-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ef60-103">_**Ultimo argomento modificato:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="7ef60-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="7ef60-104">In Microsoft Lync Server 2013, il monitoraggio viene utilizzato per raccogliere informazioni sull'utilizzo e i dati QoE (Quality of Experience) sulle sessioni di comunicazione coinvolte dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="7ef60-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="7ef60-105">Il termine sessione è un termine generico riferito alla connessione di un utente a:</span><span class="sxs-lookup"><span data-stu-id="7ef60-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="7ef60-106">Conferenza</span><span class="sxs-lookup"><span data-stu-id="7ef60-106">Conference</span></span>

  - <span data-ttu-id="7ef60-107">Una modalità di conferenza, ad esempio audio/video o di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="7ef60-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="7ef60-108">Un altro utente tramite una conversazione peer-to-peer come la messaggistica istantanea o una chiamata audio</span><span class="sxs-lookup"><span data-stu-id="7ef60-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ef60-109">Lync Server 2013 tiene conto delle informazioni su ogni sessione: chi ha chiamato chi; quali endpoint sono stati utilizzati nella sessione; durata della sessione. Qual è la qualità percepita della sessione; E così via.</span><span class="sxs-lookup"><span data-stu-id="7ef60-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="7ef60-110">Tuttavia, Lync Server non registra e archivia la chiamata vera e propria.</span><span class="sxs-lookup"><span data-stu-id="7ef60-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="7ef60-111">Che include anche le sessioni di messaggistica istantanea: anche se Lync Server registra informazioni sulle sessioni di messaggistica istantanea, non gestisce un record di ogni messaggio istantaneo inviato durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="7ef60-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="7ef60-112">Le informazioni dettagliate sulle chiamate raccolte da Lync Server possono essere utilizzate per qualsiasi numero di utilizzi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="7ef60-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="7ef60-113">**Rendimento dell'investimento (ROI)**.</span><span class="sxs-lookup"><span data-stu-id="7ef60-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="7ef60-114">Gli amministratori possono confrontare i dati di utilizzo raccolti da Monitoring Server a dati simili raccolti per il sistema di telefonia precedente per poter mostrare risparmi sui costi e contribuire a giustificare la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ef60-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="7ef60-p104">**Gestione dell'inventario dei dispositivi**. Le informazioni di gestione delle risorse consentono agli amministratori di individuare i dispositivi obsoleti ancora in uso che devono essere sostituiti, nonché identificare i dispositivi costosi che risultano inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="7ef60-p104">**Device Inventory Management**. Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="7ef60-117">Supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="7ef60-117">Help Desk.</span></span> <span data-ttu-id="7ef60-118">I dati sulla risoluzione dei problemi consentono ai tecnici dei servizi di supporto di stabilire le cause di una chiamata non riuscita, senza dover raccogliere log sul lato server o client.</span><span class="sxs-lookup"><span data-stu-id="7ef60-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="7ef60-119">Tali informazioni possono essere facilmente accessibili e intese da personale di supporto che non dispone di una conoscenza approfondita tecnica di Microsoft Lync 2013 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ef60-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="7ef60-p106">**Risoluzione dei problemi di sistema**. Gli amministratori hanno la possibilità di rilevare i principali problemi che possono impedire agli utenti finali di eseguire attività di base come partecipare a una conferenza, eseguire una chiamata o inviare un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="7ef60-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="7ef60-122">Oltre a queste informazioni sulla chiamata di base, il Monitoring Server fornisce anche un meccanismo che consente agli endpoint SIP (come Lync 2013) di fornire informazioni sulla risoluzione dei problemi a cui il server non avrebbe altrimenti accesso:</span><span class="sxs-lookup"><span data-stu-id="7ef60-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="7ef60-p107">**Metriche che influiscono sulla qualità**. Queste metriche riguardano l'effettiva trasmissione della chiamata, ovvero offrono una sorta di registro di viaggio del percorso della chiamata in rete. Queste metriche, che includono dati come perdita di pacchetti, instabilità e tempi di round trip, offrono informazioni su cosa accade per la chiamata dal momento in cui lascia l'endpoint di partenza al momento in cui raggiunge l'endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7ef60-p107">**Media Metrics that Impact Quality**. These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network. These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="7ef60-126">**Problemi segnalati all'utente finale**.</span><span class="sxs-lookup"><span data-stu-id="7ef60-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="7ef60-127">Queste metriche includono notifiche di qualità scadente che Lync 2013 presenta agli utenti finali nei casi in cui sono troppo lontani da un microfono, parlando troppo piano, hanno una connessione di rete scadente o stanno vivendo una qualità scadente perché un altro programma del computer è utilizzo delle risorse disponibili.</span><span class="sxs-lookup"><span data-stu-id="7ef60-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="7ef60-p109">**Informazioni sull'ambiente**. Queste metriche offrono dati dettagliati su aspetti che influiscono sulla qualità delle chiamate, come il tipo di microfono e altoparlanti in uso, se l'utente è connesso tramite VPN e se l'utente sta utilizzando una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="7ef60-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="7ef60-p110">Al termine di ogni chiamata, gli endpoint conformi a SIP trasmettono automaticamente queste informazioni al Front End Server che ha inoltrato la chiamata. Non è necessario eseguire alcuna operazione per fare in modo che gli endpoint trasmettano tali informazioni, perché questo comportamento è incorporato nel protocollo SIP. Se si desidera raccogliere e archiviare tali informazioni, tuttavia, è necessario installare e abilitare il monitoraggio. In questo modo, le informazioni sulle chiamate vengono raccolte dagli agenti in esecuzione nel Front End Server e inoltrate a una coppia di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ef60-p110">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call. You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol. However, if you want to collect and store that information, then you need to install and enable monitoring. If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="7ef60-134">Si noti che il processo di installazione e configurazione del monitoraggio è stato semplificato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ef60-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="7ef60-135">Nelle versioni precedenti del software, il monitoraggio richiedeva un ruolo di Monitoring Server separato, che in genere indicava un computer separato accantonato per l'utilizzo come Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="7ef60-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="7ef60-136">In Lync Server 2013, tuttavia, il ruolo Monitoring Server è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="7ef60-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="7ef60-137">Al contrario, il servizio di monitoraggio, sotto forma di "agenti di raccolta dati unificati", è stato collocato in tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="7ef60-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="7ef60-138">Sono presenti almeno due vantaggi principali.</span><span class="sxs-lookup"><span data-stu-id="7ef60-138">This has at least two major benefits.</span></span> <span data-ttu-id="7ef60-139">Collocazione del servizio di monitoraggio:</span><span class="sxs-lookup"><span data-stu-id="7ef60-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="7ef60-140">Consente di ridurre il numero di ruoli del server necessari per l'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ef60-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="7ef60-141">La rimozione del ruolo Monitoring Server contribuisce anche a ridurre i costi, eliminando la necessità di gestire server dedicati per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7ef60-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="7ef60-142">Riduce la complessità dell'installazione e dell'amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ef60-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="7ef60-143">La collocazione dei servizi di monitoraggio in ogni Front End Server significa che non è più necessario installare, configurare e gestire il ruolo Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="7ef60-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="7ef60-144">Per ulteriori informazioni, vedere l'argomento [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) nella Guida alla distribuzione di lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="7ef60-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

