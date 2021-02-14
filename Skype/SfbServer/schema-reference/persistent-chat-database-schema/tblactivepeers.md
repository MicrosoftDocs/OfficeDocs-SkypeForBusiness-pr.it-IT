---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: In tblActivePeers sono incluse le connessioni peer-to-peer correnti tra i servizi chat.
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812936"
---
# <a name="tblactivepeers"></a><span data-ttu-id="2d22c-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="2d22c-103">tblActivePeers</span></span>
 
<span data-ttu-id="2d22c-104">In tblActivePeers sono incluse le connessioni peer-to-peer correnti tra i servizi chat.</span><span class="sxs-lookup"><span data-stu-id="2d22c-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="2d22c-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2d22c-105">**Columns**</span></span>

|<span data-ttu-id="2d22c-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2d22c-106">**Column**</span></span>|<span data-ttu-id="2d22c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2d22c-107">**Type**</span></span>|<span data-ttu-id="2d22c-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2d22c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d22c-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="2d22c-109">aplServerID</span></span>  <br/> |<span data-ttu-id="2d22c-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="2d22c-110">int, not null</span></span>  <br/> |<span data-ttu-id="2d22c-111">ID del server che ha inviato la voce.</span><span class="sxs-lookup"><span data-stu-id="2d22c-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="2d22c-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="2d22c-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="2d22c-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="2d22c-113">int, not null</span></span>  <br/> |<span data-ttu-id="2d22c-114">ID del peer a cui è connesso il server che esegue l'invio.</span><span class="sxs-lookup"><span data-stu-id="2d22c-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="2d22c-115">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="2d22c-115">**Keys**</span></span>

|<span data-ttu-id="2d22c-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2d22c-116">**Column**</span></span>|<span data-ttu-id="2d22c-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2d22c-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="2d22c-118">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="2d22c-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2d22c-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="2d22c-119">aplServerID</span></span>  <br/> |<span data-ttu-id="2d22c-120">Chiave esterna con ricerca nella tabella tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="2d22c-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="2d22c-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="2d22c-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="2d22c-122">Chiave esterna con ricerca nella tabella tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="2d22c-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

