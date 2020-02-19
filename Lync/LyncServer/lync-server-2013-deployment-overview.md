---
title: 'Lync Server 2013: Panoramica della distribuzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33328e124a1b444b4639b85bc6c1941c55f5ed1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="72d05-102">Panoramica della distribuzione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72d05-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72d05-103">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="72d05-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="72d05-104">La differenza principale tra Lync Server 2013 Enterprise Edition e Lync Server 2013 Standard Edition è che Standard Edition non supporta le funzionalità di disponibilità elevata incluse in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="72d05-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="72d05-105">Per la disponibilità elevata, è necessario distribuire più front end server in un pool e quindi è possibile eseguire il mirroring del server che esegue SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72d05-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="72d05-106">Con Enterprise Edition è possibile scegliere di collocare o definire un Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="72d05-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="72d05-107">Monitoring Server and Archiving Server può utilizzare un server autonomo che esegue SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72d05-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="72d05-108">In alternativa, possono disporre di istanze di SQL Server in esecuzione nel server di database per i pool Front end e i server.</span><span class="sxs-lookup"><span data-stu-id="72d05-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="72d05-109">I server che eseguono Lync Server 2013 Standard Edition sono progettati per organizzazioni di dimensioni ridotte e posizioni remote, che sono geograficamente rimosse dalla distribuzione principale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72d05-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="72d05-110">Due server Standard Edition in combinazione per il failover in caso di emergenza possono supportare fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="72d05-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="72d05-111">Non è possibile raggruppare i server Standard Edition come i front end server in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="72d05-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="72d05-112">Inoltre, il database di SQL Server utilizzato da Standard Edition è un server collocato che esegue SQL Server Express che è stato creato per gestire i carichi di lavoro del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72d05-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="72d05-113">Questo non significa che tutti i ruoli devono risiedere in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72d05-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="72d05-114">È possibile disporre di Mediation Server autonomi e server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="72d05-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="72d05-115">Il database di SQL Server per l'archivio di gestione centrale e ai fini di Lync Server 2013 deve risiedere nel server Standard Edition collocato con il server che esegue SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72d05-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="72d05-116">Il server di monitoraggio e il server di archiviazione utilizzano un server autonomo con il database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72d05-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

