---
title: 'Lync Server 2013: elenco delle tabelle di conformità del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 322b700b807f8654e96572a3c040ddd7fe0d1e5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="1e2cf-102">Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e2cf-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e2cf-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1e2cf-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1e2cf-104">Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="1e2cf-105">Elenco delle tabelle di conformità del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="1e2cf-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e2cf-106">tavolo</span><span class="sxs-lookup"><span data-stu-id="1e2cf-106">Table</span></span></th>
<th><span data-ttu-id="1e2cf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e2cf-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e2cf-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e2cf-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e2cf-109">Include gli eventi di conformità ancora non elaborati da tutti gli adattatori configurati.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="1e2cf-110">In questa tabella sono inclusi gli eventi relativi a chat persistente, ad esempio i messaggi di chat e i download di file.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="1e2cf-111">Gli eventi dei partecipanti vengono registrati dalla tabella ComplianceParticipant.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="1e2cf-112">I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella ComplianceFanout.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e2cf-113"><a href="lync-server-2013-tblcompliancefanout.md">ComplianceFanout in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e2cf-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e2cf-114">Include i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="1e2cf-115">È strettamente associata alla tabella ComplianceData.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e2cf-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e2cf-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e2cf-117">Include i partecipanti correnti per servizio chat e per server.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="1e2cf-118">Viene mantenuto in base agli eventi di conformità di join e parti ricevuti dal servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e2cf-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e2cf-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e2cf-120">Contiene informazioni relative allo stato di conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

