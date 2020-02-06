---
title: Tabella Device
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810154"
---
# <a name="device-table"></a><span data-ttu-id="975c4-104">Tabella Device</span><span class="sxs-lookup"><span data-stu-id="975c4-104">Device table</span></span>
 
<span data-ttu-id="975c4-105">La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering.</span><span class="sxs-lookup"><span data-stu-id="975c4-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="975c4-106">Ogni record nella tabella rappresenta un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="975c4-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="975c4-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="975c4-107">**Column**</span></span>|<span data-ttu-id="975c4-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="975c4-108">**Data Type**</span></span>|<span data-ttu-id="975c4-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="975c4-109">**Key/Index**</span></span>|<span data-ttu-id="975c4-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="975c4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="975c4-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="975c4-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="975c4-112">int</span><span class="sxs-lookup"><span data-stu-id="975c4-112">int</span></span>  <br/> |<span data-ttu-id="975c4-113">Principale</span><span class="sxs-lookup"><span data-stu-id="975c4-113">Primary</span></span>  <br/> |<span data-ttu-id="975c4-114">Numero univoco che identifica questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="975c4-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="975c4-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="975c4-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="975c4-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="975c4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="975c4-117">DeviceName + DeviceType è univoco</span><span class="sxs-lookup"><span data-stu-id="975c4-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="975c4-118">Nome dispositivo.</span><span class="sxs-lookup"><span data-stu-id="975c4-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="975c4-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="975c4-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="975c4-120">po'</span><span class="sxs-lookup"><span data-stu-id="975c4-120">bit</span></span>  <br/> |<span data-ttu-id="975c4-121">DeviceName + DeviceType è univoco</span><span class="sxs-lookup"><span data-stu-id="975c4-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="975c4-122">Tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="975c4-122">Device type.</span></span> <span data-ttu-id="975c4-123">1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.</span><span class="sxs-lookup"><span data-stu-id="975c4-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

