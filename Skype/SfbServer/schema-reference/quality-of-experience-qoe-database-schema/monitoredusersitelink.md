---
title: Tabella MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806356"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="68dfd-104">Tabella MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="68dfd-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="68dfd-p102">La tabella MonitoredUserSiteLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due siti utente.</span><span class="sxs-lookup"><span data-stu-id="68dfd-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="68dfd-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="68dfd-107">**Column**</span></span>|<span data-ttu-id="68dfd-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="68dfd-108">**Data Type**</span></span>|<span data-ttu-id="68dfd-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="68dfd-109">**Key/Index**</span></span>|<span data-ttu-id="68dfd-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="68dfd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="68dfd-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="68dfd-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="68dfd-112">int</span><span class="sxs-lookup"><span data-stu-id="68dfd-112">int</span></span>  <br/> |<span data-ttu-id="68dfd-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="68dfd-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="68dfd-114">Riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="68dfd-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="68dfd-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="68dfd-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="68dfd-116">int</span><span class="sxs-lookup"><span data-stu-id="68dfd-116">int</span></span>  <br/> |<span data-ttu-id="68dfd-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="68dfd-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="68dfd-118">Riferimento dalla [tabella UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="68dfd-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

