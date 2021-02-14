---
title: Schema del database Chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Questo documento documenta lo schema del database di Persistent Chat in Skype for Business Server.
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809876"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="c211d-103">Schema del database Chat persistente</span><span class="sxs-lookup"><span data-stu-id="c211d-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="c211d-104">Questo documento documenta lo schema del database di Persistent Chat in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c211d-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="c211d-105">Il database di Persistent Chat fa riferimento al database corrispondente ai ruoli **PersistentChatStore** (corrispondente al database mgc) e **PersistentChatComplianceStore** (corrispondente al database mgccomp) di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c211d-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="c211d-106">L'obiettivo della pubblicazione di questo schema è di consentire la creazione di query per comprendere meglio come generare rapporti efficaci relativi all'uso della chat, alle chat attive, agli autori di post più attivi e così via.</span><span class="sxs-lookup"><span data-stu-id="c211d-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c211d-p102">Ci riserviamo il diritto di modificare questo schema. Microsoft non garantisce di poter mantenere la completa compatibilità di questo schema pubblicato con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c211d-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="c211d-109">Tenere presenti queste procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="c211d-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="c211d-110">L'istruzione SELECT \* // non è supportata perché l'elenco di colonne può aumentare.</span><span class="sxs-lookup"><span data-stu-id="c211d-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="c211d-111">Non sono supportate modifiche allo schema generate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c211d-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="c211d-112">Non sono supportate operazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="c211d-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="c211d-113">Testare le query create con database di dimensioni rappresentative, per assicurarsi che le prestazioni soddisfino le esigenze.</span><span class="sxs-lookup"><span data-stu-id="c211d-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="c211d-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c211d-114">In this section</span></span>

- [<span data-ttu-id="c211d-115">Elenco di tabelle del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="c211d-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="c211d-116">Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c211d-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="c211d-117">Dettagli delle tabelle di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="c211d-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="c211d-118">Query del database Chat persistente di esempio</span><span class="sxs-lookup"><span data-stu-id="c211d-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

