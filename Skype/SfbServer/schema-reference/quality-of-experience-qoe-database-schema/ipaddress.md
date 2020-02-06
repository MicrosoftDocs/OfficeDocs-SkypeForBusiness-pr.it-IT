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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809544"
---
# <a name="ipaddress-table"></a><span data-ttu-id="3c85a-104">Tabella IPAddress</span><span class="sxs-lookup"><span data-stu-id="3c85a-104">IPAddress table</span></span>
 
<span data-ttu-id="3c85a-105">La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="3c85a-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3c85a-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c85a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3c85a-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3c85a-107">**Column**</span></span>|<span data-ttu-id="3c85a-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="3c85a-108">**Data Type**</span></span>|<span data-ttu-id="3c85a-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="3c85a-109">**Key/Index**</span></span>|<span data-ttu-id="3c85a-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3c85a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3c85a-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3c85a-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3c85a-112">int</span><span class="sxs-lookup"><span data-stu-id="3c85a-112">int</span></span>  <br/> |<span data-ttu-id="3c85a-113">Principale</span><span class="sxs-lookup"><span data-stu-id="3c85a-113">Primary</span></span>  <br/> |<span data-ttu-id="3c85a-114">Identificatore univoco per l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="3c85a-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="3c85a-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="3c85a-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="3c85a-116">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="3c85a-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="3c85a-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="3c85a-117">Unique</span></span>  <br/> |<span data-ttu-id="3c85a-118">Indirizzo IP univoco, ad esempio 189.168.1.1, che esegue il mapping a IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="3c85a-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="3c85a-119">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="3c85a-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

