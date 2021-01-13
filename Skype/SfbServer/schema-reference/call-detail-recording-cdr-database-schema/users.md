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
description: La tabella Users è una tabella di supporto. Ogni record nella tabella archivia le informazioni su un utente coinvolto nelle chiamate o nelle sessioni con record nel database.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831616"
---
# <a name="users-table"></a><span data-ttu-id="32070-104">Tabella Users</span><span class="sxs-lookup"><span data-stu-id="32070-104">Users table</span></span>
 
<span data-ttu-id="32070-105">La tabella Users è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="32070-105">The Users table is a supporting table.</span></span> <span data-ttu-id="32070-106">Ogni record nella tabella archivia le informazioni su un utente coinvolto nelle chiamate o nelle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="32070-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="32070-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="32070-107">**Column**</span></span>|<span data-ttu-id="32070-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="32070-108">**Data Type**</span></span>|<span data-ttu-id="32070-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="32070-109">**Key/Index**</span></span>|<span data-ttu-id="32070-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="32070-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32070-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="32070-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="32070-112">datetime</span><span class="sxs-lookup"><span data-stu-id="32070-112">datetime</span></span>  <br/> ||<span data-ttu-id="32070-113">Indicatore di data e ora per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="32070-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="32070-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="32070-114">**UserId**</span></span> <br/> |<span data-ttu-id="32070-115">int</span><span class="sxs-lookup"><span data-stu-id="32070-115">int</span></span>  <br/> |<span data-ttu-id="32070-116">Principale</span><span class="sxs-lookup"><span data-stu-id="32070-116">Primary</span></span>  <br/> |<span data-ttu-id="32070-117">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="32070-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="32070-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="32070-118">**UserUri**</span></span> <br/> |<span data-ttu-id="32070-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32070-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="32070-120">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32070-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="32070-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="32070-121">**TenantId**</span></span> <br/> |<span data-ttu-id="32070-122">int</span><span class="sxs-lookup"><span data-stu-id="32070-122">int</span></span>  <br/> |<span data-ttu-id="32070-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="32070-123">Foreign</span></span>  <br/> |<span data-ttu-id="32070-124">ID tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32070-124">This user's Tenant ID.</span></span> <span data-ttu-id="32070-125">Per ulteriori informazioni, vedere la [tabella tenant](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="32070-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="32070-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="32070-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="32070-127">int</span><span class="sxs-lookup"><span data-stu-id="32070-127">int</span></span>  <br/> |<span data-ttu-id="32070-128">Stranieri</span><span class="sxs-lookup"><span data-stu-id="32070-128">Foreign</span></span>  <br/> |<span data-ttu-id="32070-129">Tipo di URI di questo utente.</span><span class="sxs-lookup"><span data-stu-id="32070-129">This user's URI type.</span></span> <span data-ttu-id="32070-130">Per ulteriori informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="32070-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

