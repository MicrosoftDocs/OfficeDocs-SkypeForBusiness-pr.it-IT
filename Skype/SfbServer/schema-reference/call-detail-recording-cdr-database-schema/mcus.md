---
title: Tabella MCU in Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815064"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="36b3f-105">Tabella MCU in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="36b3f-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="36b3f-106">La tabella MCU è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="36b3f-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="36b3f-107">Ogni record archivia le informazioni su un servizio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="36b3f-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="36b3f-108">Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.</span><span class="sxs-lookup"><span data-stu-id="36b3f-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="36b3f-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="36b3f-109">**Column**</span></span>|<span data-ttu-id="36b3f-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="36b3f-110">**Data Type**</span></span>|<span data-ttu-id="36b3f-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="36b3f-111">**Key/Index**</span></span>|<span data-ttu-id="36b3f-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="36b3f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36b3f-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="36b3f-113">**McuId**</span></span> <br/> |<span data-ttu-id="36b3f-114">int</span><span class="sxs-lookup"><span data-stu-id="36b3f-114">int</span></span>  <br/> |<span data-ttu-id="36b3f-115">Principale</span><span class="sxs-lookup"><span data-stu-id="36b3f-115">Primary</span></span>  <br/> |<span data-ttu-id="36b3f-116">Numero univoco che identifica questo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="36b3f-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="36b3f-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="36b3f-117">**McuUri**</span></span> <br/> |<span data-ttu-id="36b3f-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="36b3f-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="36b3f-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="36b3f-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="36b3f-120">inyint</span><span class="sxs-lookup"><span data-stu-id="36b3f-120">inyint</span></span>  <br/> | <span data-ttu-id="36b3f-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="36b3f-121">Foreign</span></span> <br/> |<span data-ttu-id="36b3f-122">Tipo di server di conferenza, ad esempio conf: chat (per IMs) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="36b3f-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="36b3f-123">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="36b3f-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

