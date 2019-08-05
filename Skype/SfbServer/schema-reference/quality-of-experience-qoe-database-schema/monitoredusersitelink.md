---
title: Tabella MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194603"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="3246d-104">Tabella MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="3246d-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="3246d-105">La tabella MonitoredUserSiteLink è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="3246d-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="3246d-106">Ogni record rappresenta un collegamento tra due siti utente.</span><span class="sxs-lookup"><span data-stu-id="3246d-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="3246d-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3246d-107">**Column**</span></span>|<span data-ttu-id="3246d-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="3246d-108">**Data Type**</span></span>|<span data-ttu-id="3246d-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="3246d-109">**Key/Index**</span></span>|<span data-ttu-id="3246d-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3246d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3246d-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="3246d-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="3246d-112">int</span><span class="sxs-lookup"><span data-stu-id="3246d-112">int</span></span>  <br/> |<span data-ttu-id="3246d-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="3246d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3246d-114">A cui si fa riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="3246d-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="3246d-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="3246d-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="3246d-116">int</span><span class="sxs-lookup"><span data-stu-id="3246d-116">int</span></span>  <br/> |<span data-ttu-id="3246d-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="3246d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3246d-118">Riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="3246d-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

