---
title: 'Lync Server 2013: Elenco delle tabelle di conformità del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="91058-102">Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91058-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91058-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="91058-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="91058-104">Lo schema del database di conformità della chat persistente è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="91058-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="91058-105">Elenco delle tabelle di conformità Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="91058-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91058-106">Tabella</span><span class="sxs-lookup"><span data-stu-id="91058-106">Table</span></span></th>
<th><span data-ttu-id="91058-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91058-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91058-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91058-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="91058-109">Contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda configurata.</span><span class="sxs-lookup"><span data-stu-id="91058-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="91058-110">Questa tabella include eventi relativi alla chat persistente, ad esempio messaggi di chat e download di file.</span><span class="sxs-lookup"><span data-stu-id="91058-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="91058-111">(Gli eventi dei partecipanti vengono registrati dalla tabella tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="91058-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="91058-112">I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella tblComplianceFanout.</span><span class="sxs-lookup"><span data-stu-id="91058-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91058-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91058-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="91058-114">Contiene i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="91058-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="91058-115">Questa tabella è strettamente associata alla tabella tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="91058-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91058-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91058-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="91058-117">Contiene partecipanti correnti per servizio di chat e per server.</span><span class="sxs-lookup"><span data-stu-id="91058-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="91058-118">Viene mantenuto in base agli eventi di conformità di join e part ricevuti dal servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="91058-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91058-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91058-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="91058-120">Contiene informazioni sullo stato di conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="91058-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

