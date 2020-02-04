---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per il monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="01f84-102">Elenco di controllo di distribuzione per il monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f84-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f84-103">_**Argomento Ultima modifica:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="01f84-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="01f84-104">Anche se il monitoraggio è già installato e attivato in ogni server front-end, è necessario intraprendere diversi passaggi prima di poter effettivamente raccogliere dati di monitoraggio per Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01f84-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="01f84-105">Questi passaggi sono descritti nell'elenco di controllo seguente:</span><span class="sxs-lookup"><span data-stu-id="01f84-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f84-106">Fase</span><span class="sxs-lookup"><span data-stu-id="01f84-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="01f84-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="01f84-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="01f84-108">Appartenenza a ruoli e gruppi</span><span class="sxs-lookup"><span data-stu-id="01f84-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="01f84-109">Documentazione</span><span class="sxs-lookup"><span data-stu-id="01f84-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f84-110"><strong>Installare hardware e software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="01f84-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="01f84-111">Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="01f84-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="01f84-112">Utente del dominio che è anche membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="01f84-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="01f84-113"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella Guida alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="01f84-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="01f84-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella Guida alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="01f84-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01f84-115"><strong>Creare la topologia interna appropriata per supportare il monitoraggio</strong></span><span class="sxs-lookup"><span data-stu-id="01f84-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="01f84-116">Usare il generatore di topologia di Lync Server 2013 per aggiungere database di monitoraggio alla topologia, quindi pubblicato la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="01f84-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="01f84-117">Per definire una topologia, un utente membro del gruppo utenti locali.</span><span class="sxs-lookup"><span data-stu-id="01f84-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="01f84-118">Per pubblicare la topologia, un utente membro se il gruppo Domain Administrators e il gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="01f84-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="01f84-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associazione di un archivio di monitoraggio con un pool Front-end in Lync Server 2013</a> nella Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="01f84-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f84-120"><strong>Abilitare le impostazioni di monitoraggio appropriate</strong></span><span class="sxs-lookup"><span data-stu-id="01f84-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="01f84-121">Abilitare il monitoraggio della registrazione dei dettagli delle chiamate (CDR) e/o la qualità dell'esperienza (QoE) negli ambiti globali e/o del sito.</span><span class="sxs-lookup"><span data-stu-id="01f84-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="01f84-122">Un utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che consente di accedere ai cmdlet CsCdrConfiguration e CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="01f84-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="01f84-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza in Lync Server 2013</a> nella Guida alle operazioni</span><span class="sxs-lookup"><span data-stu-id="01f84-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

