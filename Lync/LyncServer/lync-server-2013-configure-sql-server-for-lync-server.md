---
title: 'Lync Server 2013: configurare SQL Server per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435fad8ff60a25b897eff91416e2809a6e2284f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="5fcbf-102">Configurare SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fcbf-103">_**Ultimo argomento modificato:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="5fcbf-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="5fcbf-104">Negli argomenti di questa sezione viene illustrato come distribuire e configurare SQL Server per l'utilizzo in una distribuzione aziendale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="5fcbf-105">I server Standard Edition utilizzano una versione di SQL Server Express collocata di SQL Server di dimensioni adeguate per i carichi di lavoro di un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="5fcbf-106">L'archivio di gestione centrale di Lync Server 2013 contiene i dati utente per tutti i server Enterprise Edition all'interno di un pool ed è stato creato per essere posizionato su un server back-end basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="5fcbf-107">Poiché si tratta di un archivio centralizzato, l'archivio di gestione centrale non può essere installato nello stesso computer di qualsiasi altro ruolo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="5fcbf-108">L'archivio di gestione centrale non può trovarsi in un server Enterprise Edition del pool.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="5fcbf-109">L'archivio di gestione centrale viene creato automaticamente quando si pubblica la topologia per la prima volta e si sceglie di creare i database.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="5fcbf-110">Il computer che si desidera definire come server back-end deve già eseguire il software di database di SQL Server in modo che l'installazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5fcbf-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5fcbf-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="5fcbf-111">In This Section</span></span>

  - [<span data-ttu-id="5fcbf-112">Disposizione dei file di registro e di dati di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="5fcbf-113">Configurare SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="5fcbf-114">Autorizzazioni di distribuzione per SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="5fcbf-115">Installazione di database mediante Lync Server Management Shell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="5fcbf-116">Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="5fcbf-117">Configurare il clustering di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcbf-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

