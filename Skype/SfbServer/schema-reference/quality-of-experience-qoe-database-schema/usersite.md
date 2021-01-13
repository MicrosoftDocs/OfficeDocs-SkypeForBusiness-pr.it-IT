---
title: Tabella UserSite
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799916"
---
# <a name="usersite-table"></a><span data-ttu-id="cbca8-104">Tabella UserSite</span><span class="sxs-lookup"><span data-stu-id="cbca8-104">UserSite table</span></span>
 
<span data-ttu-id="cbca8-p102">La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="cbca8-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="cbca8-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="cbca8-107">**Column**</span></span>|<span data-ttu-id="cbca8-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="cbca8-108">**Data Type**</span></span>|<span data-ttu-id="cbca8-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="cbca8-109">**Key/Index**</span></span>|<span data-ttu-id="cbca8-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="cbca8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbca8-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="cbca8-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="cbca8-112">int</span><span class="sxs-lookup"><span data-stu-id="cbca8-112">int</span></span>  <br/> |<span data-ttu-id="cbca8-113">Principale</span><span class="sxs-lookup"><span data-stu-id="cbca8-113">Primary</span></span>  <br/> |<span data-ttu-id="cbca8-114">Numero univoco che identifica il sito utente.</span><span class="sxs-lookup"><span data-stu-id="cbca8-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="cbca8-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="cbca8-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="cbca8-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="cbca8-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="cbca8-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="cbca8-117">Unique</span></span>  <br/> |<span data-ttu-id="cbca8-118">Nome del sito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cbca8-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="cbca8-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="cbca8-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="cbca8-120">int</span><span class="sxs-lookup"><span data-stu-id="cbca8-120">int</span></span>  <br/> |<span data-ttu-id="cbca8-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cbca8-121">Foreign</span></span>  <br/> |<span data-ttu-id="cbca8-122">A cui viene fatto riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="cbca8-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

