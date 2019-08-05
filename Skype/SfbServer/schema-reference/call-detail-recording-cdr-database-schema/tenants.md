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
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant. Ogni record nella tabella rappresenta un tenant.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194732"
---
# <a name="tenants-table"></a><span data-ttu-id="9a867-104">Tabella Tenants</span><span class="sxs-lookup"><span data-stu-id="9a867-104">Tenants table</span></span>
 
<span data-ttu-id="9a867-105">La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant.</span><span class="sxs-lookup"><span data-stu-id="9a867-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="9a867-106">Ogni record nella tabella rappresenta un tenant.</span><span class="sxs-lookup"><span data-stu-id="9a867-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a867-107">Nella distribuzione locale, CDR usa l'ID tenant di build-in per indicare il tipo di autenticazione diverso, ad esempio la connettività di messaggistica istantanea pubblica, federati e Anonymous.</span><span class="sxs-lookup"><span data-stu-id="9a867-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="9a867-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="9a867-108">**Column**</span></span>|<span data-ttu-id="9a867-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="9a867-109">**Data Type**</span></span>|<span data-ttu-id="9a867-110">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="9a867-110">**Key/Index**</span></span>|<span data-ttu-id="9a867-111">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="9a867-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a867-112">**ID tenant**</span><span class="sxs-lookup"><span data-stu-id="9a867-112">**TenantId**</span></span> <br/> |<span data-ttu-id="9a867-113">int</span><span class="sxs-lookup"><span data-stu-id="9a867-113">int</span></span>  <br/> |<span data-ttu-id="9a867-114">Principale</span><span class="sxs-lookup"><span data-stu-id="9a867-114">Primary</span></span>  <br/> |<span data-ttu-id="9a867-115">Numero univoco che identifica questo ID tenant.</span><span class="sxs-lookup"><span data-stu-id="9a867-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="9a867-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="9a867-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="9a867-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9a867-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9a867-118">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="9a867-118">Allowed values:</span></span> <br/>  <span data-ttu-id="9a867-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="9a867-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="9a867-120">00000000-0000-0000-0000-000000000001-federati</span><span class="sxs-lookup"><span data-stu-id="9a867-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="9a867-121">00000000-0000-0000-0000-000000000002-Anonimo</span><span class="sxs-lookup"><span data-stu-id="9a867-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="9a867-122">00000000-0000-0000-0000-000000000003-connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9a867-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

