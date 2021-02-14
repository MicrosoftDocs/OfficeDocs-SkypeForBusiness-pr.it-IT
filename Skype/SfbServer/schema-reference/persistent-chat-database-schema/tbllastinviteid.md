---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene l'ultimo ID invito generato per ogni utente e utilizzato nella tabella tblPrincipalInvites.
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815966"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="c5020-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c5020-103">tblLastInviteId</span></span>
 
<span data-ttu-id="c5020-104">tblLastInviteId contiene l'ultimo ID invito generato per ogni utente e utilizzato nella tabella tblPrincipalInvites.</span><span class="sxs-lookup"><span data-stu-id="c5020-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="c5020-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c5020-105">**Columns**</span></span>

|<span data-ttu-id="c5020-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c5020-106">**Column**</span></span>|<span data-ttu-id="c5020-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c5020-107">**Type**</span></span>|<span data-ttu-id="c5020-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c5020-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5020-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c5020-109">prinID</span></span>  <br/> |<span data-ttu-id="c5020-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="c5020-110">int, not null</span></span>  <br/> |<span data-ttu-id="c5020-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="c5020-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c5020-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="c5020-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="c5020-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="c5020-113">int, not null</span></span>  <br/> |<span data-ttu-id="c5020-114">Ultimo ID invito utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c5020-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="c5020-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="c5020-115">**Keys**</span></span>

|<span data-ttu-id="c5020-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c5020-116">**Column**</span></span>|<span data-ttu-id="c5020-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c5020-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c5020-118">prinID</span><span class="sxs-lookup"><span data-stu-id="c5020-118">prinID</span></span>  <br/> |<span data-ttu-id="c5020-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="c5020-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c5020-120">prinID</span><span class="sxs-lookup"><span data-stu-id="c5020-120">prinID</span></span>  <br/> |<span data-ttu-id="c5020-121">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c5020-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c5020-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5020-122">See also</span></span>

[<span data-ttu-id="c5020-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c5020-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
