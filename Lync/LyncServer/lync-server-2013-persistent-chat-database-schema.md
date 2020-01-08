---
title: 'Lync Server 2013: Schema del database di Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="d9862-102">Schema del database di Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9862-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9862-103">_**Argomento Ultima modifica:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="d9862-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="d9862-104">Questo documento documenta lo schema del database di chat persistente nel software di comunicazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9862-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="d9862-105">Il database della chat persistente fa riferimento al database corrispondente ai ruoli di Lync Server 2013 back-end server **PersistentChatStore** (corrispondente al database mgc) e **PersistentChatComplianceStore** (corrispondente al database mgccomp).</span><span class="sxs-lookup"><span data-stu-id="d9862-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="d9862-106">L'obiettivo della pubblicazione di questo schema è quello di consentire la creazione di query e acquisire alcune informazioni utili per la creazione di una segnalazione utile intorno all'utilizzo della chat, alle sale attive, ai poster principali e così via.</span><span class="sxs-lookup"><span data-stu-id="d9862-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9862-107">Ci riserviamo il diritto di evolvere questo schema.</span><span class="sxs-lookup"><span data-stu-id="d9862-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="d9862-108">Microsoft non garantisce di mantenere la compatibilità completa con questo schema pubblicato.</span><span class="sxs-lookup"><span data-stu-id="d9862-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="d9862-109">Seguire queste procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="d9862-109">Follow these best practices:</span></span>

  - <span data-ttu-id="d9862-110">Nessun SELECT\* //è supportato perché l'elenco di colonne può aumentare.</span><span class="sxs-lookup"><span data-stu-id="d9862-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="d9862-111">Non sono supportate modifiche allo schema generate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d9862-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="d9862-112">Non sono supportate operazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="d9862-112">No write operations are supported.</span></span>

  - <span data-ttu-id="d9862-113">Testare le query che si compilano su database di dimensioni rappresentative per verificare che le query possano essere eseguite a un livello per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="d9862-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9862-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d9862-114">In This Section</span></span>

  - [<span data-ttu-id="d9862-115">Elenco delle tabelle del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9862-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="d9862-116">Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9862-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="d9862-117">Dettagli sulle tabelle del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9862-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="d9862-118">Query del database di Chat persistente di esempio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9862-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

