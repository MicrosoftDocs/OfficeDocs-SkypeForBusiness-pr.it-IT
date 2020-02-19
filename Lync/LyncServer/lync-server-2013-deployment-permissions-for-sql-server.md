---
title: 'Lync Server 2013: autorizzazioni di distribuzione per SQL Server'
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
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="ca3e0-102">Autorizzazioni di distribuzione per SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca3e0-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca3e0-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ca3e0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ca3e0-104">Microsoft SQL Server 2012 ha requisiti specifici per l'installazione e la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="ca3e0-105">Poiché Windows e SQL Server definiscono la propria sicurezza in modo diverso, l'accesso come amministratore nel dominio di Active Directory non concede implicitamente autorizzazioni per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="ca3e0-106">È inoltre necessario essere membri dell'entità sysadmin nel server basato su SQL Server che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="ca3e0-107">Autorizzazioni necessarie per l'installazione dei database e di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ca3e0-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="ca3e0-108">Le opzioni seguenti specificano tre autorizzazioni e associazioni di appartenenza a gruppi per l'installazione di file di Lync Server 2013 e database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="ca3e0-109">Scegliere lo scenario più adatto ai requisiti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="ca3e0-110">Associazioni di autorizzazioni e appartenenze ai gruppi</span><span class="sxs-lookup"><span data-stu-id="ca3e0-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca3e0-111">Ruolo SQL Server o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca3e0-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="ca3e0-112">Autorizzazioni e appartenenze ai gruppi di SQL Server tipiche del ruolo</span><span class="sxs-lookup"><span data-stu-id="ca3e0-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="ca3e0-113">Autorizzazioni di Lync Server 2013 e appartenenza a gruppi tipiche del ruolo</span><span class="sxs-lookup"><span data-stu-id="ca3e0-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="ca3e0-114">Risultati delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ca3e0-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca3e0-115">Amministratore di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca3e0-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-116">Deve appartenere al gruppo di sicurezza sysadmins di SQL Server ed essere membro del gruppo Administrators locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca3e0-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-117">Deve essere un membro del gruppo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ca3e0-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-118">L'amministratore di Lync Server 2013 dispone delle autorizzazioni appropriate per installare sia Lync Server 2013 che i database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e0-119">Amministratore di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca3e0-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-120">Membro del gruppo sysadmins di SQL Server (o equivalente) e membro del gruppo Administrators locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca3e0-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-121">Deve essere un membro del gruppo RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="ca3e0-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-122">L'amministratore di SQL Server dispone delle autorizzazioni appropriate per installare sia Lync Server 2013 che i database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e0-123">Entrambi gli amministratori condividono responsabilità per l'installazione</span><span class="sxs-lookup"><span data-stu-id="ca3e0-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-124">L'amministratore di SQL Server è membro del gruppo sysadmins (o equivalente) e membro del gruppo Administrarors locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca3e0-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-125">Lync Server 2013 Administrator è membro di RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ca3e0-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ca3e0-126">L'amministratore di Lync Server 2013 può installare Lync Server 2013, ma non è in grado di installare i database.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="ca3e0-127">L'amministratore di SQL Server utilizza i cmdlet di Lync Server Management Shell e Windows PowerShell forniti dall'amministratore di Lync Server 2013 per installare i database.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="ca3e0-128">Il Lync Server 2013 Management Shell utilizzato dall'amministratore di SQL Server viene installato nel front end server.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="ca3e0-129">In questo modo viene eliminata la necessità di installare gli strumenti di amministrazione di Lync Server 2013 nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca3e0-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

