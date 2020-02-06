---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814574"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="7373f-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="7373f-103">tblLastInviteId</span></span>
 
<span data-ttu-id="7373f-104">tblLastInviteId contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="7373f-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="7373f-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7373f-105">**Columns**</span></span>

|<span data-ttu-id="7373f-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7373f-106">**Column**</span></span>|<span data-ttu-id="7373f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7373f-107">**Type**</span></span>|<span data-ttu-id="7373f-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7373f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7373f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="7373f-109">prinID</span></span>  <br/> |<span data-ttu-id="7373f-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="7373f-110">int, not null</span></span>  <br/> |<span data-ttu-id="7373f-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="7373f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="7373f-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="7373f-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="7373f-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="7373f-113">int, not null</span></span>  <br/> |<span data-ttu-id="7373f-114">Ultimo ID invito usato.</span><span class="sxs-lookup"><span data-stu-id="7373f-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="7373f-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="7373f-115">**Keys**</span></span>

|<span data-ttu-id="7373f-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7373f-116">**Column**</span></span>|<span data-ttu-id="7373f-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7373f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7373f-118">prinID</span><span class="sxs-lookup"><span data-stu-id="7373f-118">prinID</span></span>  <br/> |<span data-ttu-id="7373f-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7373f-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7373f-120">prinID</span><span class="sxs-lookup"><span data-stu-id="7373f-120">prinID</span></span>  <br/> |<span data-ttu-id="7373f-121">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="7373f-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7373f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7373f-122">See also</span></span>

[<span data-ttu-id="7373f-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="7373f-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
