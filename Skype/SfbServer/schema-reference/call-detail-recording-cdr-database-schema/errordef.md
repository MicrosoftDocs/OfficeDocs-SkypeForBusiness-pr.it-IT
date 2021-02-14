---
title: Tabella ErrorDef in Skype for Business Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: Nella tabella ErrorDef sono archiviate informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821726"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fd834-104">Tabella ErrorDef in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd834-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fd834-105">Nella tabella ErrorDef sono archiviate informazioni su ogni tipo di errore che può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="fd834-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="fd834-106">Ogni record è un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="fd834-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="fd834-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="fd834-107">**Column**</span></span>|<span data-ttu-id="fd834-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="fd834-108">**Data Type**</span></span>|<span data-ttu-id="fd834-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="fd834-109">**Key/Index**</span></span>|<span data-ttu-id="fd834-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="fd834-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd834-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="fd834-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="fd834-112">int</span><span class="sxs-lookup"><span data-stu-id="fd834-112">int</span></span>  <br/> |<span data-ttu-id="fd834-113">Principale</span><span class="sxs-lookup"><span data-stu-id="fd834-113">Primary</span></span>  <br/> |<span data-ttu-id="fd834-114">Numero ID univoco che identifica questo tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="fd834-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="fd834-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="fd834-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="fd834-116">int</span><span class="sxs-lookup"><span data-stu-id="fd834-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="fd834-117">Codice di risposta SIP standard associato a questo errore.</span><span class="sxs-lookup"><span data-stu-id="fd834-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="fd834-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="fd834-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="fd834-119">int</span><span class="sxs-lookup"><span data-stu-id="fd834-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="fd834-120">ID diagnostica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd834-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="fd834-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="fd834-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="fd834-122">Soglia</span><span class="sxs-lookup"><span data-stu-id="fd834-122">Int</span></span>  <br/> |<span data-ttu-id="fd834-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="fd834-123">Foreign</span></span>  <br/> |<span data-ttu-id="fd834-124">Tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd834-124">Type of the call.</span></span> <span data-ttu-id="fd834-125">Per ulteriori informazioni, vedere la tabella [CallType in Skype for Business Server 2015.](calltype.md)</span><span class="sxs-lookup"><span data-stu-id="fd834-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fd834-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="fd834-126">**RequestType**</span></span> <br/> |<span data-ttu-id="fd834-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="fd834-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="fd834-128">Tipo della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="fd834-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="fd834-129">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="fd834-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="fd834-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="fd834-130">**ContentType**</span></span> <br/> |<span data-ttu-id="fd834-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="fd834-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="fd834-132">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="fd834-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="fd834-133">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="fd834-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

