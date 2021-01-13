---
title: Tabella IPAddress
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabella IPAddress mappa gli indirizzi IP agli identificatori di indirizzo IP univoci usati altrove nel database QoS (Quality of Experience). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802776"
---
# <a name="ipaddress-table"></a><span data-ttu-id="a218a-104">Tabella IPAddress</span><span class="sxs-lookup"><span data-stu-id="a218a-104">IPAddress table</span></span>
 
<span data-ttu-id="a218a-105">La tabella IPAddress mappa gli indirizzi IP agli identificatori di indirizzo IP univoci usati altrove nel database QoS (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="a218a-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a218a-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a218a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a218a-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a218a-107">**Column**</span></span>|<span data-ttu-id="a218a-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a218a-108">**Data Type**</span></span>|<span data-ttu-id="a218a-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="a218a-109">**Key/Index**</span></span>|<span data-ttu-id="a218a-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a218a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a218a-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="a218a-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="a218a-112">int</span><span class="sxs-lookup"><span data-stu-id="a218a-112">int</span></span>  <br/> |<span data-ttu-id="a218a-113">Principale</span><span class="sxs-lookup"><span data-stu-id="a218a-113">Primary</span></span>  <br/> |<span data-ttu-id="a218a-114">Identificatore univoco per l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="a218a-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="a218a-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="a218a-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="a218a-116">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="a218a-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="a218a-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="a218a-117">Unique</span></span>  <br/> |<span data-ttu-id="a218a-p103">Indirizzo IP univoco (ad esempio, 189.168.1.1) mappato a IpAddressKey. Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="a218a-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

