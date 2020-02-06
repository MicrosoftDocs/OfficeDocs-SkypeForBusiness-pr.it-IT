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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812274"
---
# <a name="tblserveridentity"></a><span data-ttu-id="b4646-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="b4646-103">tblServerIdentity</span></span>
 
<span data-ttu-id="b4646-104">tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b4646-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="b4646-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4646-105">**Columns**</span></span>

|<span data-ttu-id="b4646-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b4646-106">**Column**</span></span>|<span data-ttu-id="b4646-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4646-107">**Type**</span></span>|<span data-ttu-id="b4646-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b4646-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4646-109">serverID</span><span class="sxs-lookup"><span data-stu-id="b4646-109">serverID</span></span>  <br/> |<span data-ttu-id="b4646-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4646-110">int, not null</span></span>  <br/> |<span data-ttu-id="b4646-111">ID server.</span><span class="sxs-lookup"><span data-stu-id="b4646-111">Server ID.</span></span> <span data-ttu-id="b4646-112">Corrisponde all'ID istanza di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="b4646-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="b4646-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="b4646-113">serverAddress</span></span>  <br/> |<span data-ttu-id="b4646-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="b4646-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b4646-115">Indirizzo del server tramite l'indirizzo di Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="b4646-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="b4646-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="b4646-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="b4646-117">DateTime</span><span class="sxs-lookup"><span data-stu-id="b4646-117">datetime</span></span>  <br/> |<span data-ttu-id="b4646-118">L'ultima volta che il Channel Server ha aggiornato questa riga per dare prova che è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4646-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="b4646-119">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="b4646-119">**Key**</span></span>

|<span data-ttu-id="b4646-120">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b4646-120">**Column**</span></span>|<span data-ttu-id="b4646-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b4646-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4646-122">serverID</span><span class="sxs-lookup"><span data-stu-id="b4646-122">serverID</span></span>  <br/> |<span data-ttu-id="b4646-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b4646-123">Primary key.</span></span>  <br/> |
   

