---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809886"
---
# <a name="tbladminlock"></a><span data-ttu-id="e84bf-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="e84bf-103">tblAdminLock</span></span>
 
<span data-ttu-id="e84bf-104">La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e84bf-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="e84bf-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e84bf-105">**Columns**</span></span>

|<span data-ttu-id="e84bf-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e84bf-106">**Column**</span></span>|<span data-ttu-id="e84bf-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e84bf-107">**Type**</span></span>|<span data-ttu-id="e84bf-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e84bf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e84bf-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="e84bf-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="e84bf-110">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="e84bf-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="e84bf-p101">Data e ora di scadenza del blocco. Il proprietario può estendere questo valore periodicamente.</span><span class="sxs-lookup"><span data-stu-id="e84bf-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="e84bf-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="e84bf-113">lockServerID</span></span>  <br/> |<span data-ttu-id="e84bf-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="e84bf-114">int, not null</span></span>  <br/> |<span data-ttu-id="e84bf-115">ID del server proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e84bf-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="e84bf-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="e84bf-116">lockActorID</span></span>  <br/> |<span data-ttu-id="e84bf-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="e84bf-117">int, not null</span></span>  <br/> |<span data-ttu-id="e84bf-118">ID dell'entità proprietaria del blocco.</span><span class="sxs-lookup"><span data-stu-id="e84bf-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

