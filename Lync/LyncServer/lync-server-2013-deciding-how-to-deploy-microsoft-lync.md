---
title: 'Lync Server 2013: scelta della modalità di distribuzione di Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f4e622d71175ec393706af39ce470c5030216a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="954dc-102">Decidere come distribuire Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="954dc-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="954dc-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="954dc-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="954dc-104">Durante la pianificazione di Lync, la prima decisione importante è la distribuzione di Microsoft Lync: come Lync Server 2013 in locale oppure Lync Online con Microsoft 365 o Office 365 nel cloud.</span><span class="sxs-lookup"><span data-stu-id="954dc-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft 365 or Office 365 in the cloud.</span></span>

  - <span data-ttu-id="954dc-105">**Lync Server 2013 locale** : questa opzione offre il set completo di funzionalità di Lync e fornisce la massima flessibilità per la configurazione, la personalizzazione e la gestione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="954dc-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="954dc-106">Tutti i server sono installati localmente e mantenuti presso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="954dc-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="954dc-107">Una distribuzione locale fornisce l'intera gamma di funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="954dc-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="954dc-108">**Lync Online nel cloud** Lync Online è stato ideato per le organizzazioni che desiderano i vantaggi di costo e agilità dei servizi di messaggistica istantanea basati su cloud, presenza e riunioni senza sacrificare le funzionalità di Business-Class di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="954dc-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="954dc-109">Con Lync Online, Microsoft distribuisce e gestisce l'infrastruttura server necessaria e gestisce la manutenzione, le patch e gli aggiornamenti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="954dc-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="954dc-110">Alcune funzionalità disponibili in una distribuzione locale non sono disponibili in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="954dc-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="954dc-111">Il tipo di distribuzione più adatto per un'azienda dipende dal tipo di workload che si ha bisogno di distribuire, nonché dalla posizione geografica e dallo stato dell'attività dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="954dc-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="954dc-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="954dc-112">Lync Server</span></span>

<span data-ttu-id="954dc-113">Una distribuzione locale di Lync Server rappresenta la soluzione ideale nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="954dc-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="954dc-114">Funzionalità complete di **VoIP aziendale**     Se si prevede di distribuire una soluzione VoIP aziendale completa per la sostituzione del sistema PBX o che utilizza funzionalità di chiamata avanzate, è necessaria una distribuzione locale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="954dc-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="954dc-115">La distribuzione locale supporta un tipo di connettività diretta con i sistemi e trunk PBX, e funzionalità telefoniche avanzate come gruppi di risposta e parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="954dc-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="954dc-116">Lync Online attualmente non supporta queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="954dc-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="954dc-117">Controlli di qualità **multimediale**     Se si desidera che l'intera gamma di funzionalità di controllo della qualità multimediale, ad esempio le caratteristiche di servizio di ammissione di chiamata (CAC) e Quality of Service (QoS), si desideri una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="954dc-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="954dc-118">**Chat**     persistente Se è necessario distribuire la chat persistente per l'organizzazione, è necessario scegliere una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="954dc-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="954dc-119">Applicazioni server di terze **parti**     Solo le distribuzioni locali possono lavorare con le applicazioni di terze parti attendibili che utilizzano Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="954dc-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="954dc-120">**Società multi-nazionali/multiregionali che necessitano di supporto regionale**     Se si dispone di datacenter in più paesi o aree geografiche e devono essere distribuiti e gestiti su base regionale, è preferibile una distribuzione locale, in quanto fornisce questo tipo di funzionalità di gestione regionale.</span><span class="sxs-lookup"><span data-stu-id="954dc-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="954dc-121">**Controllo completo sui criteri, i report e gli aggiornamenti**     Con una distribuzione di Lync Server locale, è possibile accedere al set completo di criteri server e client, al monitoraggio e ad altri report e alla tempistica degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="954dc-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="954dc-122">Lync Online fornisce un sottoinsieme di impostazioni e report di criteri e fornisce una finestra limitata, anche se significativa, per l'accettazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="954dc-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="954dc-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="954dc-123">Lync Online</span></span>

<span data-ttu-id="954dc-124">Se nessuno dei precedenti rappresenta un fattore di importanza critica per la propria organizzazione, è possibile scegliere Lync Online, che offre una distribuzione e una gestibilità semplificate.</span><span class="sxs-lookup"><span data-stu-id="954dc-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="954dc-125">Lync Online offre un robusto set di funzionalità di messaggistica istantanea, presenza e conferenza e consente inoltre di abilitare le chiamate vocali e video su IP tra gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="954dc-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
