---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814694"
---
# <a name="tbladminlock"></a><span data-ttu-id="76894-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="76894-103">tblAdminLock</span></span>
 
<span data-ttu-id="76894-104">tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="76894-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="76894-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="76894-105">**Columns**</span></span>

|<span data-ttu-id="76894-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="76894-106">**Column**</span></span>|<span data-ttu-id="76894-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="76894-107">**Type**</span></span>|<span data-ttu-id="76894-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="76894-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76894-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="76894-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="76894-110">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="76894-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="76894-111">Bloccare la data e l'ora di scadenza.</span><span class="sxs-lookup"><span data-stu-id="76894-111">Lock expiration date and time.</span></span> <span data-ttu-id="76894-112">Il proprietario può estendere questo valore periodicamente.</span><span class="sxs-lookup"><span data-stu-id="76894-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="76894-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="76894-113">lockServerID</span></span>  <br/> |<span data-ttu-id="76894-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="76894-114">int, not null</span></span>  <br/> |<span data-ttu-id="76894-115">ID del server che possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="76894-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="76894-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="76894-116">lockActorID</span></span>  <br/> |<span data-ttu-id="76894-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="76894-117">int, not null</span></span>  <br/> |<span data-ttu-id="76894-118">ID dell'entità che possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="76894-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

