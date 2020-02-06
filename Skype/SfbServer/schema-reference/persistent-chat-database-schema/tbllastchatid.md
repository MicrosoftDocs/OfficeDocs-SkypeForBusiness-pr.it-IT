---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814584"
---
# <a name="tbllastchatid"></a><span data-ttu-id="c9501-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="c9501-103">tblLastChatId</span></span>
 
<span data-ttu-id="c9501-104">tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="c9501-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="c9501-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c9501-105">**Columns**</span></span>

|<span data-ttu-id="c9501-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c9501-106">**Column**</span></span>|<span data-ttu-id="c9501-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c9501-107">**Type**</span></span>|<span data-ttu-id="c9501-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c9501-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9501-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="c9501-109">nodeID</span></span>  <br/> |<span data-ttu-id="c9501-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="c9501-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9501-111">ID nodo (solo chat room-tipo).</span><span class="sxs-lookup"><span data-stu-id="c9501-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="c9501-112">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="c9501-112">lastChatID</span></span>  <br/> |<span data-ttu-id="c9501-113">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="c9501-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="c9501-114">Ultimo ID chat usato.</span><span class="sxs-lookup"><span data-stu-id="c9501-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="c9501-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="c9501-115">**Keys**</span></span>

|<span data-ttu-id="c9501-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c9501-116">**Column**</span></span>|<span data-ttu-id="c9501-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c9501-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9501-118">\<nodeID, dalla LastChatId\></span><span class="sxs-lookup"><span data-stu-id="c9501-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="c9501-119">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="c9501-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="c9501-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="c9501-120">nodeID</span></span>  <br/> |<span data-ttu-id="c9501-121">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="c9501-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9501-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9501-122">See also</span></span>

[<span data-ttu-id="c9501-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="c9501-123">tblChat</span></span>](tblchat.md)
