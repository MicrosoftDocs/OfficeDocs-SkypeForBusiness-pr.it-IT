---
title: Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: "La tabella ConferenceJoinTimeThresholds contiene i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza. Il report Riepilogo temporale per la conferenza di partecipazione riepiloga il tempo necessario per consentire agli utenti di partecipare a una conferenza con successo. questi valori temporali vengono segnalati sia come media che in una delle categorie seguenti:"
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194841"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2dfb7-104">Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2dfb7-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2dfb7-105">La tabella ConferenceJoinTimeThresholds contiene i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="2dfb7-106">Il report Riepilogo temporale per la conferenza di partecipazione riepiloga il tempo necessario per consentire agli utenti di partecipare a una conferenza con successo. questi valori temporali vengono segnalati sia come media che in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dfb7-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="2dfb7-107">Meno di 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="2dfb7-108">Tra 2 secondi e 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="2dfb7-109">Tra 5 secondi e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="2dfb7-110">Più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="2dfb7-111">La tabella ConferenceJoinTimeThresholds contiene i valori di classificazione 2 secondi, 5 secondi e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="2dfb7-112">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2dfb7-113">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2dfb7-113">**Column**</span></span>|<span data-ttu-id="2dfb7-114">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2dfb7-114">**Data Type**</span></span>|<span data-ttu-id="2dfb7-115">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2dfb7-115">**Key/Index**</span></span>|<span data-ttu-id="2dfb7-116">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2dfb7-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2dfb7-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="2dfb7-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="2dfb7-118">int</span><span class="sxs-lookup"><span data-stu-id="2dfb7-118">int</span></span>  <br/> |<span data-ttu-id="2dfb7-119">Principale</span><span class="sxs-lookup"><span data-stu-id="2dfb7-119">Primary</span></span>  <br/> |<span data-ttu-id="2dfb7-120">Identificatore univoco per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="2dfb7-121">**ThresholdValue:**</span><span class="sxs-lookup"><span data-stu-id="2dfb7-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="2dfb7-122">int</span><span class="sxs-lookup"><span data-stu-id="2dfb7-122">int</span></span>  <br/> || <span data-ttu-id="2dfb7-123">Limite superiore per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="2dfb7-123">Upper limit for the classification.</span></span> <span data-ttu-id="2dfb7-124">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="2dfb7-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="2dfb7-125">2</span><span class="sxs-lookup"><span data-stu-id="2dfb7-125">2</span></span> <br/>  <span data-ttu-id="2dfb7-126">5</span><span class="sxs-lookup"><span data-stu-id="2dfb7-126">5</span></span> <br/>  <span data-ttu-id="2dfb7-127">10</span><span class="sxs-lookup"><span data-stu-id="2dfb7-127">10</span></span> <br/> |
   

