---
title: Tabella Mcus in Skype for Business Server 2015
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
description: La tabella Mcus è una tabella di supporto. In ogni record sono archiviate informazioni su un servizio di conferenza. Possono includere il servizio Im Conferencing e il servizio Di telefonia (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821426"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f9fc8-105">Tabella Mcus in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f9fc8-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f9fc8-106">La tabella Mcus è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="f9fc8-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="f9fc8-107">In ogni record sono archiviate informazioni su un servizio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="f9fc8-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="f9fc8-108">Possono includere il servizio Im Conferencing e il servizio Di telefonia (che vengono eseguiti come processi nei server front-end) e il servizio Web Conferencing e il servizio A/V Conferencing.</span><span class="sxs-lookup"><span data-stu-id="f9fc8-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="f9fc8-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-109">**Column**</span></span>|<span data-ttu-id="f9fc8-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-110">**Data Type**</span></span>|<span data-ttu-id="f9fc8-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-111">**Key/Index**</span></span>|<span data-ttu-id="f9fc8-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f9fc8-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-113">**McuId**</span></span> <br/> |<span data-ttu-id="f9fc8-114">int</span><span class="sxs-lookup"><span data-stu-id="f9fc8-114">int</span></span>  <br/> |<span data-ttu-id="f9fc8-115">Principale</span><span class="sxs-lookup"><span data-stu-id="f9fc8-115">Primary</span></span>  <br/> |<span data-ttu-id="f9fc8-116">Numero univoco che identifica il server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="f9fc8-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="f9fc8-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-117">**McuUri**</span></span> <br/> |<span data-ttu-id="f9fc8-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="f9fc8-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="f9fc8-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="f9fc8-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="f9fc8-120">inyint</span><span class="sxs-lookup"><span data-stu-id="f9fc8-120">inyint</span></span>  <br/> | <span data-ttu-id="f9fc8-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="f9fc8-121">Foreign</span></span> <br/> |<span data-ttu-id="f9fc8-122">Tipo di server per conferenze, ad esempio conf:chat (per IMs) o conf:audio-video.</span><span class="sxs-lookup"><span data-stu-id="f9fc8-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="f9fc8-123">Per altre [informazioni, vedi la tabella UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="f9fc8-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

