---
title: 'Lync Server 2013: Requisiti relativi a IIS (Internet Information Services)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="080af-102">Requisiti relativi a IIS (Internet Information Services) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="080af-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="080af-103">_**Argomento Ultima modifica:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="080af-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="080af-104">Diversi componenti di Lync Server 2013 richiedono Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="080af-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="080af-105">In questo argomento vengono illustrate le caratteristiche specifiche di IIS necessarie per supportare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="080af-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="080af-106">Gli argomenti in questa sezione descrivono i requisiti di componenti specifici per IIS.</span><span class="sxs-lookup"><span data-stu-id="080af-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="080af-107">Quando il ruolo del server Web (IIS) è abilitato in Windows Server 2008, per impostazione predefinita vengono installati vari servizi di ruolo.</span><span class="sxs-lookup"><span data-stu-id="080af-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="080af-108">La tabella seguente descrive i servizi ruolo aggiuntivi che devono essere installati quando il ruolo del server Web (IIS) è abilitato in Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="080af-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="080af-109">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="080af-109">Role service</span></span></th>
<th><span data-ttu-id="080af-110">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="080af-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="080af-111">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="080af-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="080af-112">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="080af-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080af-113">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="080af-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="080af-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="080af-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="080af-115">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="080af-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="080af-116">Estensibilità .NET</span><span class="sxs-lookup"><span data-stu-id="080af-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080af-117">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="080af-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="080af-118">Estensioni ISAPI</span><span class="sxs-lookup"><span data-stu-id="080af-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="080af-119">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="080af-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="080af-120">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="080af-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080af-121">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="080af-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="080af-122">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="080af-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="080af-123">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="080af-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="080af-124">Traccia</span><span class="sxs-lookup"><span data-stu-id="080af-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080af-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="080af-125">Security</span></span></p></td>
<td><p><span data-ttu-id="080af-126">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="080af-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="080af-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="080af-127">Security</span></span></p></td>
<td><p><span data-ttu-id="080af-128">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="080af-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080af-129">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="080af-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="080af-130">Script e strumenti di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="080af-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="080af-131">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="080af-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="080af-132">Compatibilità di gestione di IIS 6</span><span class="sxs-lookup"><span data-stu-id="080af-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="080af-134">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="080af-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="080af-135">Se si usa IIS 7,0 in un sistema operativo Windows Server 2008, il programma di installazione di Lync Server disabilita l'autenticazione in modalità kernel in IIS.</span><span class="sxs-lookup"><span data-stu-id="080af-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="080af-136">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="080af-136">In This Section</span></span>

  - [<span data-ttu-id="080af-137">Requisiti di IIS per pool Front End e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="080af-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

