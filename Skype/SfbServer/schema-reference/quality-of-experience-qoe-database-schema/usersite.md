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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194562"
---
# <a name="usersite-table"></a><span data-ttu-id="273bd-104">Tabella UserSite</span><span class="sxs-lookup"><span data-stu-id="273bd-104">UserSite table</span></span>
 
<span data-ttu-id="273bd-105">La tabella UserSite è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="273bd-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="273bd-106">Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="273bd-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="273bd-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="273bd-107">**Column**</span></span>|<span data-ttu-id="273bd-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="273bd-108">**Data Type**</span></span>|<span data-ttu-id="273bd-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="273bd-109">**Key/Index**</span></span>|<span data-ttu-id="273bd-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="273bd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="273bd-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="273bd-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="273bd-112">int</span><span class="sxs-lookup"><span data-stu-id="273bd-112">int</span></span>  <br/> |<span data-ttu-id="273bd-113">Principale</span><span class="sxs-lookup"><span data-stu-id="273bd-113">Primary</span></span>  <br/> |<span data-ttu-id="273bd-114">Numero univoco che identifica il sito utente.</span><span class="sxs-lookup"><span data-stu-id="273bd-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="273bd-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="273bd-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="273bd-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="273bd-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="273bd-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="273bd-117">Unique</span></span>  <br/> |<span data-ttu-id="273bd-118">Nome del sito utente.</span><span class="sxs-lookup"><span data-stu-id="273bd-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="273bd-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="273bd-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="273bd-120">int</span><span class="sxs-lookup"><span data-stu-id="273bd-120">int</span></span>  <br/> |<span data-ttu-id="273bd-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="273bd-121">Foreign</span></span>  <br/> |<span data-ttu-id="273bd-122">A cui si fa riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="273bd-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

