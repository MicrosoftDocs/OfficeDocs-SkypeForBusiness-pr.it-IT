---
title: Tabella Gateways in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821586"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="176da-104">Tabella Gateways in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="176da-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="176da-105">La tabella Gateways è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="176da-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="176da-106">In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.</span><span class="sxs-lookup"><span data-stu-id="176da-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="176da-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="176da-107">**Column**</span></span>|<span data-ttu-id="176da-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="176da-108">**Data Type**</span></span>|<span data-ttu-id="176da-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="176da-109">**Key/Index**</span></span>|<span data-ttu-id="176da-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="176da-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="176da-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="176da-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="176da-112">int</span><span class="sxs-lookup"><span data-stu-id="176da-112">int</span></span>  <br/> |<span data-ttu-id="176da-113">Principale</span><span class="sxs-lookup"><span data-stu-id="176da-113">Primary</span></span>  <br/> |<span data-ttu-id="176da-114">Numero univoco che identifica il gateway.</span><span class="sxs-lookup"><span data-stu-id="176da-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="176da-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="176da-115">**Gateway**</span></span> <br/> |<span data-ttu-id="176da-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="176da-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="176da-117">Nome gateway.</span><span class="sxs-lookup"><span data-stu-id="176da-117">Gateway name.</span></span>  <br/> |
   

