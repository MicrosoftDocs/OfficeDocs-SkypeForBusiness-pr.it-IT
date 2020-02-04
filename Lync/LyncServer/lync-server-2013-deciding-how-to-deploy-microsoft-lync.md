---
title: 'Lync Server 2013: Determinazione della modalità di distribuzione di Microsoft Lync'
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
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="51441-102">Determinazione della modalità di distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51441-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51441-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="51441-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="51441-104">Durante la pianificazione di Lync, la prima decisione importante è la distribuzione di Microsoft Lync: come Lync Server 2013 in locale o Lync Online con Microsoft Office 365 nel cloud.</span><span class="sxs-lookup"><span data-stu-id="51441-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="51441-105">**Lync Server 2013 locale** : questa opzione offre il set completo di funzionalità Lync e offre la massima flessibilità nella configurazione, personalizzazione e gestione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="51441-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="51441-106">Tutti i server sono installati in loco e gestiti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51441-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="51441-107">Una distribuzione locale offre l'intera gamma di funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51441-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="51441-108">**Lync Online nel cloud** Lync Online è progettato per le organizzazioni che desiderano vantaggi per i costi e la flessibilità dei servizi di messaggistica istantanea, presenza e riunioni basati sul cloud, senza sacrificare le funzionalità di classe aziendale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51441-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="51441-109">Con Lync Online, Microsoft distribuisce e gestisce l'infrastruttura server necessaria e gestisce la manutenzione, le patch e gli aggiornamenti in corso.</span><span class="sxs-lookup"><span data-stu-id="51441-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="51441-110">Alcune funzionalità disponibili in una distribuzione locale non sono disponibili in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="51441-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="51441-111">Il tipo di distribuzione più adatto dipende dai carichi di lavoro che si vogliono distribuire e dallo stato geografico e aziendale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51441-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="51441-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="51441-112">Lync Server</span></span>

<span data-ttu-id="51441-113">Una distribuzione locale di Lync Server è la soluzione migliore per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="51441-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="51441-114">**Funzionalità di VoIP aziendale completa**   se si prevede di distribuire una soluzione VoIP aziendale completa per sostituire il PBX o che usa funzionalità avanzate per le chiamate, è necessaria una distribuzione locale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51441-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="51441-115">Locale supporta la connettività diretta con sistemi PBX e trunk e funzionalità avanzate per il telefono, ad esempio Response Group e Call Park.</span><span class="sxs-lookup"><span data-stu-id="51441-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="51441-116">Lync Online attualmente non supporta queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="51441-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="51441-117">**Controlli di qualità multimediale**   se si vuole che l'intera gamma di caratteristiche di garanzia della qualità dei contenuti multimediali, ad esempio le funzionalità di controllo di ammissione alle chiamate (CAC) e qualità del servizio (QoS), si voglia eseguire una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="51441-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="51441-118">**Chat persistente**   se è necessario distribuire la chat persistente per l'organizzazione, è necessario scegliere una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="51441-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="51441-119">**applicazioni server di**   terze parti solo le distribuzioni locali possono lavorare con le applicazioni di terze parti attendibili che usano Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="51441-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="51441-120">**Società multinazionali/multiregionali che necessitano**   di un supporto regionale se si hanno datacenter in più paesi o aree geografiche e i server devono essere distribuiti e gestiti su base regionale, è consigliabile una distribuzione locale, in quanto offre questo tipo di funzionalità di gestione regionale.</span><span class="sxs-lookup"><span data-stu-id="51441-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="51441-121">**Controllo completo sui criteri, i report e gli aggiornamenti**   con una distribuzione locale di Lync Server, è possibile accedere al set completo di criteri per server e client, per il monitoraggio e altri report e per la tempistica degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="51441-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="51441-122">Lync Online offre un sottoinsieme di impostazioni e report dei criteri e offre una finestra limitata, ma significativa, per l'accettazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="51441-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="51441-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="51441-123">Lync Online</span></span>

<span data-ttu-id="51441-124">Se nessuno dei fattori nell'elenco precedente è fondamentale per l'utente, è consigliabile scegliere Lync Online per semplificare la distribuzione e la gestibilità.</span><span class="sxs-lookup"><span data-stu-id="51441-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="51441-125">Lync Online offre un set di caratteristiche di messaggistica istantanea, presenza e conferenze affidabili e consente inoltre di effettuare chiamate vocali e video tramite IP tra gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51441-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

