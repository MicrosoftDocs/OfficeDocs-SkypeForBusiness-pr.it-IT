---
title: Tabella MCU in Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabella MCU è una tabella di supporto. Ogni record archivia le informazioni su un servizio di conferenza. Tali servizi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di telefonia (che viene eseguito come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821426"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="55e41-105">Tabella MCU in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55e41-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55e41-106">La tabella MCU è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="55e41-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="55e41-107">Ogni record archivia le informazioni su un servizio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="55e41-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="55e41-108">Tali servizi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di telefonia (che viene eseguito come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.</span><span class="sxs-lookup"><span data-stu-id="55e41-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="55e41-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="55e41-109">**Column**</span></span>|<span data-ttu-id="55e41-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="55e41-110">**Data Type**</span></span>|<span data-ttu-id="55e41-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="55e41-111">**Key/Index**</span></span>|<span data-ttu-id="55e41-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="55e41-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55e41-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="55e41-113">**McuId**</span></span> <br/> |<span data-ttu-id="55e41-114">int</span><span class="sxs-lookup"><span data-stu-id="55e41-114">int</span></span>  <br/> |<span data-ttu-id="55e41-115">Principale</span><span class="sxs-lookup"><span data-stu-id="55e41-115">Primary</span></span>  <br/> |<span data-ttu-id="55e41-116">Numero univoco che identifica il server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="55e41-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="55e41-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="55e41-117">**McuUri**</span></span> <br/> |<span data-ttu-id="55e41-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="55e41-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="55e41-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="55e41-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="55e41-120">inyint</span><span class="sxs-lookup"><span data-stu-id="55e41-120">inyint</span></span>  <br/> | <span data-ttu-id="55e41-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="55e41-121">Foreign</span></span> <br/> |<span data-ttu-id="55e41-122">Tipo di Server Conferencing, ad esempio conf: chat (per IMs) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="55e41-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="55e41-123">Per ulteriori informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="55e41-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

