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
ms.openlocfilehash: 692c3e3baa564b2276be678b48e67b5f2a4abd56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="f77cd-102">Rapporti di diagnostica delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f77cd-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f77cd-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="f77cd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="f77cd-104">Nei rapporti di diagnostica delle chiamate vengono forniti informazioni riepilogative e dati diagnostici per sessioni peer-to-peer e di conferenza non riuscite.</span><span class="sxs-lookup"><span data-stu-id="f77cd-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f77cd-105">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f77cd-105">In This Section</span></span>

  - <span data-ttu-id="f77cd-106">[Il rapporto riepilogativo di diagnostica chiamate in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   fornisce un riepilogo generale delle sessioni peer-to-peer e delle sessioni di conferenza non riuscite.</span><span class="sxs-lookup"><span data-stu-id="f77cd-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="f77cd-107">Le sessioni peer-to-peer sono sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f77cd-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="f77cd-108">Le sessioni di conferenza coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f77cd-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="f77cd-109">[Il rapporto di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   fornisce una visualizzazione di tendenza complessiva delle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="f77cd-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="f77cd-110">Una sessione peer-to-peer coinvolge solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f77cd-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="f77cd-111">[Il rapporto di diagnostica conferenze in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   fornisce una visualizzazione di tendenza complessiva delle sessioni di conferenza non riuscite e delle visualizzazioni di tendenza per ogni modalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="f77cd-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="f77cd-112">Le sessioni di conferenza coinvolgono almeno tre partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f77cd-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="f77cd-113">[Il rapporto errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md)   fornisce un elenco degli errori più frequenti e delle relative tendenze nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f77cd-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="f77cd-114">[Il rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   fornisce un'analisi delle sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="f77cd-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="f77cd-115">[Il rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md)   fornisce informazioni dettagliate sui singoli partecipanti coinvolti in una conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="f77cd-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="f77cd-116">[Report di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md)   fornisce informazioni diagnostiche e di risoluzione dei problemi (inclusi i codici di risposta SIP e gli ID e le intestazioni di diagnostica) per le sessioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="f77cd-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

