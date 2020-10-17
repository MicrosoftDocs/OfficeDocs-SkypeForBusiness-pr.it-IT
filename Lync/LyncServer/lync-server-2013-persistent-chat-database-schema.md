---
title: 'Lync Server 2013: schema del database di chat persistente'
description: 'Lync Server 2013: schema del database di chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66151201f65310cc8e6d3f2251be4f86ce2be15d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545152"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="573ee-103">Schema del database di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="573ee-103">Persistent Chat database schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="573ee-104">_**Ultimo argomento modificato:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="573ee-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="573ee-105">In questo documento viene documentato lo schema del database di chat persistente in Lync Server 2013 Communications software.</span><span class="sxs-lookup"><span data-stu-id="573ee-105">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="573ee-106">Il database di Persistent Chat si riferisce al database corrispondente ai ruoli del server back-end di Lync Server 2013 **PersistentChatStore** (corrispondente al database di MGC) e **PersistentChatComplianceStore** (corrispondente al database di mgccomp).</span><span class="sxs-lookup"><span data-stu-id="573ee-106">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="573ee-107">L'obiettivo della pubblicazione di questo schema è di consentire la creazione di query per comprendere meglio come generare rapporti efficaci relativi all'uso della chat, alle chat attive, agli autori di post più attivi e così via.</span><span class="sxs-lookup"><span data-stu-id="573ee-107">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="573ee-p102">Ci riserviamo il diritto di modificare questo schema. Microsoft non garantisce di poter mantenere la completa compatibilità di questo schema pubblicato con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="573ee-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="573ee-110">Tenere presenti queste procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="573ee-110">Follow these best practices:</span></span>

  - <span data-ttu-id="573ee-111">Nessuna selezione \* //è supportata perché l'elenco di colonne può aumentare.</span><span class="sxs-lookup"><span data-stu-id="573ee-111">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="573ee-112">Non sono supportate modifiche allo schema generate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="573ee-112">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="573ee-113">Non sono supportate operazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="573ee-113">No write operations are supported.</span></span>

  - <span data-ttu-id="573ee-114">Testare le query create con database di dimensioni rappresentative, per assicurarsi che le prestazioni soddisfino le esigenze.</span><span class="sxs-lookup"><span data-stu-id="573ee-114">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="573ee-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="573ee-115">In This Section</span></span>

  - [<span data-ttu-id="573ee-116">Elenco delle tabelle del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="573ee-116">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="573ee-117">Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="573ee-117">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="573ee-118">Dettagli della tabella del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="573ee-118">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="573ee-119">Query del database di chat persistente di esempio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="573ee-119">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

