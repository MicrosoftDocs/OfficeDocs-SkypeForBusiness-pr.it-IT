---
title: Tabella UriTypes
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814844"
---
# <a name="uritypes-table"></a><span data-ttu-id="0cfd3-103">Tabella UriTypes</span><span class="sxs-lookup"><span data-stu-id="0cfd3-103">UriTypes table</span></span>
 
<span data-ttu-id="0cfd3-104">La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0cfd3-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="0cfd3-105">Quando viene creato il DB CDR, vengono creati due record per rappresentare PhoneUri e UserUri e i record creati dopo che sono stati assegnati in modo dinamico UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="0cfd3-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="0cfd3-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0cfd3-106">**Column**</span></span>|<span data-ttu-id="0cfd3-107">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="0cfd3-107">**Data Type**</span></span>|<span data-ttu-id="0cfd3-108">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="0cfd3-108">**Key/Index**</span></span>|<span data-ttu-id="0cfd3-109">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="0cfd3-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cfd3-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="0cfd3-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="0cfd3-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="0cfd3-111">tinyint</span></span>  <br/> |<span data-ttu-id="0cfd3-112">Principale</span><span class="sxs-lookup"><span data-stu-id="0cfd3-112">Primary</span></span>  <br/> |<span data-ttu-id="0cfd3-113">Identificatore univoco assegnato a un tipo URI.</span><span class="sxs-lookup"><span data-stu-id="0cfd3-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="0cfd3-114">Valori possibili-da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="0cfd3-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="0cfd3-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="0cfd3-115">**UriType**</span></span> <br/> |<span data-ttu-id="0cfd3-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0cfd3-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="0cfd3-117">Descrizioni dei diversi tipi di URI.</span><span class="sxs-lookup"><span data-stu-id="0cfd3-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="0cfd3-118">I valori seguenti sono pre-assegnati:</span><span class="sxs-lookup"><span data-stu-id="0cfd3-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="0cfd3-119">URI 1-Phone</span><span class="sxs-lookup"><span data-stu-id="0cfd3-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="0cfd3-120">0-URI utente</span><span class="sxs-lookup"><span data-stu-id="0cfd3-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="0cfd3-121">Altri tipi possibili includono:</span><span class="sxs-lookup"><span data-stu-id="0cfd3-121">Other possible types include:</span></span> <br/><span data-ttu-id="0cfd3-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="0cfd3-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="0cfd3-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="0cfd3-123">conf:audio-video</span></span><br/> <span data-ttu-id="0cfd3-124">conf: chat</span><span class="sxs-lookup"><span data-stu-id="0cfd3-124">conf:chat</span></span><br/>    <span data-ttu-id="0cfd3-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="0cfd3-125">conf:focus</span></span><br/>   <span data-ttu-id="0cfd3-126">MRA</span><span class="sxs-lookup"><span data-stu-id="0cfd3-126">mras</span></span><br/>
