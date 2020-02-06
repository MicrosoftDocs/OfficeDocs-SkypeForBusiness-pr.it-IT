---
title: Tabella CallType in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabella CallType è una tabella statica in cui è archiviato l'elenco dei tipi di chiamata possibili.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815434"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="23f88-103">Tabella CallType in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="23f88-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23f88-104">La tabella CallType è una tabella statica in cui è archiviato l'elenco dei tipi di chiamata possibili.</span><span class="sxs-lookup"><span data-stu-id="23f88-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="23f88-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="23f88-105">**Column**</span></span>|<span data-ttu-id="23f88-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="23f88-106">**Data Type**</span></span>|<span data-ttu-id="23f88-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="23f88-107">**Key/Index**</span></span>|<span data-ttu-id="23f88-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="23f88-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23f88-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="23f88-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="23f88-110">int</span><span class="sxs-lookup"><span data-stu-id="23f88-110">int</span></span>  <br/> |<span data-ttu-id="23f88-111">Principale</span><span class="sxs-lookup"><span data-stu-id="23f88-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="23f88-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="23f88-112">**CallType**</span></span> <br/> |<span data-ttu-id="23f88-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="23f88-113">nvarchar</span></span>  <br/> || <span data-ttu-id="23f88-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="23f88-114">Allowed values:</span></span> <br/>  <span data-ttu-id="23f88-115">0--sconosciuto</span><span class="sxs-lookup"><span data-stu-id="23f88-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="23f88-116">1-messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="23f88-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="23f88-117">2--condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="23f88-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="23f88-118">3--audio</span><span class="sxs-lookup"><span data-stu-id="23f88-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="23f88-119">4-audio e video</span><span class="sxs-lookup"><span data-stu-id="23f88-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="23f88-120">5-trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="23f88-120">5 - File Transfer</span></span> <br/> |
   

