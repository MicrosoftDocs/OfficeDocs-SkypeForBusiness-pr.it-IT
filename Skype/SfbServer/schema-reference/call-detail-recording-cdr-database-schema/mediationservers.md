---
title: Tabella MediationServers
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
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: La tabella MediationServers è una tabella di supporto. In ogni record vengono archiviate informazioni su un Mediation Server coinvolto nelle chiamate con record nel database.
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814766"
---
# <a name="mediationservers-table"></a><span data-ttu-id="84b5e-104">Tabella MediationServers</span><span class="sxs-lookup"><span data-stu-id="84b5e-104">MediationServers table</span></span>
 
<span data-ttu-id="84b5e-105">La tabella MediationServers è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="84b5e-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="84b5e-106">In ogni record vengono archiviate informazioni su un Mediation Server coinvolto nelle chiamate con record nel database.</span><span class="sxs-lookup"><span data-stu-id="84b5e-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="84b5e-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="84b5e-107">**Column**</span></span>|<span data-ttu-id="84b5e-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="84b5e-108">**Data Type**</span></span>|<span data-ttu-id="84b5e-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="84b5e-109">**Key/Index**</span></span>|<span data-ttu-id="84b5e-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="84b5e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84b5e-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="84b5e-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="84b5e-112">int</span><span class="sxs-lookup"><span data-stu-id="84b5e-112">int</span></span>  <br/> |<span data-ttu-id="84b5e-113">Principale</span><span class="sxs-lookup"><span data-stu-id="84b5e-113">Primary</span></span>  <br/> |<span data-ttu-id="84b5e-114">Numero univoco che identifica il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="84b5e-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="84b5e-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="84b5e-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="84b5e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="84b5e-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="84b5e-117">Nome mediation server.</span><span class="sxs-lookup"><span data-stu-id="84b5e-117">Mediation Server name.</span></span>  <br/> |
   

