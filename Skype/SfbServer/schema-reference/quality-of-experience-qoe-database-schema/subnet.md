---
title: Tabella Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831336"
---
# <a name="subnet-table"></a><span data-ttu-id="b767b-104">Tabella Subnet</span><span class="sxs-lookup"><span data-stu-id="b767b-104">Subnet table</span></span>
 
<span data-ttu-id="b767b-p102">La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="b767b-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="b767b-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b767b-107">**Column**</span></span>|<span data-ttu-id="b767b-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b767b-108">**Data Type**</span></span>|<span data-ttu-id="b767b-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="b767b-109">**Key/Index**</span></span>|<span data-ttu-id="b767b-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b767b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b767b-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="b767b-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="b767b-112">int</span><span class="sxs-lookup"><span data-stu-id="b767b-112">int</span></span>  <br/> |<span data-ttu-id="b767b-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="b767b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b767b-114">Rappresentazione in forma di numero intero dell'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="b767b-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="b767b-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="b767b-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="b767b-116">int</span><span class="sxs-lookup"><span data-stu-id="b767b-116">int</span></span>  <br/> ||<span data-ttu-id="b767b-117">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="b767b-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="b767b-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="b767b-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="b767b-119">int</span><span class="sxs-lookup"><span data-stu-id="b767b-119">int</span></span>  <br/> |<span data-ttu-id="b767b-120">Esterna</span><span class="sxs-lookup"><span data-stu-id="b767b-120">Foreign</span></span>  <br/> |<span data-ttu-id="b767b-121">Riferimento dalla [tabella UserSite.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="b767b-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="b767b-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="b767b-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="b767b-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="b767b-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="b767b-124">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="b767b-124">The description for the subnet.</span></span>  <br/> |
   

