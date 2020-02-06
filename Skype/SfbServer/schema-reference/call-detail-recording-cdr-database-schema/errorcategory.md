---
title: Tabella ErrorCategory in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815254"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ab39c-104">Tabella ErrorCategory in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab39c-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ab39c-105">La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ab39c-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="ab39c-106">Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab39c-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="ab39c-107">0--successo</span><span class="sxs-lookup"><span data-stu-id="ab39c-107">0 -- Success</span></span>
    
- <span data-ttu-id="ab39c-108">1-errore previsto</span><span class="sxs-lookup"><span data-stu-id="ab39c-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="ab39c-109">2-errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="ab39c-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="ab39c-110">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab39c-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ab39c-111">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ab39c-111">**Column**</span></span>|<span data-ttu-id="ab39c-112">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ab39c-112">**Data Type**</span></span>|<span data-ttu-id="ab39c-113">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="ab39c-113">**Key/Index**</span></span>|<span data-ttu-id="ab39c-114">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="ab39c-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab39c-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="ab39c-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="ab39c-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="ab39c-116">tinyint</span></span>  <br/> |<span data-ttu-id="ab39c-117">Principale</span><span class="sxs-lookup"><span data-stu-id="ab39c-117">Primary</span></span>  <br/> |<span data-ttu-id="ab39c-118">Identificatore univoco per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="ab39c-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="ab39c-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ab39c-119">**Name**</span></span> <br/> |<span data-ttu-id="ab39c-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab39c-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ab39c-121">Valore e nome descrittivo assegnato alla classificazione.</span><span class="sxs-lookup"><span data-stu-id="ab39c-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="ab39c-122">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="ab39c-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="ab39c-123">0--successo</span><span class="sxs-lookup"><span data-stu-id="ab39c-123">0 -- Success</span></span> <br/>  <span data-ttu-id="ab39c-124">1-errore previsto</span><span class="sxs-lookup"><span data-stu-id="ab39c-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="ab39c-125">2-errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="ab39c-125">2 - Unexpected failure</span></span> <br/> |
   

