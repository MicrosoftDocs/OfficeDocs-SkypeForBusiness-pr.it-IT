---
title: Visualizzazione ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi e versioni di client che hanno partecipato alle sessioni registrate nel database. Ogni record della visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194845"
---
# <a name="clientversions-view"></a><span data-ttu-id="a4ce1-105">Visualizzazione ClientVersions</span><span class="sxs-lookup"><span data-stu-id="a4ce1-105">ClientVersions view</span></span>
 
<span data-ttu-id="a4ce1-106">La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi e versioni di client che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a4ce1-107">Ogni record della visualizzazione rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="a4ce1-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4ce1-109">Per alcune colonne possono essere presenti più record.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="a4ce1-110">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-110">**Column**</span></span>|<span data-ttu-id="a4ce1-111">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-111">**Data Type**</span></span>|<span data-ttu-id="a4ce1-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4ce1-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-113">**VersionId**</span></span> <br/> |<span data-ttu-id="a4ce1-114">int</span><span class="sxs-lookup"><span data-stu-id="a4ce1-114">int</span></span>  <br/> |<span data-ttu-id="a4ce1-115">Numero univoco che identifica questo tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="a4ce1-116">**Versione**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-116">**Version**</span></span> <br/> |<span data-ttu-id="a4ce1-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a4ce1-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a4ce1-118">Rappresenta l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="a4ce1-119">**TipoClient**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-119">**ClientType**</span></span> <br/> |<span data-ttu-id="a4ce1-120">int</span><span class="sxs-lookup"><span data-stu-id="a4ce1-120">int</span></span>  <br/> |<span data-ttu-id="a4ce1-121">Tipo di client.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="a4ce1-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="a4ce1-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="a4ce1-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a4ce1-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="a4ce1-124">Categoria a cui appartiene il client.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-124">Category that the client belongs to.</span></span> <span data-ttu-id="a4ce1-125">Ad esempio, il client Conferencing_Attendant_ 1.0 appartiene alla ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="a4ce1-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

