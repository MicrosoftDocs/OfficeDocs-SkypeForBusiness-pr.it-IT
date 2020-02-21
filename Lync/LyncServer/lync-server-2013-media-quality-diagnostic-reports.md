---
title: 'Lync Server 2013: rapporti di diagnostica per la qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6c2a11be8baabd74d8928fcb805ecf7367d23d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="5c3d2-102">Rapporti di diagnostica qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c3d2-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c3d2-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5c3d2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5c3d2-104">Nei Rapporti diagnostica qualità multimediale vengono fornite informazioni sulla qualità delle chiamate, nonché informazioni per la diagnostica e la risoluzione dei problemi relativi a chiamate non riuscite.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c3d2-105">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="5c3d2-105">In This Section</span></span>

  - <span data-ttu-id="5c3d2-106">[Il rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   fornisce dati generali sulla qualità per i diversi tipi di endpoint, tra cui le chiamate peer-to-peer VoIP aziendale, le chiamate in conferenza VoIP aziendale e le chiamate che si basano almeno in parte sulla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="5c3d2-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="5c3d2-107">[Il rapporto di confronto qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   fornisce un confronto tra i valori di qualità delle chiamate per i diversi tipi di chiamate audio (ad esempio, le chiamate effettuate tramite una rete wireless o le chiamate effettuate tramite una connessione cablata).</span><span class="sxs-lookup"><span data-stu-id="5c3d2-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="5c3d2-108">[Il rapporto prestazioni server in Lync Server 2013](lync-server-2013-server-performance-report.md)   elenca i server che hanno riscontrato la maggior parte dei problemi, in base alle misure di tali metriche di qualità chiave come degrado, perdita di pacchetti e instabilità.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="5c3d2-109">[Il rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md)   fornisce un elenco di percorsi di rete e un riepilogo della qualità multimediale delle chiamate che si verificano in ogni percorso.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="5c3d2-110">Ai fini di questo rapporto, i percorsi sono basati su subnet IP.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="5c3d2-111">[Il rapporto sui dispositivi in Lync Server 2013](lync-server-2013-device-report.md)   fornisce un riepilogo dei dispositivi utilizzati per le chiamate vocali di VoIP aziendale e include la qualità media delle chiamate in base al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="5c3d2-112">[Il rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md)   fornisce informazioni dettagliate sulle telefonate effettuate o ricevute all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="5c3d2-113">[Il rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md)   fornisce informazioni dettagliate sulle telefonate effettuate o ricevute all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="5c3d2-114">[Il rapporto tendenze qualità multimediale server in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   consente di confrontare graficamente fino a 5 Server in base alla qualità delle metriche di utilizzo, ad esempio il volume delle chiamate, la percentuale di chiamate insufficienti, la perdita di pacchetti e l'instabilità.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="5c3d2-115">[Il rapporto distribuzione metriche di qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   fornisce un grafico che mostra i valori di distribuzione per una metrica di qualità di esperienza, ad esempio instabilità o perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="5c3d2-116">[Il rapporto tendenze percorso in Lync Server 2013](lync-server-2013-location-trend-report.md)   fornisce informazioni sulla qualità delle chiamate per i percorsi di rete.</span><span class="sxs-lookup"><span data-stu-id="5c3d2-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

