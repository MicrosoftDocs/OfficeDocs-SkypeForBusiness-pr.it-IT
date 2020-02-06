---
title: Tabella UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805004"
---
# <a name="usersite-table"></a><span data-ttu-id="8b3e5-104">Tabella UserSite</span><span class="sxs-lookup"><span data-stu-id="8b3e5-104">UserSite table</span></span>
 
<span data-ttu-id="8b3e5-105">La tabella UserSite è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="8b3e5-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="8b3e5-106">Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="8b3e5-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="8b3e5-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-107">**Column**</span></span>|<span data-ttu-id="8b3e5-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-108">**Data Type**</span></span>|<span data-ttu-id="8b3e5-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-109">**Key/Index**</span></span>|<span data-ttu-id="8b3e5-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b3e5-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="8b3e5-112">int</span><span class="sxs-lookup"><span data-stu-id="8b3e5-112">int</span></span>  <br/> |<span data-ttu-id="8b3e5-113">Principale</span><span class="sxs-lookup"><span data-stu-id="8b3e5-113">Primary</span></span>  <br/> |<span data-ttu-id="8b3e5-114">Numero univoco che identifica il sito utente.</span><span class="sxs-lookup"><span data-stu-id="8b3e5-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="8b3e5-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="8b3e5-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="8b3e5-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="8b3e5-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="8b3e5-117">Unique</span></span>  <br/> |<span data-ttu-id="8b3e5-118">Nome del sito utente.</span><span class="sxs-lookup"><span data-stu-id="8b3e5-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="8b3e5-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="8b3e5-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="8b3e5-120">int</span><span class="sxs-lookup"><span data-stu-id="8b3e5-120">int</span></span>  <br/> |<span data-ttu-id="8b3e5-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="8b3e5-121">Foreign</span></span>  <br/> |<span data-ttu-id="8b3e5-122">A cui si fa riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e5-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

