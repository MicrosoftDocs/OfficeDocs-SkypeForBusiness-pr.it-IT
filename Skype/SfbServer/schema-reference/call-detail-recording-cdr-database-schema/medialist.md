---
title: Tabella MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813136"
---
# <a name="medialist-table"></a><span data-ttu-id="970a9-103">Tabella MediaList</span><span class="sxs-lookup"><span data-stu-id="970a9-103">MediaList table</span></span>
 
<span data-ttu-id="970a9-104">La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="970a9-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="970a9-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="970a9-105">**Column**</span></span>|<span data-ttu-id="970a9-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="970a9-106">**Data Type**</span></span>|<span data-ttu-id="970a9-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="970a9-107">**Key/Index**</span></span>|<span data-ttu-id="970a9-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="970a9-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="970a9-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="970a9-109">**MediaId**</span></span> <br/> |<span data-ttu-id="970a9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="970a9-110">tinyint</span></span>  <br/> |<span data-ttu-id="970a9-111">Principale</span><span class="sxs-lookup"><span data-stu-id="970a9-111">Primary</span></span>  <br/> |<span data-ttu-id="970a9-112">Valori: 1-7</span><span class="sxs-lookup"><span data-stu-id="970a9-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="970a9-113">**Contenuti multimediali**</span><span class="sxs-lookup"><span data-stu-id="970a9-113">**Media**</span></span> <br/> |<span data-ttu-id="970a9-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="970a9-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="970a9-115">Mapping statico dei valori MediaID e Media:</span><span class="sxs-lookup"><span data-stu-id="970a9-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="970a9-116">1 -- Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="970a9-116">1 -- IM</span></span> <br/>  <span data-ttu-id="970a9-117">2 - Trasferimento file</span><span class="sxs-lookup"><span data-stu-id="970a9-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="970a9-118">3 - Assistenza remota</span><span class="sxs-lookup"><span data-stu-id="970a9-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="970a9-119">4 - Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="970a9-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="970a9-120">5 -- Audio</span><span class="sxs-lookup"><span data-stu-id="970a9-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="970a9-121">6 -- Video</span><span class="sxs-lookup"><span data-stu-id="970a9-121">6 -- Video</span></span> <br/>  <span data-ttu-id="970a9-122">7 - Invito all'app</span><span class="sxs-lookup"><span data-stu-id="970a9-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="970a9-123">Se si sta tentando di determinare il tipo di modalità per i valori in LcsCDR.SessionDetailsView.MediaTypes, è necessario utilizzare il frammento join seguente:</span><span class="sxs-lookup"><span data-stu-id="970a9-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
