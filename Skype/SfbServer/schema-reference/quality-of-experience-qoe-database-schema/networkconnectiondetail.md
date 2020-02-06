---
title: Tabella NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807504"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="943dd-104">Tabella NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="943dd-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="943dd-105">La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="943dd-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="943dd-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="943dd-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="943dd-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="943dd-107">**Column**</span></span>|<span data-ttu-id="943dd-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="943dd-108">**Data Type**</span></span>|<span data-ttu-id="943dd-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="943dd-109">**Key/Index**</span></span>|<span data-ttu-id="943dd-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="943dd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="943dd-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="943dd-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="943dd-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="943dd-112">tinyint</span></span>  <br/> |<span data-ttu-id="943dd-113">Principale</span><span class="sxs-lookup"><span data-stu-id="943dd-113">Primary</span></span>  <br/> |<span data-ttu-id="943dd-114">Identificatore univoco per il tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="943dd-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="943dd-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="943dd-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="943dd-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="943dd-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="943dd-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="943dd-117">Unique</span></span>  <br/> |<span data-ttu-id="943dd-118">Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="943dd-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="943dd-119">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="943dd-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="943dd-120">0--Wired</span><span class="sxs-lookup"><span data-stu-id="943dd-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="943dd-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="943dd-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="943dd-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="943dd-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="943dd-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="943dd-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="943dd-124">4--altro</span><span class="sxs-lookup"><span data-stu-id="943dd-124">4 -- Other</span></span>  <br/> <span data-ttu-id="943dd-125">5--tunnel</span><span class="sxs-lookup"><span data-stu-id="943dd-125">5 -- Tunnel</span></span>  <br/> |
   

