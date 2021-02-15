---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831496"
---
# <a name="tblserveridentity"></a><span data-ttu-id="13ef4-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="13ef4-103">tblServerIdentity</span></span>
 
<span data-ttu-id="13ef4-104">tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="13ef4-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="13ef4-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="13ef4-105">**Columns**</span></span>

|<span data-ttu-id="13ef4-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="13ef4-106">**Column**</span></span>|<span data-ttu-id="13ef4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="13ef4-107">**Type**</span></span>|<span data-ttu-id="13ef4-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="13ef4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13ef4-109">serverID</span><span class="sxs-lookup"><span data-stu-id="13ef4-109">serverID</span></span>  <br/> |<span data-ttu-id="13ef4-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="13ef4-110">int, not null</span></span>  <br/> |<span data-ttu-id="13ef4-111">ID del server.</span><span class="sxs-lookup"><span data-stu-id="13ef4-111">Server ID.</span></span> <span data-ttu-id="13ef4-112">Corrisponde all'ID istanza dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="13ef4-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="13ef4-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="13ef4-113">serverAddress</span></span>  <br/> |<span data-ttu-id="13ef4-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="13ef4-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="13ef4-115">Indirizzo del server che usa l'indirizzo di Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="13ef4-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="13ef4-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="13ef4-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="13ef4-117">datetime</span><span class="sxs-lookup"><span data-stu-id="13ef4-117">datetime</span></span>  <br/> |<span data-ttu-id="13ef4-118">Ora dell'ultimo aggiornamento di questa riga eseguito dal Channel Server per confermare che è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="13ef4-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="13ef4-119">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="13ef4-119">**Key**</span></span>

|<span data-ttu-id="13ef4-120">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="13ef4-120">**Column**</span></span>|<span data-ttu-id="13ef4-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="13ef4-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13ef4-122">serverID</span><span class="sxs-lookup"><span data-stu-id="13ef4-122">serverID</span></span>  <br/> |<span data-ttu-id="13ef4-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="13ef4-123">Primary key.</span></span>  <br/> |
   

