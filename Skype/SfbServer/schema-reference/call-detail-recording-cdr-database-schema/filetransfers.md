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
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194802"
---
# <a name="filetransfers-view"></a><span data-ttu-id="695be-104">Visualizzazione FileTransfers</span><span class="sxs-lookup"><span data-stu-id="695be-104">FileTransfers view</span></span>
 
<span data-ttu-id="695be-105">La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="695be-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="695be-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="695be-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="695be-107">La Visualizzazione FileTransfers contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="695be-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="695be-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="695be-108">**Column**</span></span>|<span data-ttu-id="695be-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="695be-109">**Data Type**</span></span>|<span data-ttu-id="695be-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="695be-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="695be-111">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="695be-111">**FileName**</span></span> <br/> |<span data-ttu-id="695be-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="695be-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="695be-113">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="695be-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="695be-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="695be-114">**Cookie**</span></span> <br/> |<span data-ttu-id="695be-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="695be-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="695be-116">Usato per identificare ogni messaggio di follow-up associato a questo.</span><span class="sxs-lookup"><span data-stu-id="695be-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="695be-117">**Fileidentity**</span><span class="sxs-lookup"><span data-stu-id="695be-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="695be-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="695be-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="695be-119">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="695be-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="695be-120">**Accettare**</span><span class="sxs-lookup"><span data-stu-id="695be-120">**Accept**</span></span> <br/> |<span data-ttu-id="695be-121">po'</span><span class="sxs-lookup"><span data-stu-id="695be-121">bit</span></span>  <br/> |<span data-ttu-id="695be-122">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="695be-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="695be-123">Se TRUE, quindi Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="695be-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="695be-124">**Rifiutare**</span><span class="sxs-lookup"><span data-stu-id="695be-124">**Reject**</span></span> <br/> |<span data-ttu-id="695be-125">po'</span><span class="sxs-lookup"><span data-stu-id="695be-125">bit</span></span>  <br/> |<span data-ttu-id="695be-126">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="695be-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="695be-127">Se TRUE, accetta e Annulla sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="695be-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="695be-128">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="695be-128">**Cancel**</span></span> <br/> |<span data-ttu-id="695be-129">po'</span><span class="sxs-lookup"><span data-stu-id="695be-129">bit</span></span>  <br/> |<span data-ttu-id="695be-130">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="695be-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="695be-131">Se TRUE, accetta e rifiuta sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="695be-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

