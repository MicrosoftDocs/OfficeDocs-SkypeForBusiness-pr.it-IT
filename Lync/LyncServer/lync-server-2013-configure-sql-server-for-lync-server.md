---
title: 'Lync Server 2013: Configurare SQL Server per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="c9115-102">Configurare SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9115-103">_**Argomento Ultima modifica:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="c9115-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="c9115-104">Gli argomenti di questa sezione illustrano come distribuire e configurare SQL Server per l'uso in una distribuzione aziendale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9115-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="c9115-105">I server Standard Edition usano una versione di SQL Server Express di SQL Server collocata di dimensioni adeguate per i carichi di lavoro di un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c9115-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="c9115-106">Lync Server 2013 Central Management store contiene i dati utente per tutti i server Enterprise Edition in un pool ed è progettato per essere posizionato in un server back-end basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9115-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="c9115-107">Come repository centralizzato, il Central Management store non può essere installato nello stesso computer di qualsiasi altro ruolo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9115-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="c9115-108">L'Central Management store non può risiedere in un server Enterprise Edition nel pool.</span><span class="sxs-lookup"><span data-stu-id="c9115-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="c9115-109">L'archivio di gestione centralizzato viene creato automaticamente quando si pubblica la topologia per la prima volta e si seleziona per creare i database.</span><span class="sxs-lookup"><span data-stu-id="c9115-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="c9115-110">Il computer designato come server back-end deve già eseguire il software di database di SQL Server in modo che l'installazione abbia successo.</span><span class="sxs-lookup"><span data-stu-id="c9115-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9115-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c9115-111">In This Section</span></span>

  - [<span data-ttu-id="c9115-112">Posizionamento dei file di log e dei file di dati di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="c9115-113">Configurare SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="c9115-114">Autorizzazioni di distribuzione per SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="c9115-115">Installazione di database mediante Lync Server Management Shell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="c9115-116">Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="c9115-117">Configurare il clustering di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9115-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

