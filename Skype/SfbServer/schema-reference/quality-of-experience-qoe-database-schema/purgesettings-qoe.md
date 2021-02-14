---
title: Tabella PurgeSettings (QoE)
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
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: "Nella tabella PurgeSettings sono contenute informazioni che specificano se e quando i record QoE (qualità percepita dagli utenti) obsoleti verranno eliminati automaticamente dal database QoE. Si noti che le informazioni relative all'eliminazione possono essere ottenute anche da Skype for Business Server Management Shell eseguendo il comando seguente:"
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815806"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="e189e-104">Tabella PurgeSettings (QoE)</span><span class="sxs-lookup"><span data-stu-id="e189e-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="e189e-105">Nella tabella PurgeSettings sono contenute informazioni che specificano se e quando i record QoE (qualità percepita dagli utenti) obsoleti verranno eliminati automaticamente dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="e189e-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="e189e-106">Si noti che le informazioni relative all'eliminazione possono essere ottenute anche da Skype for Business Server Management Shell eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e189e-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="e189e-107">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e189e-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e189e-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e189e-108">**Column**</span></span>|<span data-ttu-id="e189e-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e189e-109">**Data Type**</span></span>|<span data-ttu-id="e189e-110">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e189e-110">**Key/Index**</span></span>|<span data-ttu-id="e189e-111">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e189e-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e189e-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="e189e-112">**ID**</span></span> <br/> |<span data-ttu-id="e189e-113">int</span><span class="sxs-lookup"><span data-stu-id="e189e-113">int</span></span>  <br/> |<span data-ttu-id="e189e-114">Principale</span><span class="sxs-lookup"><span data-stu-id="e189e-114">Primary</span></span>  <br/> |<span data-ttu-id="e189e-115">Identificatore univoco per la raccolta delle impostazioni di eliminazione QoE.</span><span class="sxs-lookup"><span data-stu-id="e189e-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="e189e-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="e189e-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="e189e-117">bit</span><span class="sxs-lookup"><span data-stu-id="e189e-117">bit</span></span>  <br/> ||<span data-ttu-id="e189e-118">Se impostato su True (1) Microsoft Lync Server 2013 elimina periodicamente i record non aggiornati dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="e189e-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="e189e-119">L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="e189e-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="e189e-120">Se impostato su False (0), i record non verranno eliminati automaticamente dal database.</span><span class="sxs-lookup"><span data-stu-id="e189e-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="e189e-121">Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="e189e-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="e189e-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="e189e-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="e189e-123">int</span><span class="sxs-lookup"><span data-stu-id="e189e-123">int</span></span>  <br/> ||<span data-ttu-id="e189e-p104">Specifica la giacenza dei record QoE (in giorni) che verranno eliminati dal database. Se l'eliminazione è abilitata, i record QoE precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="e189e-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="e189e-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="e189e-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="e189e-127">int</span><span class="sxs-lookup"><span data-stu-id="e189e-127">int</span></span>  <br/> ||<span data-ttu-id="e189e-p105">Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 1 (1 del mattino). Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 1 (1 del mattino).</span><span class="sxs-lookup"><span data-stu-id="e189e-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

