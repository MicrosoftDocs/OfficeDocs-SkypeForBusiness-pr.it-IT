---
title: Tabella Device
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814746"
---
# <a name="device-table"></a><span data-ttu-id="a3dd7-104">Tabella Device</span><span class="sxs-lookup"><span data-stu-id="a3dd7-104">Device table</span></span>
 
<span data-ttu-id="a3dd7-105">La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering.</span><span class="sxs-lookup"><span data-stu-id="a3dd7-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="a3dd7-106">Ogni record nella tabella rappresenta un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3dd7-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="a3dd7-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-107">**Column**</span></span>|<span data-ttu-id="a3dd7-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-108">**Data Type**</span></span>|<span data-ttu-id="a3dd7-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-109">**Key/Index**</span></span>|<span data-ttu-id="a3dd7-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3dd7-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="a3dd7-112">int</span><span class="sxs-lookup"><span data-stu-id="a3dd7-112">int</span></span>  <br/> |<span data-ttu-id="a3dd7-113">Principale</span><span class="sxs-lookup"><span data-stu-id="a3dd7-113">Primary</span></span>  <br/> |<span data-ttu-id="a3dd7-114">Numero univoco che identifica il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3dd7-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="a3dd7-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="a3dd7-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3dd7-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a3dd7-117">DeviceName + DeviceType è univoco</span><span class="sxs-lookup"><span data-stu-id="a3dd7-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="a3dd7-118">Nome del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3dd7-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="a3dd7-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="a3dd7-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="a3dd7-120">po'</span><span class="sxs-lookup"><span data-stu-id="a3dd7-120">bit</span></span>  <br/> |<span data-ttu-id="a3dd7-121">DeviceName + DeviceType è univoco</span><span class="sxs-lookup"><span data-stu-id="a3dd7-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="a3dd7-122">Tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3dd7-122">Device type.</span></span> <span data-ttu-id="a3dd7-123">1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.</span><span class="sxs-lookup"><span data-stu-id="a3dd7-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

