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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194574"
---
# <a name="subnet-table"></a><span data-ttu-id="e7c7c-104">Tabella Subnet</span><span class="sxs-lookup"><span data-stu-id="e7c7c-104">Subnet table</span></span>
 
<span data-ttu-id="e7c7c-105">La tabella subnet è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="e7c7c-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="e7c7c-106">Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="e7c7c-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="e7c7c-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-107">**Column**</span></span>|<span data-ttu-id="e7c7c-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-108">**Data Type**</span></span>|<span data-ttu-id="e7c7c-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-109">**Key/Index**</span></span>|<span data-ttu-id="e7c7c-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7c7c-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="e7c7c-112">int</span><span class="sxs-lookup"><span data-stu-id="e7c7c-112">int</span></span>  <br/> |<span data-ttu-id="e7c7c-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e7c7c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e7c7c-114">Rappresentazione Integer per l'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="e7c7c-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="e7c7c-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="e7c7c-116">int</span><span class="sxs-lookup"><span data-stu-id="e7c7c-116">int</span></span>  <br/> ||<span data-ttu-id="e7c7c-117">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="e7c7c-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="e7c7c-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="e7c7c-119">int</span><span class="sxs-lookup"><span data-stu-id="e7c7c-119">int</span></span>  <br/> |<span data-ttu-id="e7c7c-120">Esterna</span><span class="sxs-lookup"><span data-stu-id="e7c7c-120">Foreign</span></span>  <br/> |<span data-ttu-id="e7c7c-121">A cui si fa riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e7c7c-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="e7c7c-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="e7c7c-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="e7c7c-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="e7c7c-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="e7c7c-124">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="e7c7c-124">The description for the subnet.</span></span>  <br/> |
   

