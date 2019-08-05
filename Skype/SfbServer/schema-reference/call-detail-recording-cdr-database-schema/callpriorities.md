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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194850"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4e728-103">Tabella CallPriorities in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4e728-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4e728-104">La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".</span><span class="sxs-lookup"><span data-stu-id="4e728-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="4e728-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4e728-105">**Column**</span></span>|<span data-ttu-id="4e728-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="4e728-106">**Data Type**</span></span>|<span data-ttu-id="4e728-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="4e728-107">**Key/Index**</span></span>|<span data-ttu-id="4e728-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="4e728-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e728-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="4e728-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="4e728-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="4e728-110">tinyint</span></span>  <br/> |<span data-ttu-id="4e728-111">Principale</span><span class="sxs-lookup"><span data-stu-id="4e728-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="4e728-112">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="4e728-112">**Priority**</span></span> <br/> |<span data-ttu-id="4e728-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4e728-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="4e728-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="4e728-114">Allowed values:</span></span> <br/>  <span data-ttu-id="4e728-115">0-sconosciuto</span><span class="sxs-lookup"><span data-stu-id="4e728-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="4e728-116">1-non urgente</span><span class="sxs-lookup"><span data-stu-id="4e728-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="4e728-117">2-normale</span><span class="sxs-lookup"><span data-stu-id="4e728-117">2 - Normal</span></span> <br/>  <span data-ttu-id="4e728-118">3-urgente</span><span class="sxs-lookup"><span data-stu-id="4e728-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="4e728-119">4-emergenza</span><span class="sxs-lookup"><span data-stu-id="4e728-119">4 - Emergency</span></span> <br/> |
   

