---
title: Tabella CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabella CodecDescription associa identificatori di codec univoci al relativo codec. I codec vengono usati per codificare i segnali digitali per la trasmissione e la trasmissione e quindi per decodificare i segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810364"
---
# <a name="codecdescription-table"></a><span data-ttu-id="a23c1-105">Tabella CodecDescription</span><span class="sxs-lookup"><span data-stu-id="a23c1-105">CodecDescription table</span></span>
 
<span data-ttu-id="a23c1-106">La tabella CodecDescription associa identificatori di codec univoci al relativo codec.</span><span class="sxs-lookup"><span data-stu-id="a23c1-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="a23c1-107">I codec vengono usati per codificare i segnali digitali per la trasmissione e la trasmissione e quindi per decodificare i segnali per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="a23c1-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="a23c1-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a23c1-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="a23c1-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a23c1-109">**Column**</span></span>|<span data-ttu-id="a23c1-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a23c1-110">**Data Type**</span></span>|<span data-ttu-id="a23c1-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="a23c1-111">**Key/Index**</span></span>|<span data-ttu-id="a23c1-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a23c1-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a23c1-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="a23c1-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="a23c1-114">smallint</span><span class="sxs-lookup"><span data-stu-id="a23c1-114">smallint</span></span>  <br/> |<span data-ttu-id="a23c1-115">Principale</span><span class="sxs-lookup"><span data-stu-id="a23c1-115">Primary</span></span>  <br/> |<span data-ttu-id="a23c1-116">Identificatore univoco assegnato al codec.</span><span class="sxs-lookup"><span data-stu-id="a23c1-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="a23c1-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="a23c1-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="a23c1-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23c1-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="a23c1-119">Univoci</span><span class="sxs-lookup"><span data-stu-id="a23c1-119">Unique</span></span>  <br/> |<span data-ttu-id="a23c1-120">Descrizione univoca del codec corrispondente a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="a23c1-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

