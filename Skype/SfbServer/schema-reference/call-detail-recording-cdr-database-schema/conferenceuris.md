---
title: Tabella ConferenceUris in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database. Ogni record nella tabella rappresenta un URI di conferenza.
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194826"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9741c-104">Tabella ConferenceUris in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9741c-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9741c-105">La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="9741c-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="9741c-106">Ogni record nella tabella rappresenta un URI di conferenza.</span><span class="sxs-lookup"><span data-stu-id="9741c-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="9741c-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="9741c-107">**Column**</span></span>|<span data-ttu-id="9741c-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="9741c-108">**Data Type**</span></span>|<span data-ttu-id="9741c-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="9741c-109">**Key/Index**</span></span>|<span data-ttu-id="9741c-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="9741c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9741c-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9741c-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9741c-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="9741c-112">datetime</span></span>  <br/> |<span data-ttu-id="9741c-113">Principale</span><span class="sxs-lookup"><span data-stu-id="9741c-113">Primary</span></span>  <br/> |<span data-ttu-id="9741c-114">Indicatore di data e ora, interno usato.</span><span class="sxs-lookup"><span data-stu-id="9741c-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="9741c-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="9741c-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="9741c-116">int</span><span class="sxs-lookup"><span data-stu-id="9741c-116">int</span></span>  <br/> |<span data-ttu-id="9741c-117">Principale</span><span class="sxs-lookup"><span data-stu-id="9741c-117">Primary</span></span>  <br/> |<span data-ttu-id="9741c-118">Numero univoco che identifica questo URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="9741c-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="9741c-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="9741c-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="9741c-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9741c-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="9741c-121">URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="9741c-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="9741c-122">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="9741c-122">**Checksum**</span></span> <br/> |<span data-ttu-id="9741c-123">int</span><span class="sxs-lookup"><span data-stu-id="9741c-123">int</span></span>  <br/> ||<span data-ttu-id="9741c-124">Checksum di ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="9741c-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="9741c-125">Usato per aumentare la velocità delle ricerche nel database.</span><span class="sxs-lookup"><span data-stu-id="9741c-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="9741c-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="9741c-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="9741c-127">int</span><span class="sxs-lookup"><span data-stu-id="9741c-127">int</span></span>  <br/> |<span data-ttu-id="9741c-128">Esterna</span><span class="sxs-lookup"><span data-stu-id="9741c-128">Foreign</span></span>  <br/> |<span data-ttu-id="9741c-129">Tipo di URI, ad esempio conf: chat per la conferenza di messaggistica istantanea o conf: audio-video per conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="9741c-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="9741c-130">Per altre informazioni, vedere la tabella [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="9741c-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

