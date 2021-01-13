---
title: Tabella media
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
# <a name="medialist-table"></a><span data-ttu-id="500bc-103">Tabella media</span><span class="sxs-lookup"><span data-stu-id="500bc-103">MediaList table</span></span>
 
<span data-ttu-id="500bc-104">La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="500bc-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="500bc-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="500bc-105">**Column**</span></span>|<span data-ttu-id="500bc-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="500bc-106">**Data Type**</span></span>|<span data-ttu-id="500bc-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="500bc-107">**Key/Index**</span></span>|<span data-ttu-id="500bc-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="500bc-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="500bc-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="500bc-109">**MediaId**</span></span> <br/> |<span data-ttu-id="500bc-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="500bc-110">tinyint</span></span>  <br/> |<span data-ttu-id="500bc-111">Principale</span><span class="sxs-lookup"><span data-stu-id="500bc-111">Primary</span></span>  <br/> |<span data-ttu-id="500bc-112">Valori: 1-7</span><span class="sxs-lookup"><span data-stu-id="500bc-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="500bc-113">**Contenuti multimediali**</span><span class="sxs-lookup"><span data-stu-id="500bc-113">**Media**</span></span> <br/> |<span data-ttu-id="500bc-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="500bc-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="500bc-115">Mapping statico dei valori di MediaID e media:</span><span class="sxs-lookup"><span data-stu-id="500bc-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="500bc-116">1 -- Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="500bc-116">1 -- IM</span></span> <br/>  <span data-ttu-id="500bc-117">2-trasferimento file</span><span class="sxs-lookup"><span data-stu-id="500bc-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="500bc-118">3-assistenza remota</span><span class="sxs-lookup"><span data-stu-id="500bc-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="500bc-119">4-condivisione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="500bc-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="500bc-120">5 -- Audio</span><span class="sxs-lookup"><span data-stu-id="500bc-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="500bc-121">6 -- Video</span><span class="sxs-lookup"><span data-stu-id="500bc-121">6 -- Video</span></span> <br/>  <span data-ttu-id="500bc-122">7-app invite</span><span class="sxs-lookup"><span data-stu-id="500bc-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="500bc-123">Se si sta tentando di determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario utilizzare il seguente frammento di join:</span><span class="sxs-lookup"><span data-stu-id="500bc-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
