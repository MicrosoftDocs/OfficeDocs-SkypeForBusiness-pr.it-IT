---
title: Visualizzazione FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815204"
---
# <a name="filetransfers-view"></a><span data-ttu-id="415f9-104">Visualizzazione FileTransfers</span><span class="sxs-lookup"><span data-stu-id="415f9-104">FileTransfers view</span></span>
 
<span data-ttu-id="415f9-105">La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="415f9-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="415f9-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="415f9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="415f9-107">La Visualizzazione FileTransfers contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="415f9-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="415f9-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="415f9-108">**Column**</span></span>|<span data-ttu-id="415f9-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="415f9-109">**Data Type**</span></span>|<span data-ttu-id="415f9-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="415f9-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="415f9-111">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="415f9-111">**FileName**</span></span> <br/> |<span data-ttu-id="415f9-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="415f9-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="415f9-113">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="415f9-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="415f9-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="415f9-114">**Cookie**</span></span> <br/> |<span data-ttu-id="415f9-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="415f9-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="415f9-116">Usato per identificare ogni messaggio di follow-up associato a questo.</span><span class="sxs-lookup"><span data-stu-id="415f9-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="415f9-117">**Fileidentity**</span><span class="sxs-lookup"><span data-stu-id="415f9-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="415f9-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="415f9-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="415f9-119">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="415f9-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="415f9-120">**Accettare**</span><span class="sxs-lookup"><span data-stu-id="415f9-120">**Accept**</span></span> <br/> |<span data-ttu-id="415f9-121">po'</span><span class="sxs-lookup"><span data-stu-id="415f9-121">bit</span></span>  <br/> |<span data-ttu-id="415f9-122">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="415f9-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="415f9-123">Se TRUE, quindi Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="415f9-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="415f9-124">**Rifiutare**</span><span class="sxs-lookup"><span data-stu-id="415f9-124">**Reject**</span></span> <br/> |<span data-ttu-id="415f9-125">po'</span><span class="sxs-lookup"><span data-stu-id="415f9-125">bit</span></span>  <br/> |<span data-ttu-id="415f9-126">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="415f9-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="415f9-127">Se TRUE, accetta e Annulla sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="415f9-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="415f9-128">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="415f9-128">**Cancel**</span></span> <br/> |<span data-ttu-id="415f9-129">po'</span><span class="sxs-lookup"><span data-stu-id="415f9-129">bit</span></span>  <br/> |<span data-ttu-id="415f9-130">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="415f9-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="415f9-131">Se TRUE, accetta e rifiuta sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="415f9-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

