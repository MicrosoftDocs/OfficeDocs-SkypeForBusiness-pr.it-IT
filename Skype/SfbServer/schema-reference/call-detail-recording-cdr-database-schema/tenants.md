---
title: Tabella Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant. Ogni record nella tabella rappresenta un tenant.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814854"
---
# <a name="tenants-table"></a><span data-ttu-id="d3149-104">Tabella Tenants</span><span class="sxs-lookup"><span data-stu-id="d3149-104">Tenants table</span></span>
 
<span data-ttu-id="d3149-105">La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant.</span><span class="sxs-lookup"><span data-stu-id="d3149-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="d3149-106">Ogni record nella tabella rappresenta un tenant.</span><span class="sxs-lookup"><span data-stu-id="d3149-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3149-107">Nella distribuzione locale, CDR usa l'ID tenant di build-in per indicare il tipo di autenticazione diverso, ad esempio la connettività di messaggistica istantanea pubblica, federati e Anonymous.</span><span class="sxs-lookup"><span data-stu-id="d3149-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="d3149-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d3149-108">**Column**</span></span>|<span data-ttu-id="d3149-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="d3149-109">**Data Type**</span></span>|<span data-ttu-id="d3149-110">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="d3149-110">**Key/Index**</span></span>|<span data-ttu-id="d3149-111">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="d3149-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3149-112">**ID tenant**</span><span class="sxs-lookup"><span data-stu-id="d3149-112">**TenantId**</span></span> <br/> |<span data-ttu-id="d3149-113">int</span><span class="sxs-lookup"><span data-stu-id="d3149-113">int</span></span>  <br/> |<span data-ttu-id="d3149-114">Principale</span><span class="sxs-lookup"><span data-stu-id="d3149-114">Primary</span></span>  <br/> |<span data-ttu-id="d3149-115">Numero univoco che identifica questo ID tenant.</span><span class="sxs-lookup"><span data-stu-id="d3149-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="d3149-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d3149-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="d3149-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3149-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d3149-118">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="d3149-118">Allowed values:</span></span> <br/>  <span data-ttu-id="d3149-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3149-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="d3149-120">00000000-0000-0000-0000-000000000001-federati</span><span class="sxs-lookup"><span data-stu-id="d3149-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="d3149-121">00000000-0000-0000-0000-000000000002-Anonimo</span><span class="sxs-lookup"><span data-stu-id="d3149-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="d3149-122">00000000-0000-0000-0000-000000000003-connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="d3149-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

