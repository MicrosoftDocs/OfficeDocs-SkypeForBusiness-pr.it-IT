---
title: Tabella MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194769"
---
# <a name="medialist-table"></a><span data-ttu-id="b8084-103">Tabella MediaList</span><span class="sxs-lookup"><span data-stu-id="b8084-103">MediaList table</span></span>
 
<span data-ttu-id="b8084-104">La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="b8084-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="b8084-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b8084-105">**Column**</span></span>|<span data-ttu-id="b8084-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b8084-106">**Data Type**</span></span>|<span data-ttu-id="b8084-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="b8084-107">**Key/Index**</span></span>|<span data-ttu-id="b8084-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b8084-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8084-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="b8084-109">**MediaId**</span></span> <br/> |<span data-ttu-id="b8084-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="b8084-110">tinyint</span></span>  <br/> |<span data-ttu-id="b8084-111">Principale</span><span class="sxs-lookup"><span data-stu-id="b8084-111">Primary</span></span>  <br/> |<span data-ttu-id="b8084-112">Valori: 1-7</span><span class="sxs-lookup"><span data-stu-id="b8084-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="b8084-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="b8084-113">**Media**</span></span> <br/> |<span data-ttu-id="b8084-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b8084-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b8084-115">Mapping statico di valori MediaID e media:</span><span class="sxs-lookup"><span data-stu-id="b8084-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="b8084-116">1--MESSAGGISTICA ISTANTANEA</span><span class="sxs-lookup"><span data-stu-id="b8084-116">1 -- IM</span></span> <br/>  <span data-ttu-id="b8084-117">2-trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="b8084-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="b8084-118">3-assistenza remota</span><span class="sxs-lookup"><span data-stu-id="b8084-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="b8084-119">4-condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="b8084-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="b8084-120">5--audio</span><span class="sxs-lookup"><span data-stu-id="b8084-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="b8084-121">6--video</span><span class="sxs-lookup"><span data-stu-id="b8084-121">6 -- Video</span></span> <br/>  <span data-ttu-id="b8084-122">7-invito all'app</span><span class="sxs-lookup"><span data-stu-id="b8084-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="b8084-123">Se si sta provando a determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario usare il frammento di join seguente:</span><span class="sxs-lookup"><span data-stu-id="b8084-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
