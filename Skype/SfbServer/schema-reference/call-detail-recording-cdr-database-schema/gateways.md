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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabella Gateways è una tabella di supporto. Ogni record archivia le informazioni relative a un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815164"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="07bc2-104">Tabella gateway in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="07bc2-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07bc2-105">La tabella Gateways è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="07bc2-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="07bc2-106">Ogni record archivia le informazioni relative a un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.</span><span class="sxs-lookup"><span data-stu-id="07bc2-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="07bc2-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="07bc2-107">**Column**</span></span>|<span data-ttu-id="07bc2-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="07bc2-108">**Data Type**</span></span>|<span data-ttu-id="07bc2-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="07bc2-109">**Key/Index**</span></span>|<span data-ttu-id="07bc2-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="07bc2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07bc2-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="07bc2-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="07bc2-112">int</span><span class="sxs-lookup"><span data-stu-id="07bc2-112">int</span></span>  <br/> |<span data-ttu-id="07bc2-113">Principale</span><span class="sxs-lookup"><span data-stu-id="07bc2-113">Primary</span></span>  <br/> |<span data-ttu-id="07bc2-114">Numero univoco che identifica questo gateway.</span><span class="sxs-lookup"><span data-stu-id="07bc2-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="07bc2-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="07bc2-115">**Gateway**</span></span> <br/> |<span data-ttu-id="07bc2-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="07bc2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="07bc2-117">Nome del gateway.</span><span class="sxs-lookup"><span data-stu-id="07bc2-117">Gateway name.</span></span>  <br/> |
   

