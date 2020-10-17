---
title: 'Lync Server 2013: rapporti di diagnostica chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46073c5540b0b4cd48f6c5a13c17d4a4d3f12a46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526333"
---
# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="632ca-102">Rapporti di diagnostica delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="632ca-102">Call Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="632ca-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="632ca-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="632ca-104">Nei rapporti di diagnostica delle chiamate vengono forniti informazioni riepilogative e dati diagnostici per sessioni peer-to-peer e di conferenza non riuscite.</span><span class="sxs-lookup"><span data-stu-id="632ca-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="632ca-105">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="632ca-105">In This Section</span></span>

  - <span data-ttu-id="632ca-106">[Rapporto riepilogativo di diagnostica chiamate in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)     Viene fornito un riepilogo generale delle sessioni peer-to-peer non riuscite e delle sessioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="632ca-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="632ca-107">Le sessioni peer-to-peer sono sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="632ca-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="632ca-108">Le sessioni di conferenza coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="632ca-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="632ca-109">[Rapporto di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)     Fornisce una visualizzazione di tendenza complessiva delle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="632ca-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="632ca-110">Una sessione peer-to-peer coinvolge solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="632ca-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="632ca-111">[Rapporto di diagnostica conferenze in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)     Fornisce una visualizzazione di tendenza complessiva delle sessioni di conferenza e delle visualizzazioni di tendenza non riuscite per ogni modalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="632ca-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="632ca-112">Le sessioni di conferenza coinvolgono almeno tre partecipanti.</span><span class="sxs-lookup"><span data-stu-id="632ca-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="632ca-113">[Rapporto errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md)     Viene fornito un elenco degli errori più frequenti e delle relative tendenze nel tempo.</span><span class="sxs-lookup"><span data-stu-id="632ca-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="632ca-114">[Rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md)     Fornisce un'analisi delle sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="632ca-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="632ca-115">[Rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md)     Vengono fornite informazioni dettagliate sui singoli partecipanti coinvolti in una conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="632ca-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="632ca-116">[Rapporto di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md)     Fornisce informazioni di diagnostica e risoluzione dei problemi (inclusi i codici di risposta SIP e le intestazioni e gli ID di diagnostica) per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="632ca-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

