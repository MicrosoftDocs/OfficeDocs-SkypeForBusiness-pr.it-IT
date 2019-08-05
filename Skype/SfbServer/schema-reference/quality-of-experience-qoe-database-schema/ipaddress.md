---
title: Tabella IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194616"
---
# <a name="ipaddress-table"></a><span data-ttu-id="8a360-104">Tabella IPAddress</span><span class="sxs-lookup"><span data-stu-id="8a360-104">IPAddress table</span></span>
 
<span data-ttu-id="8a360-105">La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="8a360-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="8a360-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a360-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8a360-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8a360-107">**Column**</span></span>|<span data-ttu-id="8a360-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="8a360-108">**Data Type**</span></span>|<span data-ttu-id="8a360-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="8a360-109">**Key/Index**</span></span>|<span data-ttu-id="8a360-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="8a360-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8a360-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="8a360-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="8a360-112">int</span><span class="sxs-lookup"><span data-stu-id="8a360-112">int</span></span>  <br/> |<span data-ttu-id="8a360-113">Principale</span><span class="sxs-lookup"><span data-stu-id="8a360-113">Primary</span></span>  <br/> |<span data-ttu-id="8a360-114">Identificatore univoco per l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="8a360-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="8a360-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="8a360-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="8a360-116">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="8a360-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="8a360-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="8a360-117">Unique</span></span>  <br/> |<span data-ttu-id="8a360-118">Indirizzo IP univoco, ad esempio 189.168.1.1, che esegue il mapping a IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="8a360-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="8a360-119">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="8a360-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

