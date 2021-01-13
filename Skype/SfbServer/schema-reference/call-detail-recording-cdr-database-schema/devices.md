---
title: Tabella Devices in Skype for Business Server 2015
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831816"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c733c-104">Tabella Devices in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c733c-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c733c-105">La tabella Devices è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="c733c-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="c733c-106">In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="c733c-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="c733c-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c733c-107">**Column**</span></span>|<span data-ttu-id="c733c-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="c733c-108">**Data Type**</span></span>|<span data-ttu-id="c733c-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="c733c-109">**Key/Index**</span></span>|<span data-ttu-id="c733c-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c733c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c733c-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="c733c-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="c733c-112">int</span><span class="sxs-lookup"><span data-stu-id="c733c-112">int</span></span>  <br/> |<span data-ttu-id="c733c-113">Principale</span><span class="sxs-lookup"><span data-stu-id="c733c-113">Primary</span></span>  <br/> |<span data-ttu-id="c733c-114">Numero univoco che identifica questa versione hardware.</span><span class="sxs-lookup"><span data-stu-id="c733c-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="c733c-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="c733c-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="c733c-116">int</span><span class="sxs-lookup"><span data-stu-id="c733c-116">int</span></span>  <br/> |<span data-ttu-id="c733c-117">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c733c-117">Foreign</span></span>  <br/> |<span data-ttu-id="c733c-118">Produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c733c-118">Manufacturer of this device.</span></span> <span data-ttu-id="c733c-119">Per ulteriori informazioni, vedere la [tabella Manufacturers in Skype for Business Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="c733c-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c733c-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="c733c-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="c733c-121">int</span><span class="sxs-lookup"><span data-stu-id="c733c-121">int</span></span>  <br/> |<span data-ttu-id="c733c-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c733c-122">Foreign</span></span>  <br/> |<span data-ttu-id="c733c-123">Versione hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c733c-123">Hardware version of this device.</span></span> <span data-ttu-id="c733c-124">Per ulteriori informazioni, vedere la [tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="c733c-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c733c-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="c733c-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="c733c-126">bigint</span><span class="sxs-lookup"><span data-stu-id="c733c-126">bigint</span></span>  <br/> ||<span data-ttu-id="c733c-127">Indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="c733c-127">MAC Address</span></span>  <br/> |
   

