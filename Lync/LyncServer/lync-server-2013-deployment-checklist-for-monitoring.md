---
title: 'Lync Server 2013: elenco di controllo di distribuzione per il monitoraggio'
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
ms.openlocfilehash: 8e455cb06c6890bb8925bc35a8d5f4c6775288f8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="a45d3-102">Elenco di controllo di distribuzione per il monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a45d3-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a45d3-103">_**Ultimo argomento modificato:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="a45d3-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="a45d3-104">Anche se il monitoraggio è già installato e attivato in ogni Front End Server, è necessario intraprendere alcuni passaggi prima di poter effettivamente raccogliere dati di monitoraggio per Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a45d3-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a45d3-105">Questi passaggi sono descritti nell'elenco di controllo seguente:</span><span class="sxs-lookup"><span data-stu-id="a45d3-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a45d3-106">Fase</span><span class="sxs-lookup"><span data-stu-id="a45d3-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="a45d3-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="a45d3-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="a45d3-108">Appartenenza a gruppi e ruoli </span><span class="sxs-lookup"><span data-stu-id="a45d3-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="a45d3-109">Documentazione</span><span class="sxs-lookup"><span data-stu-id="a45d3-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45d3-110"><strong>Installare l'hardware e il software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="a45d3-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="a45d3-111">Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="a45d3-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="a45d3-112">Utente di dominio che è anche membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="a45d3-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="a45d3-113"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella Guida alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="a45d3-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="a45d3-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella Guida relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="a45d3-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45d3-115"><strong>Creare la topologia interna appropriata per supportare il monitoraggio</strong></span><span class="sxs-lookup"><span data-stu-id="a45d3-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="a45d3-116">Utilizzare il generatore di topologie di Lync Server 2013 per aggiungere database di monitoraggio alla topologia e quindi pubblicare la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="a45d3-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="a45d3-117">Per definire una topologia, un utente membro del gruppo utenti locali.</span><span class="sxs-lookup"><span data-stu-id="a45d3-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="a45d3-118">Per pubblicare la topologia, un utente membro del gruppo Domain Administrators e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a45d3-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="a45d3-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associazione di un archivio di monitoraggio a un pool Front end in Lync Server 2013</a> nella Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="a45d3-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45d3-120"><strong>Abilitare le impostazioni di monitoraggio appropriate</strong></span><span class="sxs-lookup"><span data-stu-id="a45d3-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="a45d3-121">Abilitare il monitoraggio di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) negli ambiti globali e/o del sito.</span><span class="sxs-lookup"><span data-stu-id="a45d3-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="a45d3-122">Un utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che fornisce l'accesso ai cmdlet CsCdrConfiguration e CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a45d3-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="a45d3-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurazione delle impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Lync Server 2013</a> nella Guida alle operazioni</span><span class="sxs-lookup"><span data-stu-id="a45d3-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

