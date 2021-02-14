---
title: Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813056"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="80936-103">Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80936-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="80936-104">Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="80936-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="80936-105">Elenco delle tabelle di conformità del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="80936-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="80936-106">**tavolo**</span><span class="sxs-lookup"><span data-stu-id="80936-106">**Table**</span></span>|<span data-ttu-id="80936-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="80936-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="80936-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="80936-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="80936-109">Include gli eventi di conformità ancora non elaborati da tutti gli adattatori configurati.</span><span class="sxs-lookup"><span data-stu-id="80936-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="80936-110">Questa tabella include eventi correlati a Persistent Chat, ad esempio messaggi di chat e download di file.</span><span class="sxs-lookup"><span data-stu-id="80936-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="80936-111">Gli eventi dei partecipanti vengono registrati dalla tabella ComplianceParticipant.</span><span class="sxs-lookup"><span data-stu-id="80936-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="80936-112">I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella ComplianceFanout.</span><span class="sxs-lookup"><span data-stu-id="80936-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="80936-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="80936-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="80936-114">Include i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="80936-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="80936-115">È strettamente associata alla tabella ComplianceData.</span><span class="sxs-lookup"><span data-stu-id="80936-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="80936-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="80936-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="80936-117">Include i partecipanti correnti per servizio chat e per server.</span><span class="sxs-lookup"><span data-stu-id="80936-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="80936-118">Viene gestito in base agli eventi di conformità di parte e di partecipazione ricevuti dal servizio Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="80936-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="80936-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="80936-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="80936-120">Contiene informazioni relative allo stato di conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="80936-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

