---
title: Tabella DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La tabella DeviceDriver è una tabella di supporto. Ogni record rappresenta un driver utilizzato da un dispositivo di acquisizione o di rendering.
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823076"
---
# <a name="devicedriver-table"></a><span data-ttu-id="2b1d7-104">Tabella DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="2b1d7-104">DeviceDriver table</span></span>
 
<span data-ttu-id="2b1d7-p102">La tabella DeviceDriver è una tabella di supporto. Ogni record rappresenta un driver utilizzato da un dispositivo di acquisizione o di rendering.</span><span class="sxs-lookup"><span data-stu-id="2b1d7-p102">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="2b1d7-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2b1d7-107">**Column**</span></span>|<span data-ttu-id="2b1d7-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2b1d7-108">**Data Type**</span></span>|<span data-ttu-id="2b1d7-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2b1d7-109">**Key/Index**</span></span>|<span data-ttu-id="2b1d7-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2b1d7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b1d7-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="2b1d7-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="2b1d7-112">int</span><span class="sxs-lookup"><span data-stu-id="2b1d7-112">int</span></span>  <br/> |<span data-ttu-id="2b1d7-113">Principale</span><span class="sxs-lookup"><span data-stu-id="2b1d7-113">Primary</span></span>  <br/> |<span data-ttu-id="2b1d7-114">Numero univoco che identifica questo record del driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b1d7-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="2b1d7-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="2b1d7-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="2b1d7-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b1d7-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="2b1d7-117">unique</span><span class="sxs-lookup"><span data-stu-id="2b1d7-117">unique</span></span>  <br/> |<span data-ttu-id="2b1d7-118">Nome del driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b1d7-118">Device driver name.</span></span>  <br/> |
   

