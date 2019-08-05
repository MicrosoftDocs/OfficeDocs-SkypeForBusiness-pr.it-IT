---
title: Elenco delle tabelle di conformità Persistent Chat Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Lo schema del database di conformità della chat persistente è costituito dalle tabelle seguenti.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194716"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="236d0-103">Elenco delle tabelle di conformità Persistent Chat Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="236d0-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="236d0-104">Lo schema del database di conformità della chat persistente è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="236d0-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="236d0-105">Elenco delle tabelle di conformità Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="236d0-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="236d0-106">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="236d0-106">**Table**</span></span>|<span data-ttu-id="236d0-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="236d0-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="236d0-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="236d0-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="236d0-109">Contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda configurata.</span><span class="sxs-lookup"><span data-stu-id="236d0-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="236d0-110">Questa tabella include eventi relativi alla chat persistente, ad esempio messaggi di chat e download di file.</span><span class="sxs-lookup"><span data-stu-id="236d0-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="236d0-111">(Gli eventi dei partecipanti vengono registrati dalla tabella tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="236d0-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="236d0-112">I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella tblComplianceFanout.</span><span class="sxs-lookup"><span data-stu-id="236d0-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="236d0-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="236d0-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="236d0-114">Contiene i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="236d0-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="236d0-115">Questa tabella è strettamente associata alla tabella tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="236d0-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="236d0-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="236d0-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="236d0-117">Contiene partecipanti correnti per servizio di chat e per server.</span><span class="sxs-lookup"><span data-stu-id="236d0-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="236d0-118">Viene mantenuto in base agli eventi di conformità di join e part ricevuti dal servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="236d0-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="236d0-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="236d0-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="236d0-120">Contiene informazioni sullo stato di conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="236d0-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

