---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194655"
---
# <a name="tblserveridentity"></a><span data-ttu-id="e4cf0-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="e4cf0-103">tblServerIdentity</span></span>
 
<span data-ttu-id="e4cf0-104">tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="e4cf0-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-105">**Columns**</span></span>

|<span data-ttu-id="e4cf0-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-106">**Column**</span></span>|<span data-ttu-id="e4cf0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-107">**Type**</span></span>|<span data-ttu-id="e4cf0-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4cf0-109">serverID</span><span class="sxs-lookup"><span data-stu-id="e4cf0-109">serverID</span></span>  <br/> |<span data-ttu-id="e4cf0-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e4cf0-110">int, not null</span></span>  <br/> |<span data-ttu-id="e4cf0-111">ID server.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-111">Server ID.</span></span> <span data-ttu-id="e4cf0-112">Corrisponde all'ID istanza di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="e4cf0-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="e4cf0-113">serverAddress</span></span>  <br/> |<span data-ttu-id="e4cf0-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="e4cf0-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e4cf0-115">Indirizzo del server tramite l'indirizzo di Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="e4cf0-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="e4cf0-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="e4cf0-117">DateTime</span><span class="sxs-lookup"><span data-stu-id="e4cf0-117">datetime</span></span>  <br/> |<span data-ttu-id="e4cf0-118">L'ultima volta che il Channel Server ha aggiornato questa riga per dare prova che è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="e4cf0-119">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-119">**Key**</span></span>

|<span data-ttu-id="e4cf0-120">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-120">**Column**</span></span>|<span data-ttu-id="e4cf0-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e4cf0-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e4cf0-122">serverID</span><span class="sxs-lookup"><span data-stu-id="e4cf0-122">serverID</span></span>  <br/> |<span data-ttu-id="e4cf0-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-123">Primary key.</span></span>  <br/> |
   

