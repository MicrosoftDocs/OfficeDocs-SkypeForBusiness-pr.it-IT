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
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194679"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="3c831-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="3c831-103">tblLastInviteId</span></span>
 
<span data-ttu-id="3c831-104">tblLastInviteId contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="3c831-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="3c831-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3c831-105">**Columns**</span></span>

|<span data-ttu-id="3c831-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3c831-106">**Column**</span></span>|<span data-ttu-id="3c831-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c831-107">**Type**</span></span>|<span data-ttu-id="3c831-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3c831-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c831-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3c831-109">prinID</span></span>  <br/> |<span data-ttu-id="3c831-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="3c831-110">int, not null</span></span>  <br/> |<span data-ttu-id="3c831-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="3c831-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3c831-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="3c831-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="3c831-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="3c831-113">int, not null</span></span>  <br/> |<span data-ttu-id="3c831-114">Ultimo ID invito usato.</span><span class="sxs-lookup"><span data-stu-id="3c831-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="3c831-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="3c831-115">**Keys**</span></span>

|<span data-ttu-id="3c831-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3c831-116">**Column**</span></span>|<span data-ttu-id="3c831-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3c831-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c831-118">prinID</span><span class="sxs-lookup"><span data-stu-id="3c831-118">prinID</span></span>  <br/> |<span data-ttu-id="3c831-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3c831-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3c831-120">prinID</span><span class="sxs-lookup"><span data-stu-id="3c831-120">prinID</span></span>  <br/> |<span data-ttu-id="3c831-121">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="3c831-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3c831-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c831-122">See also</span></span>

[<span data-ttu-id="3c831-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="3c831-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
