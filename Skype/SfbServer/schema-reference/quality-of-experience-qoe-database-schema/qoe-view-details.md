---
title: Dettagli della visualizzazione QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Le viste disponibili soddisfano gli scenari più comuni per la restituzione di dati dal database di SQL Server QoE. Si tratta di visualizzazioni consigliate utilizzate per la creazione di report personalizzati invece di accedere direttamente alle tabelle di database. Questo perché le visualizzazioni hanno maggiori probabilità di mantenere la compatibilità con le versioni precedenti.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834476"
---
# <a name="qoe-view-details"></a><span data-ttu-id="4f2de-104">Dettagli della visualizzazione QoE</span><span class="sxs-lookup"><span data-stu-id="4f2de-104">QoE view details</span></span>
 
<span data-ttu-id="4f2de-105">Le viste disponibili soddisfano gli scenari più comuni per la restituzione di dati dal database di SQL Server QoE.</span><span class="sxs-lookup"><span data-stu-id="4f2de-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="4f2de-106">Si tratta di visualizzazioni consigliate utilizzate per la creazione di report personalizzati invece di accedere direttamente alle tabelle di database. Questo perché le visualizzazioni hanno maggiori probabilità di mantenere la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="4f2de-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="4f2de-107">**Nome visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="4f2de-107">**View Name**</span></span>|<span data-ttu-id="4f2de-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4f2de-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4f2de-109">Visualizzazione AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="4f2de-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="4f2de-110">Archivia informazioni su ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="4f2de-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="4f2de-111">Visualizzazione MediaLine</span><span class="sxs-lookup"><span data-stu-id="4f2de-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="4f2de-112">Archivia informazioni su ogni linea multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="4f2de-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="4f2de-113">Una sessione audio in genere contiene una linea multimediale audio.</span><span class="sxs-lookup"><span data-stu-id="4f2de-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="4f2de-114">Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta.</span><span class="sxs-lookup"><span data-stu-id="4f2de-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="4f2de-115">Visualizzazione NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="4f2de-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="4f2de-116">Archivia informazioni sulla configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="4f2de-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="4f2de-117">Visualizzazione sessione</span><span class="sxs-lookup"><span data-stu-id="4f2de-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="4f2de-118">Archivia informazioni sulle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="4f2de-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="4f2de-119">Visualizzazione UserAgent</span><span class="sxs-lookup"><span data-stu-id="4f2de-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="4f2de-120">Archivia informazioni sugli agenti utenti coinvolti nelle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="4f2de-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="4f2de-121">Visualizzazione VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="4f2de-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="4f2de-122">Archivia informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="4f2de-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

