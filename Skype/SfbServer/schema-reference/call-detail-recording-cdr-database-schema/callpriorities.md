---
title: Tabella CallPriorities in Skype for Business Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815444"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e2fed-103">Tabella CallPriorities in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e2fed-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2fed-104">La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".</span><span class="sxs-lookup"><span data-stu-id="e2fed-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="e2fed-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e2fed-105">**Column**</span></span>|<span data-ttu-id="e2fed-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e2fed-106">**Data Type**</span></span>|<span data-ttu-id="e2fed-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e2fed-107">**Key/Index**</span></span>|<span data-ttu-id="e2fed-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e2fed-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2fed-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="e2fed-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="e2fed-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e2fed-110">tinyint</span></span>  <br/> |<span data-ttu-id="e2fed-111">Principale</span><span class="sxs-lookup"><span data-stu-id="e2fed-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e2fed-112">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="e2fed-112">**Priority**</span></span> <br/> |<span data-ttu-id="e2fed-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2fed-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e2fed-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="e2fed-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e2fed-115">0-sconosciuto</span><span class="sxs-lookup"><span data-stu-id="e2fed-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="e2fed-116">1-non urgente</span><span class="sxs-lookup"><span data-stu-id="e2fed-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="e2fed-117">2-normale</span><span class="sxs-lookup"><span data-stu-id="e2fed-117">2 - Normal</span></span> <br/>  <span data-ttu-id="e2fed-118">3-urgente</span><span class="sxs-lookup"><span data-stu-id="e2fed-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="e2fed-119">4-emergenza</span><span class="sxs-lookup"><span data-stu-id="e2fed-119">4 - Emergency</span></span> <br/> |
   

