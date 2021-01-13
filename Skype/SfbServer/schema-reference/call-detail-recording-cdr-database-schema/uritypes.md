---
title: Tabella UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831686"
---
# <a name="uritypes-table"></a><span data-ttu-id="35e2d-103">Tabella UriTypes</span><span class="sxs-lookup"><span data-stu-id="35e2d-103">UriTypes table</span></span>
 
<span data-ttu-id="35e2d-104">La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="35e2d-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="35e2d-105">Quando viene creato il database di registrazione dettagli chiamata, vengono creati due record per rappresentare PhoneUri e UserUri, nonché i record creati dopo che sono stati assegnati UriTypeId dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="35e2d-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="35e2d-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="35e2d-106">**Column**</span></span>|<span data-ttu-id="35e2d-107">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="35e2d-107">**Data Type**</span></span>|<span data-ttu-id="35e2d-108">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="35e2d-108">**Key/Index**</span></span>|<span data-ttu-id="35e2d-109">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="35e2d-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35e2d-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="35e2d-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="35e2d-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="35e2d-111">tinyint</span></span>  <br/> |<span data-ttu-id="35e2d-112">Principale</span><span class="sxs-lookup"><span data-stu-id="35e2d-112">Primary</span></span>  <br/> |<span data-ttu-id="35e2d-113">Identificatore univoco assegnato a un tipo di URI.</span><span class="sxs-lookup"><span data-stu-id="35e2d-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="35e2d-114">Valori possibili-da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="35e2d-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="35e2d-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="35e2d-115">**UriType**</span></span> <br/> |<span data-ttu-id="35e2d-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35e2d-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="35e2d-117">Descrizione dei diversi tipi di URI.</span><span class="sxs-lookup"><span data-stu-id="35e2d-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="35e2d-118">I valori seguenti sono preassegnati:</span><span class="sxs-lookup"><span data-stu-id="35e2d-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="35e2d-119">1-telefono URI</span><span class="sxs-lookup"><span data-stu-id="35e2d-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="35e2d-120">0-URI utente</span><span class="sxs-lookup"><span data-stu-id="35e2d-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="35e2d-121">Altri tipi possibili includono:</span><span class="sxs-lookup"><span data-stu-id="35e2d-121">Other possible types include:</span></span> <br/><span data-ttu-id="35e2d-122">conf: ApplicationSharing</span><span class="sxs-lookup"><span data-stu-id="35e2d-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="35e2d-123">conf: audio-video</span><span class="sxs-lookup"><span data-stu-id="35e2d-123">conf:audio-video</span></span><br/> <span data-ttu-id="35e2d-124">conf: chat</span><span class="sxs-lookup"><span data-stu-id="35e2d-124">conf:chat</span></span><br/>    <span data-ttu-id="35e2d-125">conf: Focus</span><span class="sxs-lookup"><span data-stu-id="35e2d-125">conf:focus</span></span><br/>   <span data-ttu-id="35e2d-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="35e2d-126">mras</span></span><br/>
