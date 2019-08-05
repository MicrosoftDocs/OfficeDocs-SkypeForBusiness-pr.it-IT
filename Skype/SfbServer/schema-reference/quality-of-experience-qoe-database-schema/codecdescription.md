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
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabella CodecDescription associa identificatori di codec univoci al relativo codec. I codec vengono usati per codificare i segnali digitali per la trasmissione e la trasmissione e quindi per decodificare i segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194632"
---
# <a name="codecdescription-table"></a><span data-ttu-id="a9a02-105">Tabella CodecDescription</span><span class="sxs-lookup"><span data-stu-id="a9a02-105">CodecDescription table</span></span>
 
<span data-ttu-id="a9a02-106">La tabella CodecDescription associa identificatori di codec univoci al relativo codec.</span><span class="sxs-lookup"><span data-stu-id="a9a02-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="a9a02-107">I codec vengono usati per codificare i segnali digitali per la trasmissione e la trasmissione e quindi per decodificare i segnali per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="a9a02-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="a9a02-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a02-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="a9a02-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a9a02-109">**Column**</span></span>|<span data-ttu-id="a9a02-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a9a02-110">**Data Type**</span></span>|<span data-ttu-id="a9a02-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="a9a02-111">**Key/Index**</span></span>|<span data-ttu-id="a9a02-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a9a02-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9a02-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="a9a02-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="a9a02-114">smallint</span><span class="sxs-lookup"><span data-stu-id="a9a02-114">smallint</span></span>  <br/> |<span data-ttu-id="a9a02-115">Principale</span><span class="sxs-lookup"><span data-stu-id="a9a02-115">Primary</span></span>  <br/> |<span data-ttu-id="a9a02-116">Identificatore univoco assegnato al codec.</span><span class="sxs-lookup"><span data-stu-id="a9a02-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="a9a02-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="a9a02-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="a9a02-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9a02-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="a9a02-119">Univoci</span><span class="sxs-lookup"><span data-stu-id="a9a02-119">Unique</span></span>  <br/> |<span data-ttu-id="a9a02-120">Descrizione univoca del codec corrispondente a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="a9a02-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

