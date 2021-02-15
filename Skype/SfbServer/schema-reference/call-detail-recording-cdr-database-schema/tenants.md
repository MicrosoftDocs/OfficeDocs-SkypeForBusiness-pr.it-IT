---
title: Tabella Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabella Tenants è una tabella di supporto in cui viene archiviato un elenco dei diversi tenant. Ogni record della tabella rappresenta un tenant.
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831716"
---
# <a name="tenants-table"></a><span data-ttu-id="d9007-104">Tabella Tenants</span><span class="sxs-lookup"><span data-stu-id="d9007-104">Tenants table</span></span>
 
<span data-ttu-id="d9007-p102">La tabella Tenants è una tabella di supporto in cui viene archiviato un elenco dei diversi tenant. Ogni record della tabella rappresenta un tenant.</span><span class="sxs-lookup"><span data-stu-id="d9007-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9007-107">Nelle distribuzioni on-premise, registrazione dettagli chiamata utilizza l'ID tenant predefinito per indicare tipi di autenticazione diversi, come connettività per messaggistica istantanea pubblica, autenticazione federata e autenticazione anonima.</span><span class="sxs-lookup"><span data-stu-id="d9007-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="d9007-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d9007-108">**Column**</span></span>|<span data-ttu-id="d9007-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="d9007-109">**Data Type**</span></span>|<span data-ttu-id="d9007-110">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="d9007-110">**Key/Index**</span></span>|<span data-ttu-id="d9007-111">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="d9007-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9007-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="d9007-112">**TenantId**</span></span> <br/> |<span data-ttu-id="d9007-113">int</span><span class="sxs-lookup"><span data-stu-id="d9007-113">int</span></span>  <br/> |<span data-ttu-id="d9007-114">Principale</span><span class="sxs-lookup"><span data-stu-id="d9007-114">Primary</span></span>  <br/> |<span data-ttu-id="d9007-115">Numero univoco che identifica questo ID tenant.</span><span class="sxs-lookup"><span data-stu-id="d9007-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="d9007-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d9007-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="d9007-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d9007-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d9007-118">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="d9007-118">Allowed values:</span></span> <br/>  <span data-ttu-id="d9007-119">000000000-0000-0000-0000-000000000000 - Enterprise</span><span class="sxs-lookup"><span data-stu-id="d9007-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="d9007-120">000000000-0000-0000-0000-000000000001 - Federato</span><span class="sxs-lookup"><span data-stu-id="d9007-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="d9007-121">000000000-0000-0000-0000-000000000002 - Anonimo</span><span class="sxs-lookup"><span data-stu-id="d9007-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="d9007-122">00000000-0000-0000-0000-0000000000003 - Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="d9007-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

