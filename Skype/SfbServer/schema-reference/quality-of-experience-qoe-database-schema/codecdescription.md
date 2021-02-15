---
title: Tabella CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabella CodecDescription associa identificatori codec univoci al codec corrispondente. I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831346"
---
# <a name="codecdescription-table"></a><span data-ttu-id="c1a21-105">Tabella CodecDescription</span><span class="sxs-lookup"><span data-stu-id="c1a21-105">CodecDescription table</span></span>
 
<span data-ttu-id="c1a21-106">La tabella CodecDescription associa identificatori codec univoci al codec corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c1a21-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="c1a21-107">I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="c1a21-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="c1a21-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1a21-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="c1a21-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c1a21-109">**Column**</span></span>|<span data-ttu-id="c1a21-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="c1a21-110">**Data Type**</span></span>|<span data-ttu-id="c1a21-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="c1a21-111">**Key/Index**</span></span>|<span data-ttu-id="c1a21-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c1a21-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1a21-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="c1a21-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="c1a21-114">smallint</span><span class="sxs-lookup"><span data-stu-id="c1a21-114">smallint</span></span>  <br/> |<span data-ttu-id="c1a21-115">Principale</span><span class="sxs-lookup"><span data-stu-id="c1a21-115">Primary</span></span>  <br/> |<span data-ttu-id="c1a21-116">Identificatore univoco assegnato al codec.</span><span class="sxs-lookup"><span data-stu-id="c1a21-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="c1a21-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="c1a21-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="c1a21-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1a21-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="c1a21-119">Univoco</span><span class="sxs-lookup"><span data-stu-id="c1a21-119">Unique</span></span>  <br/> |<span data-ttu-id="c1a21-120">Descrizione univoca del codec corrispondente a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="c1a21-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

