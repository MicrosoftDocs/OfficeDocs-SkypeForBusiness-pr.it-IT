---
title: Tabella dispositivi in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabella dispositivi è una tabella di supporto. Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815284"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cbdaa-104">Tabella dispositivi in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cbdaa-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbdaa-105">La tabella dispositivi è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="cbdaa-106">Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="cbdaa-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="cbdaa-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-107">**Column**</span></span>|<span data-ttu-id="cbdaa-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-108">**Data Type**</span></span>|<span data-ttu-id="cbdaa-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-109">**Key/Index**</span></span>|<span data-ttu-id="cbdaa-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbdaa-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="cbdaa-112">int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-112">int</span></span>  <br/> |<span data-ttu-id="cbdaa-113">Principale</span><span class="sxs-lookup"><span data-stu-id="cbdaa-113">Primary</span></span>  <br/> |<span data-ttu-id="cbdaa-114">Numero univoco che identifica questa versione hardware.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="cbdaa-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="cbdaa-116">int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-116">int</span></span>  <br/> |<span data-ttu-id="cbdaa-117">Esterna</span><span class="sxs-lookup"><span data-stu-id="cbdaa-117">Foreign</span></span>  <br/> |<span data-ttu-id="cbdaa-118">Fabbricante di questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-118">Manufacturer of this device.</span></span> <span data-ttu-id="cbdaa-119">Per altre informazioni, vedere la [tabella produttori in Skype for Business Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="cbdaa-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cbdaa-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="cbdaa-121">int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-121">int</span></span>  <br/> |<span data-ttu-id="cbdaa-122">Esterna</span><span class="sxs-lookup"><span data-stu-id="cbdaa-122">Foreign</span></span>  <br/> |<span data-ttu-id="cbdaa-123">Versione hardware di questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-123">Hardware version of this device.</span></span> <span data-ttu-id="cbdaa-124">Per altre informazioni, vedere la [tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="cbdaa-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cbdaa-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="cbdaa-126">bigint</span><span class="sxs-lookup"><span data-stu-id="cbdaa-126">bigint</span></span>  <br/> ||<span data-ttu-id="cbdaa-127">Indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="cbdaa-127">MAC Address</span></span>  <br/> |
   

