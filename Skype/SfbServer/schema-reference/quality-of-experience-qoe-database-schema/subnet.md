---
title: Tabella Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805204"
---
# <a name="subnet-table"></a><span data-ttu-id="10355-104">Tabella Subnet</span><span class="sxs-lookup"><span data-stu-id="10355-104">Subnet table</span></span>
 
<span data-ttu-id="10355-105">La tabella subnet è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="10355-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="10355-106">Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="10355-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="10355-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="10355-107">**Column**</span></span>|<span data-ttu-id="10355-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="10355-108">**Data Type**</span></span>|<span data-ttu-id="10355-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="10355-109">**Key/Index**</span></span>|<span data-ttu-id="10355-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="10355-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10355-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="10355-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="10355-112">int</span><span class="sxs-lookup"><span data-stu-id="10355-112">int</span></span>  <br/> |<span data-ttu-id="10355-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="10355-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="10355-114">Rappresentazione Integer per l'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="10355-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="10355-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="10355-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="10355-116">int</span><span class="sxs-lookup"><span data-stu-id="10355-116">int</span></span>  <br/> ||<span data-ttu-id="10355-117">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="10355-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="10355-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="10355-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="10355-119">int</span><span class="sxs-lookup"><span data-stu-id="10355-119">int</span></span>  <br/> |<span data-ttu-id="10355-120">Esterna</span><span class="sxs-lookup"><span data-stu-id="10355-120">Foreign</span></span>  <br/> |<span data-ttu-id="10355-121">A cui si fa riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="10355-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="10355-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="10355-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="10355-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="10355-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="10355-124">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="10355-124">The description for the subnet.</span></span>  <br/> |
   

