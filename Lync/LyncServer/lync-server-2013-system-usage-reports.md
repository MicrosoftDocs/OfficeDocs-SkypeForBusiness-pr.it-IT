---
title: "Lync Server 2013: report sull'utilizzo del sistema"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94118832be0acab9e354016a76102b0a83d253d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="d6432-102">Report sull'utilizzo del sistema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6432-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d6432-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d6432-104">I report sull'utilizzo del sistema contengono informazioni sull'uso del sistema basate sui dati di registrazione dettagli chiamata (CDR) raccolti dal server Lync.</span><span class="sxs-lookup"><span data-stu-id="d6432-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6432-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d6432-105">In This Section</span></span>

  - [<span data-ttu-id="d6432-106">Report di registrazione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="d6432-107">Fornisce un riepilogo della connettività degli utenti alla distribuzione di Lync Server 2013 in base agli eventi di registrazione, ad esempio gli accessi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d6432-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="d6432-108">Il report consente di visualizzare sia gli accessi interni che quelli esterni e di confrontare il numero di utenti che hanno eseguito l'accesso a Lync Server 2013 con il numero di utenti che hanno effettivamente usato il servizio durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d6432-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="d6432-109">Report di riepilogo attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="d6432-110">Fornisce un riepilogo delle sessioni di messaggistica istantanea, audio, video, trasferimento di file e condivisione applicazioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="d6432-110">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions.</span></span> <span data-ttu-id="d6432-111">Le sessioni peer-to-peer sono sessioni che coinvolgono solo due utenti.</span><span class="sxs-lookup"><span data-stu-id="d6432-111">Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="d6432-112">Report Riepilogo conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="d6432-113">Fornisce un riepilogo di tutte le attività di conferenza.</span><span class="sxs-lookup"><span data-stu-id="d6432-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="d6432-114">Le conferenze sono sessioni che coinvolgono tre o più persone.</span><span class="sxs-lookup"><span data-stu-id="d6432-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="d6432-115">Report di riepilogo conferenza PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="d6432-116">Fornisce un riepilogo di tutte le conferenze PSTN.</span><span class="sxs-lookup"><span data-stu-id="d6432-116">Provides a summary of all PSTN conferences.</span></span> <span data-ttu-id="d6432-117">Si tratta di conferenze in cui almeno un utente effettua la chiamata tramite la rete PSTN (Public Switched Telephone Network), definita anche conferenza telefonica con *accesso esterno*.</span><span class="sxs-lookup"><span data-stu-id="d6432-117">These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="d6432-118">Report sull'utilizzo di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="d6432-119">Fornisce un riepilogo dell'utilizzo di Response Group.</span><span class="sxs-lookup"><span data-stu-id="d6432-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="d6432-120">L'applicazione Response Group consente di instradare automaticamente le chiamate telefoniche ad entità come un help desk o una linea di supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d6432-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="d6432-121">Report sull'inventario del telefono IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="d6432-122">Fornisce informazioni sui telefoni IP attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6432-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="d6432-123">Il report si basa su registrazioni telefoniche e accessi.</span><span class="sxs-lookup"><span data-stu-id="d6432-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="d6432-124">Non dovrebbe essere considerato un inventario completo.</span><span class="sxs-lookup"><span data-stu-id="d6432-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="d6432-125">Ad esempio, potresti aver rimosso i telefoni ancora elencati nel report perché hanno effettuato l'accesso almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="d6432-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="d6432-126">Analogamente, potresti anche avere nuovi telefoni che non vengono visualizzati nel report semplicemente perché gli utenti non hanno ancora effettuato l'accesso a Lync Server con i loro nuovi telefoni.</span><span class="sxs-lookup"><span data-stu-id="d6432-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="d6432-127">Report controllo ammissione chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6432-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="d6432-128">Fornisce un elenco di attività peer-to-peer e conferenze che usano il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d6432-128">Provides a list of peer-to-peer and conference activities that use call admission control.</span></span> <span data-ttu-id="d6432-129">Il controllo di ammissione di chiamata (CAC) è un modo per determinare se è consigliabile consentire sessioni di comunicazioni in tempo reale, ad esempio chiamate vocali o videochiamate, in base a vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="d6432-129">Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

