---
title: Tabella Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabella Users è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un utente coinvolto in chiamate o sessioni con record nel database.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831616"
---
# <a name="users-table"></a><span data-ttu-id="ea34c-104">Tabella Users</span><span class="sxs-lookup"><span data-stu-id="ea34c-104">Users table</span></span>
 
<span data-ttu-id="ea34c-105">La tabella Users è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="ea34c-105">The Users table is a supporting table.</span></span> <span data-ttu-id="ea34c-106">In ogni record della tabella sono archiviate informazioni su un utente coinvolto in chiamate o sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="ea34c-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="ea34c-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ea34c-107">**Column**</span></span>|<span data-ttu-id="ea34c-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ea34c-108">**Data Type**</span></span>|<span data-ttu-id="ea34c-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="ea34c-109">**Key/Index**</span></span>|<span data-ttu-id="ea34c-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="ea34c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea34c-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ea34c-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ea34c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ea34c-112">datetime</span></span>  <br/> ||<span data-ttu-id="ea34c-113">Timestamp per uso interno.</span><span class="sxs-lookup"><span data-stu-id="ea34c-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="ea34c-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="ea34c-114">**UserId**</span></span> <br/> |<span data-ttu-id="ea34c-115">int</span><span class="sxs-lookup"><span data-stu-id="ea34c-115">int</span></span>  <br/> |<span data-ttu-id="ea34c-116">Principale</span><span class="sxs-lookup"><span data-stu-id="ea34c-116">Primary</span></span>  <br/> |<span data-ttu-id="ea34c-117">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="ea34c-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ea34c-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="ea34c-118">**UserUri**</span></span> <br/> |<span data-ttu-id="ea34c-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ea34c-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="ea34c-120">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea34c-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="ea34c-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="ea34c-121">**TenantId**</span></span> <br/> |<span data-ttu-id="ea34c-122">int</span><span class="sxs-lookup"><span data-stu-id="ea34c-122">int</span></span>  <br/> |<span data-ttu-id="ea34c-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="ea34c-123">Foreign</span></span>  <br/> |<span data-ttu-id="ea34c-124">ID tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea34c-124">This user's Tenant ID.</span></span> <span data-ttu-id="ea34c-125">Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants.</span><span class="sxs-lookup"><span data-stu-id="ea34c-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ea34c-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="ea34c-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="ea34c-127">int</span><span class="sxs-lookup"><span data-stu-id="ea34c-127">int</span></span>  <br/> |<span data-ttu-id="ea34c-128">Esterna</span><span class="sxs-lookup"><span data-stu-id="ea34c-128">Foreign</span></span>  <br/> |<span data-ttu-id="ea34c-129">Tipo di URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea34c-129">This user's URI type.</span></span> <span data-ttu-id="ea34c-130">Per altre [informazioni, vedi la tabella UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="ea34c-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

