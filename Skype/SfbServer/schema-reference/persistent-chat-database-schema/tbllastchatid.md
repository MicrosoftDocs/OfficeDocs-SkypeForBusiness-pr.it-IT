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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194682"
---
# <a name="tbllastchatid"></a><span data-ttu-id="c58ec-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="c58ec-103">tblLastChatId</span></span>
 
<span data-ttu-id="c58ec-104">tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="c58ec-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="c58ec-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c58ec-105">**Columns**</span></span>

|<span data-ttu-id="c58ec-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c58ec-106">**Column**</span></span>|<span data-ttu-id="c58ec-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c58ec-107">**Type**</span></span>|<span data-ttu-id="c58ec-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c58ec-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c58ec-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="c58ec-109">nodeID</span></span>  <br/> |<span data-ttu-id="c58ec-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="c58ec-110">int, not null</span></span>  <br/> |<span data-ttu-id="c58ec-111">ID nodo (solo chat room-tipo).</span><span class="sxs-lookup"><span data-stu-id="c58ec-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="c58ec-112">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="c58ec-112">lastChatID</span></span>  <br/> |<span data-ttu-id="c58ec-113">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="c58ec-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="c58ec-114">Ultimo ID chat usato.</span><span class="sxs-lookup"><span data-stu-id="c58ec-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="c58ec-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="c58ec-115">**Keys**</span></span>

|<span data-ttu-id="c58ec-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c58ec-116">**Column**</span></span>|<span data-ttu-id="c58ec-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c58ec-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c58ec-118">\<nodeID, dalla LastChatId\></span><span class="sxs-lookup"><span data-stu-id="c58ec-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="c58ec-119">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="c58ec-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="c58ec-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="c58ec-120">nodeID</span></span>  <br/> |<span data-ttu-id="c58ec-121">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="c58ec-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c58ec-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c58ec-122">See also</span></span>

[<span data-ttu-id="c58ec-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="c58ec-123">tblChat</span></span>](tblchat.md)
