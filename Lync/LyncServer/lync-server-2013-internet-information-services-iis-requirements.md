---
title: 'Lync Server 2013: requisiti di Internet Information Services (IIS)'
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
ms.openlocfilehash: 9a086713c4c4c1ea5752c7e1b46ce46e48a0ea42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="d6d67-102">Requisiti di Internet Information Services (IIS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6d67-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d67-103">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d6d67-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d6d67-104">Diversi componenti di Lync Server 2013 richiedono Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d6d67-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="d6d67-105">In questo argomento vengono descritte le caratteristiche di IIS specifiche necessarie per il supporto di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6d67-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="d6d67-106">Negli argomenti di questa sezione vengono descritti i requisiti per i componenti specifici di IIS.</span><span class="sxs-lookup"><span data-stu-id="d6d67-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="d6d67-107">Quando il ruolo server Web (IIS) è abilitato su Windows Server 2008, per impostazione predefinita vengono installati vari servizi ruolo.</span><span class="sxs-lookup"><span data-stu-id="d6d67-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="d6d67-108">Nella tabella seguente vengono descritti i servizi ruolo aggiuntivi che devono essere installati quando il ruolo server Web (IIS) è abilitato su Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d6d67-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d67-109">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="d6d67-109">Role service</span></span></th>
<th><span data-ttu-id="d6d67-110">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="d6d67-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d67-111">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="d6d67-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d6d67-112">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="d6d67-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d67-113">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="d6d67-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d6d67-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d6d67-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d67-115">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="d6d67-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d6d67-116">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="d6d67-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d67-117">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="d6d67-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d6d67-118">Estensioni ISAPI</span><span class="sxs-lookup"><span data-stu-id="d6d67-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d67-119">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="d6d67-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d6d67-120">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="d6d67-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d67-121">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d6d67-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d6d67-122">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="d6d67-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d67-123">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d6d67-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d6d67-124">Analisi della</span><span class="sxs-lookup"><span data-stu-id="d6d67-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d67-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6d67-125">Security</span></span></p></td>
<td><p><span data-ttu-id="d6d67-126">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="d6d67-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d67-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6d67-127">Security</span></span></p></td>
<td><p><span data-ttu-id="d6d67-128">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="d6d67-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d67-129">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="d6d67-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d6d67-130">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="d6d67-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d67-131">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="d6d67-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d6d67-132">Compatibilità gestione IIS 6</span><span class="sxs-lookup"><span data-stu-id="d6d67-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="d6d67-134">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="d6d67-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d6d67-135">Se si utilizza IIS 7,0 in un sistema operativo Windows Server 2008, il programma di installazione di Lync Server disattiva l'autenticazione in modalità kernel in IIS.</span><span class="sxs-lookup"><span data-stu-id="d6d67-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6d67-136">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d6d67-136">In This Section</span></span>

  - [<span data-ttu-id="d6d67-137">Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6d67-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

