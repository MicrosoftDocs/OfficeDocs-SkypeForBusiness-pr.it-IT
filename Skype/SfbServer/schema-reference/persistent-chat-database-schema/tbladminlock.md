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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194702"
---
# <a name="tbladminlock"></a><span data-ttu-id="b7660-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="b7660-103">tblAdminLock</span></span>
 
<span data-ttu-id="b7660-104">tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b7660-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="b7660-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b7660-105">**Columns**</span></span>

|<span data-ttu-id="b7660-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b7660-106">**Column**</span></span>|<span data-ttu-id="b7660-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b7660-107">**Type**</span></span>|<span data-ttu-id="b7660-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b7660-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7660-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="b7660-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="b7660-110">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="b7660-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="b7660-111">Bloccare la data e l'ora di scadenza.</span><span class="sxs-lookup"><span data-stu-id="b7660-111">Lock expiration date and time.</span></span> <span data-ttu-id="b7660-112">Il proprietario può estendere questo valore periodicamente.</span><span class="sxs-lookup"><span data-stu-id="b7660-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="b7660-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="b7660-113">lockServerID</span></span>  <br/> |<span data-ttu-id="b7660-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="b7660-114">int, not null</span></span>  <br/> |<span data-ttu-id="b7660-115">ID del server che possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b7660-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="b7660-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="b7660-116">lockActorID</span></span>  <br/> |<span data-ttu-id="b7660-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="b7660-117">int, not null</span></span>  <br/> |<span data-ttu-id="b7660-118">ID dell'entità che possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b7660-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

