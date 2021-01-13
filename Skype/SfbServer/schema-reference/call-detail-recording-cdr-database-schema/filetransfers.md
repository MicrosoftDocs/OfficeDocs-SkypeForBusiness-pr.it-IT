---
title: Visualizzazione FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La visualizzazione filetransfer archivia le informazioni sulle sessioni di trasferimento file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821686"
---
# <a name="filetransfers-view"></a><span data-ttu-id="0752e-104">Visualizzazione FileTransfers</span><span class="sxs-lookup"><span data-stu-id="0752e-104">FileTransfers view</span></span>
 
<span data-ttu-id="0752e-105">La visualizzazione filetransfer archivia le informazioni sulle sessioni di trasferimento file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0752e-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="0752e-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0752e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0752e-107">La Visualizzazione FileTransfers contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0752e-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0752e-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0752e-108">**Column**</span></span>|<span data-ttu-id="0752e-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="0752e-109">**Data Type**</span></span>|<span data-ttu-id="0752e-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="0752e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0752e-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="0752e-111">**FileName**</span></span> <br/> |<span data-ttu-id="0752e-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0752e-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0752e-113">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="0752e-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="0752e-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="0752e-114">**Cookie**</span></span> <br/> |<span data-ttu-id="0752e-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="0752e-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="0752e-116">Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</span><span class="sxs-lookup"><span data-stu-id="0752e-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="0752e-117">**Fileidentity**</span><span class="sxs-lookup"><span data-stu-id="0752e-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="0752e-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="0752e-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="0752e-119">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome di file.</span><span class="sxs-lookup"><span data-stu-id="0752e-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="0752e-120">**Accettare**</span><span class="sxs-lookup"><span data-stu-id="0752e-120">**Accept**</span></span> <br/> |<span data-ttu-id="0752e-121">po'</span><span class="sxs-lookup"><span data-stu-id="0752e-121">bit</span></span>  <br/> |<span data-ttu-id="0752e-p103">Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="0752e-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0752e-124">**Rifiuta**</span><span class="sxs-lookup"><span data-stu-id="0752e-124">**Reject**</span></span> <br/> |<span data-ttu-id="0752e-125">po'</span><span class="sxs-lookup"><span data-stu-id="0752e-125">bit</span></span>  <br/> |<span data-ttu-id="0752e-p104">Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="0752e-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0752e-128">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="0752e-128">**Cancel**</span></span> <br/> |<span data-ttu-id="0752e-129">po'</span><span class="sxs-lookup"><span data-stu-id="0752e-129">bit</span></span>  <br/> |<span data-ttu-id="0752e-p105">Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="0752e-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

