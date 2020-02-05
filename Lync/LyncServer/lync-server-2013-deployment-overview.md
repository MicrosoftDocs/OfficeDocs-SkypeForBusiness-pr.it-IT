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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="afbc7-102">Panoramica della distribuzione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afbc7-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afbc7-103">_**Argomento Ultima modifica:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="afbc7-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="afbc7-104">La differenza principale tra Lync Server 2013 Enterprise Edition e Lync Server 2013 Standard Edition è che Standard Edition non supporta le caratteristiche di disponibilità elevata incluse in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="afbc7-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="afbc7-105">Per una disponibilità elevata, è necessario distribuire più server front-end in un pool e quindi è possibile eseguire il mirroring del server in cui è in uso SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afbc7-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="afbc7-106">Con Enterprise Edition è possibile scegliere di collocare o definire un Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="afbc7-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="afbc7-107">Il server di monitoraggio e l'archiviazione possono usare un server autonomo con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afbc7-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="afbc7-108">In alternativa, possono avere istanze di SQL Server in uso nel server di database per i pool e i server front-end.</span><span class="sxs-lookup"><span data-stu-id="afbc7-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="afbc7-109">I server che esegue Lync Server 2013 Standard Edition sono progettati per organizzazioni di piccole dimensioni e percorsi remoti, che vengono rimossi geograficamente dalla distribuzione principale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afbc7-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="afbc7-110">Due server standard in combinazione per il failover in caso di emergenza possono supportare fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="afbc7-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="afbc7-111">Non è possibile raggruppare i server standard di edizione come i server front-end in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="afbc7-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="afbc7-112">Inoltre, il database di SQL Server usato da Standard Edition è un server collocato con SQL Server Express progettato per gestire i carichi di lavoro del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="afbc7-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="afbc7-113">Questo non significa che tutti i ruoli debbano risiedere in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="afbc7-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="afbc7-114">Puoi avere Mediation Server e Edge Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="afbc7-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="afbc7-115">Il database di SQL Server per l'archivio di gestione centralizzato e per gli scopi di Lync Server 2013 deve risiedere nel server Standard Edition con il server in cui è in uso SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afbc7-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="afbc7-116">Il server di monitoraggio e l'archiviazione usano un server autonomo con il database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afbc7-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

