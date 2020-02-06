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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807794"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="31d46-104">Tabella MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="31d46-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="31d46-105">La tabella MonitoredUserSiteLink è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="31d46-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="31d46-106">Ogni record rappresenta un collegamento tra due siti utente.</span><span class="sxs-lookup"><span data-stu-id="31d46-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="31d46-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="31d46-107">**Column**</span></span>|<span data-ttu-id="31d46-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="31d46-108">**Data Type**</span></span>|<span data-ttu-id="31d46-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="31d46-109">**Key/Index**</span></span>|<span data-ttu-id="31d46-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="31d46-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="31d46-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="31d46-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="31d46-112">int</span><span class="sxs-lookup"><span data-stu-id="31d46-112">int</span></span>  <br/> |<span data-ttu-id="31d46-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="31d46-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="31d46-114">A cui si fa riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="31d46-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="31d46-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="31d46-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="31d46-116">int</span><span class="sxs-lookup"><span data-stu-id="31d46-116">int</span></span>  <br/> |<span data-ttu-id="31d46-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="31d46-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="31d46-118">Riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="31d46-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

