---
title: Schema del database di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Questo documenta lo schema del database della chat persistente in Skype for Business Server.
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814744"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="10eea-103">Schema del database di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="10eea-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="10eea-104">Questo documenta lo schema del database della chat persistente in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="10eea-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="10eea-105">Il database della chat persistente si riferisce al database corrispondente ai ruoli del server back-end di Skype for Business Server **PersistentChatStore** (corrispondente al database di MGC) e **PersistentChatComplianceStore** (corrispondente al database di mgccomp).</span><span class="sxs-lookup"><span data-stu-id="10eea-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="10eea-106">L'obiettivo della pubblicazione di questo schema è quello di consentire la creazione di query e acquisire alcune informazioni utili per la creazione di una segnalazione utile intorno all'utilizzo della chat, alle sale attive, ai poster principali e così via.</span><span class="sxs-lookup"><span data-stu-id="10eea-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="10eea-107">Ci riserviamo il diritto di evolvere questo schema.</span><span class="sxs-lookup"><span data-stu-id="10eea-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="10eea-108">Microsoft non garantisce di mantenere la compatibilità completa con questo schema pubblicato.</span><span class="sxs-lookup"><span data-stu-id="10eea-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="10eea-109">Seguire queste procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="10eea-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="10eea-110">Nessun SELECT\* //è supportato perché l'elenco di colonne può aumentare.</span><span class="sxs-lookup"><span data-stu-id="10eea-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="10eea-111">Non sono supportate modifiche allo schema generate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="10eea-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="10eea-112">Non sono supportate operazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="10eea-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="10eea-113">Testare le query che si compilano su database di dimensioni rappresentative per verificare che le query possano essere eseguite a un livello per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="10eea-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="10eea-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="10eea-114">In this section</span></span>

- [<span data-ttu-id="10eea-115">Elenco di tabelle del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="10eea-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="10eea-116">Elenco delle tabelle di conformità Persistent Chat Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10eea-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="10eea-117">Dettagli delle tabelle di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="10eea-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="10eea-118">Query del database Chat persistente di esempio</span><span class="sxs-lookup"><span data-stu-id="10eea-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

