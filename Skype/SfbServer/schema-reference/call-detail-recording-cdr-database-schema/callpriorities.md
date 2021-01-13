---
title: Tabella CallPriorities in Skype for Business Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio ' Emergency ',' urgente ' o ' Normal '.
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813436"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1bc7a-103">Tabella CallPriorities in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1bc7a-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1bc7a-104">La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio ' Emergency ',' urgente ' o ' Normal '.</span><span class="sxs-lookup"><span data-stu-id="1bc7a-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="1bc7a-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1bc7a-105">**Column**</span></span>|<span data-ttu-id="1bc7a-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="1bc7a-106">**Data Type**</span></span>|<span data-ttu-id="1bc7a-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="1bc7a-107">**Key/Index**</span></span>|<span data-ttu-id="1bc7a-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="1bc7a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bc7a-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="1bc7a-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="1bc7a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1bc7a-110">tinyint</span></span>  <br/> |<span data-ttu-id="1bc7a-111">Principale</span><span class="sxs-lookup"><span data-stu-id="1bc7a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1bc7a-112">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1bc7a-112">**Priority**</span></span> <br/> |<span data-ttu-id="1bc7a-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1bc7a-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1bc7a-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="1bc7a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1bc7a-115">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="1bc7a-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="1bc7a-116">1-non urgente</span><span class="sxs-lookup"><span data-stu-id="1bc7a-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="1bc7a-117">2 - Normale</span><span class="sxs-lookup"><span data-stu-id="1bc7a-117">2 - Normal</span></span> <br/>  <span data-ttu-id="1bc7a-118">3 - Urgente</span><span class="sxs-lookup"><span data-stu-id="1bc7a-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="1bc7a-119">4 - Emergenza</span><span class="sxs-lookup"><span data-stu-id="1bc7a-119">4 - Emergency</span></span> <br/> |
   

