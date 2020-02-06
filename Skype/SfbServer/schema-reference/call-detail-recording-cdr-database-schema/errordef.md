---
title: Tabella ErrorDef in Skype for Business Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabella ErrorDef archivia le informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815234"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2f9cc-104">Tabella ErrorDef in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f9cc-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2f9cc-105">La tabella ErrorDef archivia le informazioni su ogni tipo di errore che può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="2f9cc-106">Ogni record è un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="2f9cc-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-107">**Column**</span></span>|<span data-ttu-id="2f9cc-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-108">**Data Type**</span></span>|<span data-ttu-id="2f9cc-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-109">**Key/Index**</span></span>|<span data-ttu-id="2f9cc-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f9cc-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="2f9cc-112">int</span><span class="sxs-lookup"><span data-stu-id="2f9cc-112">int</span></span>  <br/> |<span data-ttu-id="2f9cc-113">Principale</span><span class="sxs-lookup"><span data-stu-id="2f9cc-113">Primary</span></span>  <br/> |<span data-ttu-id="2f9cc-114">Numero ID univoco che identifica questo tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="2f9cc-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="2f9cc-116">int</span><span class="sxs-lookup"><span data-stu-id="2f9cc-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="2f9cc-117">Codice di risposta SIP standard associato a questo errore.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="2f9cc-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="2f9cc-119">int</span><span class="sxs-lookup"><span data-stu-id="2f9cc-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="2f9cc-120">ID diagnostica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="2f9cc-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="2f9cc-122">Int</span><span class="sxs-lookup"><span data-stu-id="2f9cc-122">Int</span></span>  <br/> |<span data-ttu-id="2f9cc-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="2f9cc-123">Foreign</span></span>  <br/> |<span data-ttu-id="2f9cc-124">Tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-124">Type of the call.</span></span> <span data-ttu-id="2f9cc-125">Per altre informazioni, vedere la [tabella CallType in Skype for Business Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="2f9cc-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2f9cc-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-126">**RequestType**</span></span> <br/> |<span data-ttu-id="2f9cc-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="2f9cc-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="2f9cc-128">Tipo di richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="2f9cc-129">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2f9cc-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="2f9cc-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="2f9cc-130">**ContentType**</span></span> <br/> |<span data-ttu-id="2f9cc-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="2f9cc-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="2f9cc-132">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="2f9cc-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="2f9cc-133">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2f9cc-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

