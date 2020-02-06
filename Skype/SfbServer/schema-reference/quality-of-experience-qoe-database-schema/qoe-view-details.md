---
title: Dettagli della visualizzazione QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Le visualizzazioni coprono gli scenari più comuni per la restituzione dei dati dal database SQL QoE. Si tratta di visualizzazioni consigliate usate per creare report personalizzati anziché accedere direttamente alle tabelle del database. Questo perché le visualizzazioni hanno più probabilità di mantenere la compatibilità con le versioni precedenti.
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807174"
---
# <a name="qoe-view-details"></a><span data-ttu-id="8f590-104">Dettagli della visualizzazione QoE</span><span class="sxs-lookup"><span data-stu-id="8f590-104">QoE view details</span></span>
 
<span data-ttu-id="8f590-105">Le visualizzazioni coprono gli scenari più comuni per la restituzione dei dati dal database SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="8f590-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="8f590-106">Si tratta di visualizzazioni consigliate usate per creare report personalizzati anziché accedere direttamente alle tabelle del database. Questo perché le visualizzazioni hanno più probabilità di mantenere la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8f590-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="8f590-107">**Nome visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="8f590-107">**View Name**</span></span>|<span data-ttu-id="8f590-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8f590-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8f590-109">Visualizzazione AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="8f590-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="8f590-110">Archivia informazioni su ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="8f590-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="8f590-111">Visualizzazione MediaLine</span><span class="sxs-lookup"><span data-stu-id="8f590-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="8f590-112">Archivia informazioni su ogni riga multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="8f590-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="8f590-113">Una sessione audio in genere contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="8f590-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="8f590-114">Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video; Tuttavia, la sessione può contenere due linee multimediali video se viene usato un dispositivo per i servizi di conferenza o se viene usata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f590-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="8f590-115">Visualizzazione NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="8f590-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="8f590-116">Archivia informazioni sulla configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="8f590-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="8f590-117">Visualizzazione sessione</span><span class="sxs-lookup"><span data-stu-id="8f590-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="8f590-118">Archivia informazioni sulle sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="8f590-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="8f590-119">Visualizzazione UserAgent</span><span class="sxs-lookup"><span data-stu-id="8f590-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="8f590-120">Archivia informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="8f590-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="8f590-121">Visualizzazione VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="8f590-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="8f590-122">Archivia informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="8f590-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

