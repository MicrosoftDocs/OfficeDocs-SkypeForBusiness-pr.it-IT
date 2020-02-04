---
title: 'Lync Server 2013: report di diagnostica delle chiamate'
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
ms.openlocfilehash: 41100a6cc41c38b3d32870d530f99d8c919a2e83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="d4a7a-102">Chiamare i report di diagnostica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4a7a-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4a7a-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d4a7a-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d4a7a-104">I report di diagnostica delle chiamate includono informazioni di riepilogo e dati di diagnostica per sessioni peer-to-peer e conferenze non riuscite.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4a7a-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d4a7a-105">In This Section</span></span>

  - <span data-ttu-id="d4a7a-106">[Report di riepilogo diagnostica chiamata in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   offre un riepilogo complessivo delle sessioni peer-to-peer non riuscite e delle sessioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="d4a7a-107">Le sessioni peer-to-peer sono sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="d4a7a-108">Le sessioni di conferenza coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="d4a7a-109">[Il report di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   offre una visualizzazione di tendenza complessiva delle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="d4a7a-110">Una sessione peer-to-peer coinvolge solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="d4a7a-111">[Report di diagnostica conferenza in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   offre una visualizzazione di tendenza complessiva delle sessioni di conferenza non riuscite e delle visualizzazioni di tendenza per ogni modalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="d4a7a-112">Le sessioni di conferenza coinvolgono almeno tre partecipanti.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="d4a7a-113">[Il report errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md)   offre un elenco degli errori più frequenti e delle relative tendenze nel tempo.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="d4a7a-114">[Il report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   offre un'analisi delle sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="d4a7a-115">[Il report elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md)   offre informazioni dettagliate sui singoli partecipanti coinvolti in una conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="d4a7a-116">[Report di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md)   offre informazioni di diagnostica e risoluzione dei problemi (inclusi i codici di risposta SIP e le intestazioni di diagnostica e gli ID) per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="d4a7a-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

