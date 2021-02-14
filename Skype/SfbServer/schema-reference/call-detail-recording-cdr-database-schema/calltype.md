---
title: Tabella CallType in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabella CallType è una tabella statica in cui viene archiviato l'elenco dei tipi di chiamata possibili.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813366"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c144f-103">Tabella CallType in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c144f-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c144f-104">La tabella CallType è una tabella statica in cui viene archiviato l'elenco dei tipi di chiamata possibili.</span><span class="sxs-lookup"><span data-stu-id="c144f-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="c144f-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c144f-105">**Column**</span></span>|<span data-ttu-id="c144f-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="c144f-106">**Data Type**</span></span>|<span data-ttu-id="c144f-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="c144f-107">**Key/Index**</span></span>|<span data-ttu-id="c144f-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c144f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c144f-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="c144f-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="c144f-110">int</span><span class="sxs-lookup"><span data-stu-id="c144f-110">int</span></span>  <br/> |<span data-ttu-id="c144f-111">Principale</span><span class="sxs-lookup"><span data-stu-id="c144f-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="c144f-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="c144f-112">**CallType**</span></span> <br/> |<span data-ttu-id="c144f-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="c144f-113">nvarchar</span></span>  <br/> || <span data-ttu-id="c144f-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="c144f-114">Allowed values:</span></span> <br/>  <span data-ttu-id="c144f-115">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="c144f-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="c144f-116">1 - Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="c144f-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="c144f-117">2 - Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="c144f-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="c144f-118">3 - Audio</span><span class="sxs-lookup"><span data-stu-id="c144f-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="c144f-119">4 - Audio e Video</span><span class="sxs-lookup"><span data-stu-id="c144f-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="c144f-120">5 - Trasferimento file</span><span class="sxs-lookup"><span data-stu-id="c144f-120">5 - File Transfer</span></span> <br/> |
   

