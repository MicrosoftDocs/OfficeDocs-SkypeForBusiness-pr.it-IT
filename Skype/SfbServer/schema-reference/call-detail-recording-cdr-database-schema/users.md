---
title: Tabella Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabella utenti è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814804"
---
# <a name="users-table"></a><span data-ttu-id="3e0d8-104">Tabella Users</span><span class="sxs-lookup"><span data-stu-id="3e0d8-104">Users table</span></span>
 
<span data-ttu-id="3e0d8-105">La tabella utenti è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-105">The Users table is a supporting table.</span></span> <span data-ttu-id="3e0d8-106">Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="3e0d8-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-107">**Column**</span></span>|<span data-ttu-id="3e0d8-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-108">**Data Type**</span></span>|<span data-ttu-id="3e0d8-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-109">**Key/Index**</span></span>|<span data-ttu-id="3e0d8-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3e0d8-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3e0d8-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e0d8-112">datetime</span></span>  <br/> ||<span data-ttu-id="3e0d8-113">Indicatore di data e ora per uso interno.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="3e0d8-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-114">**UserId**</span></span> <br/> |<span data-ttu-id="3e0d8-115">int</span><span class="sxs-lookup"><span data-stu-id="3e0d8-115">int</span></span>  <br/> |<span data-ttu-id="3e0d8-116">Principale</span><span class="sxs-lookup"><span data-stu-id="3e0d8-116">Primary</span></span>  <br/> |<span data-ttu-id="3e0d8-117">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="3e0d8-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-118">**UserUri**</span></span> <br/> |<span data-ttu-id="3e0d8-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3e0d8-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="3e0d8-120">URI utente.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="3e0d8-121">**ID tenant**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-121">**TenantId**</span></span> <br/> |<span data-ttu-id="3e0d8-122">int</span><span class="sxs-lookup"><span data-stu-id="3e0d8-122">int</span></span>  <br/> |<span data-ttu-id="3e0d8-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="3e0d8-123">Foreign</span></span>  <br/> |<span data-ttu-id="3e0d8-124">ID tenant di questo utente.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-124">This user's Tenant ID.</span></span> <span data-ttu-id="3e0d8-125">Per altre informazioni, vedere la [tabella tenant](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="3e0d8-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3e0d8-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="3e0d8-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="3e0d8-127">int</span><span class="sxs-lookup"><span data-stu-id="3e0d8-127">int</span></span>  <br/> |<span data-ttu-id="3e0d8-128">Esterna</span><span class="sxs-lookup"><span data-stu-id="3e0d8-128">Foreign</span></span>  <br/> |<span data-ttu-id="3e0d8-129">Tipo di URI di questo utente.</span><span class="sxs-lookup"><span data-stu-id="3e0d8-129">This user's URI type.</span></span> <span data-ttu-id="3e0d8-130">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="3e0d8-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

