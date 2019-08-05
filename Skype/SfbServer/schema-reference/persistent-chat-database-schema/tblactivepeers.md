---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene le connessioni peer-to-peer correnti tra i servizi di chat.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194706"
---
# <a name="tblactivepeers"></a><span data-ttu-id="a7596-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="a7596-103">tblActivePeers</span></span>
 
<span data-ttu-id="a7596-104">tblActivePeers contiene le connessioni peer-to-peer correnti tra i servizi di chat.</span><span class="sxs-lookup"><span data-stu-id="a7596-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="a7596-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a7596-105">**Columns**</span></span>

|<span data-ttu-id="a7596-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a7596-106">**Column**</span></span>|<span data-ttu-id="a7596-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a7596-107">**Type**</span></span>|<span data-ttu-id="a7596-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a7596-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7596-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a7596-109">aplServerID</span></span>  <br/> |<span data-ttu-id="a7596-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a7596-110">int, not null</span></span>  <br/> |<span data-ttu-id="a7596-111">ID del server che ha pubblicato la voce.</span><span class="sxs-lookup"><span data-stu-id="a7596-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="a7596-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a7596-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="a7596-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="a7596-113">int, not null</span></span>  <br/> |<span data-ttu-id="a7596-114">ID del peer a cui è connesso il server di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a7596-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="a7596-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="a7596-115">**Keys**</span></span>

|<span data-ttu-id="a7596-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a7596-116">**Column**</span></span>|<span data-ttu-id="a7596-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a7596-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7596-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="a7596-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="a7596-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="a7596-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a7596-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a7596-120">aplServerID</span></span>  <br/> |<span data-ttu-id="a7596-121">Chiave esterna con ricerca nella tabella tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="a7596-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="a7596-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a7596-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="a7596-123">Chiave esterna con ricerca nella tabella tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="a7596-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

