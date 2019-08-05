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
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabella ErrorDef archivia le informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194810"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="55acd-104">Tabella ErrorDef in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55acd-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55acd-105">La tabella ErrorDef archivia le informazioni su ogni tipo di errore che può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="55acd-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="55acd-106">Ogni record è un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="55acd-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="55acd-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="55acd-107">**Column**</span></span>|<span data-ttu-id="55acd-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="55acd-108">**Data Type**</span></span>|<span data-ttu-id="55acd-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="55acd-109">**Key/Index**</span></span>|<span data-ttu-id="55acd-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="55acd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55acd-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="55acd-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="55acd-112">int</span><span class="sxs-lookup"><span data-stu-id="55acd-112">int</span></span>  <br/> |<span data-ttu-id="55acd-113">Principale</span><span class="sxs-lookup"><span data-stu-id="55acd-113">Primary</span></span>  <br/> |<span data-ttu-id="55acd-114">Numero ID univoco che identifica questo tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="55acd-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="55acd-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="55acd-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="55acd-116">int</span><span class="sxs-lookup"><span data-stu-id="55acd-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="55acd-117">Codice di risposta SIP standard associato a questo errore.</span><span class="sxs-lookup"><span data-stu-id="55acd-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="55acd-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="55acd-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="55acd-119">int</span><span class="sxs-lookup"><span data-stu-id="55acd-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="55acd-120">ID diagnostica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55acd-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="55acd-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="55acd-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="55acd-122">Int</span><span class="sxs-lookup"><span data-stu-id="55acd-122">Int</span></span>  <br/> |<span data-ttu-id="55acd-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="55acd-123">Foreign</span></span>  <br/> |<span data-ttu-id="55acd-124">Tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="55acd-124">Type of the call.</span></span> <span data-ttu-id="55acd-125">Per altre informazioni, vedere la [tabella CallType in Skype for Business Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="55acd-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="55acd-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="55acd-126">**RequestType**</span></span> <br/> |<span data-ttu-id="55acd-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="55acd-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="55acd-128">Tipo di richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="55acd-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="55acd-129">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="55acd-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="55acd-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="55acd-130">**ContentType**</span></span> <br/> |<span data-ttu-id="55acd-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="55acd-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="55acd-132">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="55acd-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="55acd-133">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="55acd-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

