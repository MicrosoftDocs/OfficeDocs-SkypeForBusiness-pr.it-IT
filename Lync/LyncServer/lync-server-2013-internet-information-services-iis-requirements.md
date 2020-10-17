---
title: 'Lync Server 2013: requisiti di Internet Information Services (IIS)'
description: 'Lync Server 2013: requisiti di Internet Information Services (IIS).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543992"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="139ba-103">Requisiti di Internet Information Services (IIS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="139ba-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="139ba-104">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="139ba-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="139ba-105">Diversi componenti di Lync Server 2013 richiedono Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="139ba-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="139ba-106">In questo argomento vengono descritte le caratteristiche di IIS specifiche necessarie per il supporto di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="139ba-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="139ba-107">Negli argomenti di questa sezione vengono descritti i requisiti per i componenti specifici di IIS.</span><span class="sxs-lookup"><span data-stu-id="139ba-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="139ba-108">Quando il ruolo server Web (IIS) è abilitato su Windows Server 2008, per impostazione predefinita vengono installati vari servizi ruolo.</span><span class="sxs-lookup"><span data-stu-id="139ba-108">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="139ba-109">Nella tabella seguente vengono descritti i servizi ruolo aggiuntivi che devono essere installati quando il ruolo server Web (IIS) è abilitato su Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="139ba-109">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="139ba-110">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="139ba-110">Role service</span></span></th>
<th><span data-ttu-id="139ba-111">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="139ba-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="139ba-112">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="139ba-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="139ba-113">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="139ba-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="139ba-114">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="139ba-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="139ba-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="139ba-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="139ba-116">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="139ba-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="139ba-117">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="139ba-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="139ba-118">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="139ba-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="139ba-119">Estensioni ISAPI</span><span class="sxs-lookup"><span data-stu-id="139ba-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="139ba-120">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="139ba-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="139ba-121">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="139ba-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="139ba-122">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="139ba-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="139ba-123">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="139ba-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="139ba-124">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="139ba-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="139ba-125">Analisi della</span><span class="sxs-lookup"><span data-stu-id="139ba-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="139ba-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="139ba-126">Security</span></span></p></td>
<td><p><span data-ttu-id="139ba-127">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="139ba-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="139ba-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="139ba-128">Security</span></span></p></td>
<td><p><span data-ttu-id="139ba-129">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="139ba-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="139ba-130">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="139ba-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="139ba-131">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="139ba-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="139ba-132">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="139ba-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="139ba-133">Compatibilità gestione IIS 6</span><span class="sxs-lookup"><span data-stu-id="139ba-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="139ba-135">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="139ba-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="139ba-136">Se si utilizza IIS 7,0 in un sistema operativo Windows Server 2008, il programma di installazione di Lync Server disattiva l'autenticazione in modalità kernel in IIS.</span><span class="sxs-lookup"><span data-stu-id="139ba-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="139ba-137">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="139ba-137">In This Section</span></span>

  - [<span data-ttu-id="139ba-138">Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="139ba-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

