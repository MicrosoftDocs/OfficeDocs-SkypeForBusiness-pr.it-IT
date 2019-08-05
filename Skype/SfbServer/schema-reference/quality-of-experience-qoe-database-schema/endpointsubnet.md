---
title: Tabella EndpointSubnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: La tabella EndpointSubnet è una tabella di supporto. Ogni record rappresenta una subnet acquisita dagli endpoint.
ms.openlocfilehash: b8a8e62178919da72082f99acad7798f3935a5ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194620"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="e470f-104">Tabella EndpointSubnet</span><span class="sxs-lookup"><span data-stu-id="e470f-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="e470f-105">La tabella EndpointSubnet è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="e470f-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="e470f-106">Ogni record rappresenta una subnet acquisita dagli endpoint.</span><span class="sxs-lookup"><span data-stu-id="e470f-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="e470f-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e470f-107">**Column**</span></span>|<span data-ttu-id="e470f-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e470f-108">**Data Type**</span></span>|<span data-ttu-id="e470f-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e470f-109">**Key/Index**</span></span>|<span data-ttu-id="e470f-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e470f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e470f-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="e470f-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="e470f-112">int</span><span class="sxs-lookup"><span data-stu-id="e470f-112">int</span></span>  <br/> |<span data-ttu-id="e470f-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e470f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e470f-114">Rappresentazione Integer per la subnet.</span><span class="sxs-lookup"><span data-stu-id="e470f-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="e470f-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e470f-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e470f-116">DateTime</span><span class="sxs-lookup"><span data-stu-id="e470f-116">datetime</span></span>  <br/> ||<span data-ttu-id="e470f-117">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="e470f-117">For internal use only.</span></span>  <br/> |
   

