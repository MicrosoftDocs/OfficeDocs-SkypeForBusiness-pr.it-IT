---
title: Visualizzazione elementi multimediali
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Nella visualizzazione Media vengono archiviate le informazioni sul tipo di supporto utilizzato in una sessione peer-to-peer. Qualora si utilizzino più supporti, nella tabella saranno presenti più record per una sessione. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831791"
---
# <a name="media-view"></a><span data-ttu-id="5ae50-105">Visualizzazione elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="5ae50-105">Media view</span></span>
 
<span data-ttu-id="5ae50-106">Nella visualizzazione Media vengono archiviate le informazioni sul tipo di supporto utilizzato in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="5ae50-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="5ae50-107">Qualora si utilizzino più supporti, nella tabella saranno presenti più record per una sessione.</span><span class="sxs-lookup"><span data-stu-id="5ae50-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="5ae50-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ae50-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ae50-p103">La visualizzazione Media non deve essere utilizzata per calcolare la durata di utilizzo del supporto in una sessione. Questa visualizzazione contiene i dettagli di segnalazione dello scambio di supporti in una sessione. Lo scambio dei supporti viene effettuato mediante la richiesta INVITE, mentre StartTime indica l'ora in cui la richiesta INVITE è stata inviata. L'ora dell'invito non corrisponde necessariamente all'ora di inizio del supporto poiché questo viene avviato solo dopo che la sessione è stata accettata.</span><span class="sxs-lookup"><span data-stu-id="5ae50-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="5ae50-112">La visualizzazione Media contiene tutte le colonne nella visualizzazione [SessionDetails,](sessiondetails-0.md) oltre a quelle elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ae50-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="5ae50-113">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="5ae50-113">**Column**</span></span>|<span data-ttu-id="5ae50-114">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="5ae50-114">**Data Type**</span></span>|<span data-ttu-id="5ae50-115">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="5ae50-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ae50-116">**Contenuti multimediali**</span><span class="sxs-lookup"><span data-stu-id="5ae50-116">**Media**</span></span> <br/> |<span data-ttu-id="5ae50-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5ae50-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5ae50-118">Tipo di supporto.</span><span class="sxs-lookup"><span data-stu-id="5ae50-118">Media type.</span></span> <span data-ttu-id="5ae50-119">Per altre [informazioni, vedi la tabella MediaList.](medialist.md)</span><span class="sxs-lookup"><span data-stu-id="5ae50-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5ae50-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="5ae50-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="5ae50-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5ae50-121">datetime</span></span>  <br/> |<span data-ttu-id="5ae50-122">Ora di invio di una richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="5ae50-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="5ae50-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="5ae50-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="5ae50-124">datetime</span><span class="sxs-lookup"><span data-stu-id="5ae50-124">datetime</span></span>  <br/> |<span data-ttu-id="5ae50-125">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="5ae50-125">End time of the session.</span></span>  <br/> |
   

