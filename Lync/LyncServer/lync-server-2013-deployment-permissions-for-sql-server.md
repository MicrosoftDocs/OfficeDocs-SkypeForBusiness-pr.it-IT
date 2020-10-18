---
title: 'Lync Server 2013: autorizzazioni di distribuzione per SQL Server'
description: 'Lync Server 2013: autorizzazioni di distribuzione per SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575722"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="7e513-103">Autorizzazioni di distribuzione per SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e513-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e513-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7e513-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7e513-105">Microsoft SQL Server 2012 ha requisiti specifici per l'installazione e la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e513-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="7e513-106">Poiché Windows e SQL Server definiscono la propria sicurezza in modo diverso, l'accesso come amministratore nel dominio di Active Directory non concede implicitamente autorizzazioni per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e513-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="7e513-107">È inoltre necessario essere membri dell'entità sysadmin nel server basato su SQL Server che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="7e513-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="7e513-108">Autorizzazioni necessarie per l'installazione dei database e di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7e513-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="7e513-109">Le opzioni seguenti specificano tre autorizzazioni e associazioni di appartenenza a gruppi per l'installazione di file di Lync Server 2013 e database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e513-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="7e513-110">Scegliere lo scenario più adatto ai requisiti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e513-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="7e513-111">Associazioni di autorizzazioni e appartenenze ai gruppi</span><span class="sxs-lookup"><span data-stu-id="7e513-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e513-112">Ruolo SQL Server o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e513-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="7e513-113">Autorizzazioni e appartenenze ai gruppi di SQL Server tipiche del ruolo</span><span class="sxs-lookup"><span data-stu-id="7e513-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="7e513-114">Autorizzazioni di Lync Server 2013 e appartenenza a gruppi tipiche del ruolo</span><span class="sxs-lookup"><span data-stu-id="7e513-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="7e513-115">Risultati delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7e513-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e513-116">Amministratore di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e513-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="7e513-117">Deve appartenere al gruppo di sicurezza sysadmins di SQL Server ed essere membro del gruppo Administrators locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e513-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="7e513-118">Deve essere un membro del gruppo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7e513-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="7e513-119">L'amministratore di Lync Server 2013 dispone delle autorizzazioni appropriate per installare sia Lync Server 2013 che i database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e513-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e513-120">Amministratore di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e513-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="7e513-121">Membro del gruppo sysadmins di SQL Server (o equivalente) e membro del gruppo Administrators locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e513-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="7e513-122">Deve essere un membro del gruppo RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="7e513-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="7e513-123">L'amministratore di SQL Server dispone delle autorizzazioni appropriate per installare sia Lync Server 2013 che i database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e513-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e513-124">Entrambi gli amministratori condividono responsabilità per l'installazione</span><span class="sxs-lookup"><span data-stu-id="7e513-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="7e513-125">L'amministratore di SQL Server è membro del gruppo sysadmins (o equivalente) e membro del gruppo Administrarors locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e513-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="7e513-126">Lync Server 2013 Administrator è membro di RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7e513-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7e513-127">L'amministratore di Lync Server 2013 può installare Lync Server 2013, ma non è in grado di installare i database.</span><span class="sxs-lookup"><span data-stu-id="7e513-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="7e513-128">L'amministratore di SQL Server utilizza i cmdlet di Lync Server Management Shell e Windows PowerShell forniti dall'amministratore di Lync Server 2013 per installare i database.</span><span class="sxs-lookup"><span data-stu-id="7e513-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="7e513-129">Il Lync Server 2013 Management Shell utilizzato dall'amministratore di SQL Server viene installato nel front end server.</span><span class="sxs-lookup"><span data-stu-id="7e513-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="7e513-130">In questo modo viene eliminata la necessità di installare gli strumenti di amministrazione di Lync Server 2013 nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e513-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

