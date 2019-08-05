---
title: Tabella gateway in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabella Gateways è una tabella di supporto. Ogni record archivia le informazioni relative a un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194796"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a732a-104">Tabella gateway in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a732a-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a732a-105">La tabella Gateways è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="a732a-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="a732a-106">Ogni record archivia le informazioni relative a un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.</span><span class="sxs-lookup"><span data-stu-id="a732a-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="a732a-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a732a-107">**Column**</span></span>|<span data-ttu-id="a732a-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a732a-108">**Data Type**</span></span>|<span data-ttu-id="a732a-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="a732a-109">**Key/Index**</span></span>|<span data-ttu-id="a732a-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a732a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a732a-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="a732a-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="a732a-112">int</span><span class="sxs-lookup"><span data-stu-id="a732a-112">int</span></span>  <br/> |<span data-ttu-id="a732a-113">Principale</span><span class="sxs-lookup"><span data-stu-id="a732a-113">Primary</span></span>  <br/> |<span data-ttu-id="a732a-114">Numero univoco che identifica questo gateway.</span><span class="sxs-lookup"><span data-stu-id="a732a-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="a732a-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="a732a-115">**Gateway**</span></span> <br/> |<span data-ttu-id="a732a-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a732a-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="a732a-117">Nome del gateway.</span><span class="sxs-lookup"><span data-stu-id="a732a-117">Gateway name.</span></span>  <br/> |
   

