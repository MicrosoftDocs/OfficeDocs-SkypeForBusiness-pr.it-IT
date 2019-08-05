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
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194776"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e0322-105">Tabella MCU in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0322-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e0322-106">La tabella MCU è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="e0322-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="e0322-107">Ogni record archivia le informazioni su un servizio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e0322-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="e0322-108">Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.</span><span class="sxs-lookup"><span data-stu-id="e0322-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="e0322-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e0322-109">**Column**</span></span>|<span data-ttu-id="e0322-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e0322-110">**Data Type**</span></span>|<span data-ttu-id="e0322-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e0322-111">**Key/Index**</span></span>|<span data-ttu-id="e0322-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e0322-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0322-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="e0322-113">**McuId**</span></span> <br/> |<span data-ttu-id="e0322-114">int</span><span class="sxs-lookup"><span data-stu-id="e0322-114">int</span></span>  <br/> |<span data-ttu-id="e0322-115">Principale</span><span class="sxs-lookup"><span data-stu-id="e0322-115">Primary</span></span>  <br/> |<span data-ttu-id="e0322-116">Numero univoco che identifica questo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e0322-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="e0322-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="e0322-117">**McuUri**</span></span> <br/> |<span data-ttu-id="e0322-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e0322-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="e0322-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="e0322-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="e0322-120">inyint</span><span class="sxs-lookup"><span data-stu-id="e0322-120">inyint</span></span>  <br/> | <span data-ttu-id="e0322-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="e0322-121">Foreign</span></span> <br/> |<span data-ttu-id="e0322-122">Tipo di server di conferenza, ad esempio conf: chat (per IMs) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="e0322-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="e0322-123">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="e0322-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

