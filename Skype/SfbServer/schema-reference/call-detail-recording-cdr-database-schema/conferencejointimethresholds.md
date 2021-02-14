---
title: Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabella ConferenceJoinTimeThresholds include i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza. Questo rapporto riepiloga la quantità di tempo richiesto agli utenti per partecipare a una conferenza. I valori temporali vengono riportati come media e in una delle categorie seguenti:'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813306"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c7023-104">Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c7023-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7023-p102">La tabella ConferenceJoinTimeThresholds include i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza. Questo rapporto riepiloga la quantità di tempo richiesto agli utenti per partecipare a una conferenza. I valori temporali vengono riportati come media e in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7023-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="c7023-107">Meno di 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="c7023-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="c7023-108">Tra 2 e 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="c7023-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="c7023-109">Tra 5 e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="c7023-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="c7023-110">Più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="c7023-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="c7023-111">La tabella ConferenceJoinTimeThresholds include i valori di classificazione 2 secondi, 5 secondi e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="c7023-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="c7023-112">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7023-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c7023-113">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c7023-113">**Column**</span></span>|<span data-ttu-id="c7023-114">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="c7023-114">**Data Type**</span></span>|<span data-ttu-id="c7023-115">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="c7023-115">**Key/Index**</span></span>|<span data-ttu-id="c7023-116">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c7023-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c7023-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="c7023-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="c7023-118">int</span><span class="sxs-lookup"><span data-stu-id="c7023-118">int</span></span>  <br/> |<span data-ttu-id="c7023-119">Principale</span><span class="sxs-lookup"><span data-stu-id="c7023-119">Primary</span></span>  <br/> |<span data-ttu-id="c7023-120">Identificatore univoco della classificazione.</span><span class="sxs-lookup"><span data-stu-id="c7023-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="c7023-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="c7023-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="c7023-122">int</span><span class="sxs-lookup"><span data-stu-id="c7023-122">int</span></span>  <br/> || <span data-ttu-id="c7023-p103">Limite superiore per la classificazione. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="c7023-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="c7023-125">2 </span><span class="sxs-lookup"><span data-stu-id="c7023-125">2</span></span> <br/>  <span data-ttu-id="c7023-126">5 </span><span class="sxs-lookup"><span data-stu-id="c7023-126">5</span></span> <br/>  <span data-ttu-id="c7023-127">10  </span><span class="sxs-lookup"><span data-stu-id="c7023-127">10</span></span> <br/> |
   

