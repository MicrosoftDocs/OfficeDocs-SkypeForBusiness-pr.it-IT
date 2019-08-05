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
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194600"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="092d4-104">Tabella NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="092d4-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="092d4-105">La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="092d4-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="092d4-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="092d4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="092d4-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="092d4-107">**Column**</span></span>|<span data-ttu-id="092d4-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="092d4-108">**Data Type**</span></span>|<span data-ttu-id="092d4-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="092d4-109">**Key/Index**</span></span>|<span data-ttu-id="092d4-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="092d4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="092d4-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="092d4-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="092d4-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="092d4-112">tinyint</span></span>  <br/> |<span data-ttu-id="092d4-113">Principale</span><span class="sxs-lookup"><span data-stu-id="092d4-113">Primary</span></span>  <br/> |<span data-ttu-id="092d4-114">Identificatore univoco per il tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="092d4-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="092d4-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="092d4-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="092d4-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="092d4-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="092d4-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="092d4-117">Unique</span></span>  <br/> |<span data-ttu-id="092d4-118">Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="092d4-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="092d4-119">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="092d4-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="092d4-120">0--Wired</span><span class="sxs-lookup"><span data-stu-id="092d4-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="092d4-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="092d4-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="092d4-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="092d4-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="092d4-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="092d4-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="092d4-124">4--altro</span><span class="sxs-lookup"><span data-stu-id="092d4-124">4 -- Other</span></span>  <br/> <span data-ttu-id="092d4-125">5--tunnel</span><span class="sxs-lookup"><span data-stu-id="092d4-125">5 -- Tunnel</span></span>  <br/> |
   

