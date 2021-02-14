---
title: Tabella NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806306"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="c2355-104">Tabella NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="c2355-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="c2355-105">Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="c2355-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="c2355-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2355-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c2355-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c2355-107">**Column**</span></span>|<span data-ttu-id="c2355-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="c2355-108">**Data Type**</span></span>|<span data-ttu-id="c2355-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="c2355-109">**Key/Index**</span></span>|<span data-ttu-id="c2355-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c2355-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2355-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="c2355-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="c2355-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2355-112">tinyint</span></span>  <br/> |<span data-ttu-id="c2355-113">Principale</span><span class="sxs-lookup"><span data-stu-id="c2355-113">Primary</span></span>  <br/> |<span data-ttu-id="c2355-114">Identificatore univoco del tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="c2355-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="c2355-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="c2355-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="c2355-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2355-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="c2355-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="c2355-117">Unique</span></span>  <br/> |<span data-ttu-id="c2355-p103">Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="c2355-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="c2355-120">0 - Cablata</span><span class="sxs-lookup"><span data-stu-id="c2355-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="c2355-121">1 - Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c2355-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="c2355-122">2 - Ethernet</span><span class="sxs-lookup"><span data-stu-id="c2355-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="c2355-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="c2355-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="c2355-124">4 -- Altro</span><span class="sxs-lookup"><span data-stu-id="c2355-124">4 -- Other</span></span>  <br/> <span data-ttu-id="c2355-125">5 - Tunnel</span><span class="sxs-lookup"><span data-stu-id="c2355-125">5 -- Tunnel</span></span>  <br/> |
   

