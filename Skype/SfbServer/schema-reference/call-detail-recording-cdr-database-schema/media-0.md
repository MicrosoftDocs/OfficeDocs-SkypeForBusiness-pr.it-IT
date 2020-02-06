---
title: Visualizzazione multimediale
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La visualizzazione multimediale archivia le informazioni su un tipo di elemento multimediale usato in una sessione peer-to-peer. Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815054"
---
# <a name="media-view"></a><span data-ttu-id="13cb8-105">Visualizzazione multimediale</span><span class="sxs-lookup"><span data-stu-id="13cb8-105">Media view</span></span>
 
<span data-ttu-id="13cb8-106">La visualizzazione multimediale archivia le informazioni su un tipo di elemento multimediale usato in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="13cb8-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="13cb8-107">Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="13cb8-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="13cb8-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="13cb8-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13cb8-109">La visualizzazione multimediale non deve essere usata per calcolare la durata del supporto per una sessione.</span><span class="sxs-lookup"><span data-stu-id="13cb8-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="13cb8-110">Questa visualizzazione contiene i dettagli di segnalazione dello scambio multimediale in una sessione.</span><span class="sxs-lookup"><span data-stu-id="13cb8-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="13cb8-111">Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio del supporto, perché il supporto viene avviato solo dopo l'accettazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="13cb8-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="13cb8-112">La visualizzazione multimediale contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre a quelle elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="13cb8-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="13cb8-113">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="13cb8-113">**Column**</span></span>|<span data-ttu-id="13cb8-114">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="13cb8-114">**Data Type**</span></span>|<span data-ttu-id="13cb8-115">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="13cb8-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13cb8-116">**Contenuti multimediali**</span><span class="sxs-lookup"><span data-stu-id="13cb8-116">**Media**</span></span> <br/> |<span data-ttu-id="13cb8-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="13cb8-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="13cb8-118">Tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="13cb8-118">Media type.</span></span> <span data-ttu-id="13cb8-119">Per altre informazioni, vedere la [tabella degli elementi multimediali](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="13cb8-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="13cb8-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="13cb8-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="13cb8-121">DateTime</span><span class="sxs-lookup"><span data-stu-id="13cb8-121">datetime</span></span>  <br/> |<span data-ttu-id="13cb8-122">Ora in cui è stata inviata una richiesta multimediale.</span><span class="sxs-lookup"><span data-stu-id="13cb8-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="13cb8-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="13cb8-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="13cb8-124">DateTime</span><span class="sxs-lookup"><span data-stu-id="13cb8-124">datetime</span></span>  <br/> |<span data-ttu-id="13cb8-125">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="13cb8-125">End time of the session.</span></span>  <br/> |
   

