---
title: Visualizzazione ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Nella visualizzazione ClientVersions vengono archiviate informazioni sui diversi tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813356"
---
# <a name="clientversions-view"></a><span data-ttu-id="f97dd-105">Visualizzazione ClientVersions</span><span class="sxs-lookup"><span data-stu-id="f97dd-105">ClientVersions view</span></span>
 
<span data-ttu-id="f97dd-106">Nella visualizzazione ClientVersions vengono archiviate informazioni sui diversi tipi di client e versioni che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="f97dd-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f97dd-107">Ogni record nella visualizzazione rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="f97dd-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="f97dd-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f97dd-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f97dd-109">È possibile che siano presenti più record per determinate colonne.</span><span class="sxs-lookup"><span data-stu-id="f97dd-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="f97dd-110">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f97dd-110">**Column**</span></span>|<span data-ttu-id="f97dd-111">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="f97dd-111">**Data Type**</span></span>|<span data-ttu-id="f97dd-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="f97dd-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f97dd-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="f97dd-113">**VersionId**</span></span> <br/> |<span data-ttu-id="f97dd-114">int</span><span class="sxs-lookup"><span data-stu-id="f97dd-114">int</span></span>  <br/> |<span data-ttu-id="f97dd-115">Numero univoco che identifica il tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="f97dd-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="f97dd-116">**Versione**</span><span class="sxs-lookup"><span data-stu-id="f97dd-116">**Version**</span></span> <br/> |<span data-ttu-id="f97dd-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f97dd-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f97dd-118">Rappresenta l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="f97dd-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="f97dd-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="f97dd-119">**ClientType**</span></span> <br/> |<span data-ttu-id="f97dd-120">int</span><span class="sxs-lookup"><span data-stu-id="f97dd-120">int</span></span>  <br/> |<span data-ttu-id="f97dd-121">Tipo di client.</span><span class="sxs-lookup"><span data-stu-id="f97dd-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="f97dd-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="f97dd-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="f97dd-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="f97dd-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="f97dd-124">Categoria a cui appartiene il client.</span><span class="sxs-lookup"><span data-stu-id="f97dd-124">Category that the client belongs to.</span></span> <span data-ttu-id="f97dd-125">Ad esempio, il client Conferencing_Attendant_1.0 appartiene alla CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="f97dd-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

